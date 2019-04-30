---
title: 'CA3076: XSLT 스크립트 실행이 안전하지 않습니다.'
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f98b022aef49a4d98ad4864793aa55732f8de6c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541092"
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: XSLT 스크립트 실행이 안전하지 않습니다.

|||
|-|-|
|TypeName|InsecureXSLTScriptExecution|
|CheckId|CA3076|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

.NET 애플리케이션에서 비보안 방식으로 XSLT(Extensible Stylesheets Language Transformations)를 실행하는 경우 프로세서는 공격자에게 중요한 정보를 노출하여 서비스 거부 및 사이트 간 공격을 유발할 수 있는 신뢰할 수 없는 URI 참조를 확인할 수 있습니다. 자세한 내용은 [XSLT 보안 Considerations(.NET Guide)](/dotnet/standard/data/xml/xslt-security-considerations)합니다.

## <a name="rule-description"></a>규칙 설명

**XSLT** 는 XML 데이터를 변환하기 위한 W3C(World Wide Web 콘소시엄) 표준입니다. XSLT는 XML 데이터를 HTML, 고정 길이 텍스트, 쉼표로 구분 된 텍스트 또는 XML 형식 등의 다른 형식으로 변환 하기 위한 스타일 시트를 작성 하려면 일반적으로 사용 됩니다. 이 기능은 프로젝트에서 기본적으로는 금지되어 있지만 사용하도록 설정할 수 있습니다.

공격 노출 영역을 노출 하지 하도록이 규칙 때마다 트리거는 XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 안전 하지 않은 조합 인스턴스의 받습니다 <xref:System.Xml.Xsl.XsltSettings> 및 <xref:System.Xml.XmlResolver>, 악성 스크립트를 처리를 허용 하는 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 안전 하지 않은 XsltSettings 인수를 XsltSettings 바꿉니다.<xref:System.Xml.Xsl.XsltSettings.Default%2A> 또는 인스턴스를 사용 하 여 문서 함수 및 스크립트 실행 비활성화입니다.

- <xref:System.Xml.XmlResolver> 인수를 null 또는 <xref:System.Xml.XmlSecureResolver> 인스턴스로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation-that-uses-xsltsettingstrustedxslt"></a>XsltSettings.TrustedXslt를 사용 하는 위반

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
         void TestMethod()
        {
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
        }
    }
}
```

### <a name="solution-that-uses-xsltsettingsdefault"></a>XsltSettings.Default를 사용 하는 솔루션

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violationmdashdocument-function-and-script-execution-not-disabled"></a>위반&mdash;문서 사용 하지 않도록 설정 하는 함수 및 스크립트 실행

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solutionmdashdisable-document-function-and-script-execution"></a>솔루션&mdash;문서 함수 및 스크립트 실행을 사용 하지 않도록 설정

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```

## <a name="see-also"></a>참고자료

- [XSLT 보안 고려 사항 (.NET 가이드)](/dotnet/standard/data/xml/xslt-security-considerations)