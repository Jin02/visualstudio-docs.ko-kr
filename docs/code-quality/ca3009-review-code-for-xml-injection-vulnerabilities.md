---
title: 'CA3009: 코드에서 XML 삽입 취약성에 대해 검토합니다.'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 37ba7e8664c6fa24e302dbebd38643a0c451114c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237253"
---
# <a name="ca3009-review-code-for-xml-injection-vulnerabilities"></a>CA3009: 코드에서 XML 삽입 취약성에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForXmlInjectionVulnerabilities|
|CheckId|CA3009|
|범주|Microsoft.Security|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

잠재적으로 신뢰할 수 없는 HTTP 요청 입력은 원시 XML 출력에 도달 합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력으로 작업 하는 경우 XML 삽입 공격에 유의 해야 합니다. 공격자는 xml 주입을 사용 하 여 특수 문자를 XML 문서에 삽입 하 여 xml 문서에 잘못 된 XML을 만들 수 있습니다. 또는 공격자가 선택 된 XML 노드를 악의적으로 삽입할 수 있습니다.

이 규칙은 원시 XML 쓰기에 도달 하는 HTTP 요청에서 입력을 찾으려고 시도 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어 한 어셈블리가 HTTP 요청 입력을 읽은 다음 원시 XML을 작성 하는 다른 어셈블리에 전달 하는 경우이 규칙은 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙에서 메서드 호출을 통해 데이터 흐름을 분석 하는 데 구성 가능한 제한이 있습니다. EditorConfig 파일에서 제한을 구성 하는 방법에 대 한 [Analyzer 구성](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 을 참조 하세요.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

원시 XML을 쓰지 않습니다. 대신 입력을 XML로 인코딩하는 메서드나 속성을 사용 합니다.

또는 XML-원시 XML을 작성 하기 전에 입력을 인코딩합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서 경고를 표시 하지 않습니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.Xml;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        XmlDocument d = new XmlDocument();
        XmlElement root = d.CreateElement("root");
        d.AppendChild(root);

        XmlElement allowedUser = d.CreateElement("allowedUser");
        root.AppendChild(allowedUser);

        allowedUser.InnerXml = "alice";

        // If an attacker uses this for input:
        //     some text<allowedUser>oscar</allowedUser>
        // Then the XML document will be:
        //     <root>some text<allowedUser>oscar</allowedUser></root>
        root.InnerXml = input;
    }
}
```

```vb
Imports System
Imports System.Xml

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim d As XmlDocument = New XmlDocument()
        Dim root As XmlElement = d.CreateElement("root")
        d.AppendChild(root)

        Dim allowedUser As XmlElement = d.CreateElement("allowedUser")
        root.AppendChild(allowedUser)

        allowedUser.InnerXml = "alice"

        ' If an attacker uses this for input:
        '     some text<allowedUser>oscar</allowedUser>
        ' Then the XML document will be:
        '     <root>some text<allowedUser>oscar</allowedUser></root>
        root.InnerXml = input
    End Sub
End Class
```

### <a name="solution"></a>솔루션

```csharp
using System;
using System.Xml;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        XmlDocument d = new XmlDocument();
        XmlElement root = d.CreateElement("root");
        d.AppendChild(root);

        XmlElement allowedUser = d.CreateElement("allowedUser");
        root.AppendChild(allowedUser);

        allowedUser.InnerText = "alice";

        // If an attacker uses this for input:
        //     some text<allowedUser>oscar</allowedUser>
        // Then the XML document will be:
        //     <root>&lt;allowedUser&gt;oscar&lt;/allowedUser&gt;some text<allowedUser>alice</allowedUser></root>
        root.InnerText = input;
    }
}
```

```vb
Imports System
Imports System.Xml

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim d As XmlDocument = New XmlDocument()
        Dim root As XmlElement = d.CreateElement("root")
        d.AppendChild(root)

        Dim allowedUser As XmlElement = d.CreateElement("allowedUser")
        root.AppendChild(allowedUser)

        allowedUser.InnerText = "alice"

        ' If an attacker uses this for input:
        '     some text<allowedUser>oscar</allowedUser>
        ' Then the XML document will be:
        '     <root>&lt;allowedUser&gt;oscar&lt;/allowedUser&gt;some text<allowedUser>alice</allowedUser></root>
        root.InnerText = input
    End Sub
End Class
```
