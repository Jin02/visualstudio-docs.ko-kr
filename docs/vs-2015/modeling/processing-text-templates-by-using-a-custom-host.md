---
title: 사용자 지정 호스트를 사용 하 여 텍스트 템플릿 처리 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
ms.assetid: affa3296-854d-47d6-9685-285f6d9ba5dc
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e9f27d203f317a63049015dbeba073d8ee075e61
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428079"
---
# <a name="processing-text-templates-by-using-a-custom-host"></a>사용자 지정 호스트를 사용하여 텍스트 템플릿 처리
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

합니다 *텍스트 템플릿 변환* 프로세스에서는 *텍스트 템플릿* 파일을 입력 하 고 텍스트 파일을 출력으로 생성 합니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 확장명에서나 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]가 설치된 컴퓨터에서 실행되는 독립 실행형 응용 프로그램에서 텍스트 변형 엔진을 호출할 수 있습니다. 그러나 제공 해야 합니다는 *텍스트 템플릿 호스트*합니다. 이 클래스는 템플릿을 환경에 연결하여 어셈블리, 포함 파일 등의 리소스를 찾고 출력 및 오류 메시지를 처리합니다.  
  
> [!TIP]
> [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 실행될 패키지나 확장을 작성하는 경우 고유 호스트를 작성하는 대신 텍스트 템플릿 서비스를 사용하십시오. 자세한 내용은 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)합니다.  
  
> [!NOTE]
> 서버 응용 프로그램에서는 텍스트 템플릿 변환을 사용하지 않는 것이 좋으며, 단일 스레드에서만 텍스트 템플릿 변형을 사용하는 것이 좋습니다. 텍스트 템플릿 엔진에서는 단일 AppDomain을 사용하여 템플릿을 변환하고 컴파일하고 실행하기 때문입니다. 변환된 코드는 스레드로부터 안전하도록 설계되지 않았습니다. 텍스트 템플릿 엔진은 디자인 타임에 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로젝트에 있는 파일을 연속으로 처리하도록 설계되었습니다.  
>   
> 런타임에 응용 프로그램에 전처리 된 텍스트 템플릿을 사용 하 여는 것이 좋습니다: 참조 [T4 텍스트 템플릿을 사용 하 여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
 응용 프로그램에서 컴파일 타임에 고정된 템플릿 집합을 사용하는 경우 전처리된 텍스트 템플릿을 사용하기가 더 쉽습니다. 또한 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]가 설치되지 않은 컴퓨터에서 응용 프로그램이 실행되는 경우에도 이 방법을 사용할 수 있습니다. 자세한 내용은 [T4 텍스트 템플릿을 사용 하 여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
## <a name="executing-a-text-template-in-your-application"></a>응용 프로그램에서 텍스트 템플릿 실행  
 텍스트 템플릿을 실행하려면 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>의 ProcessTemplate 메서드를 호출합니다.  
  
```  
using Microsoft.VisualStudio.TextTemplating;  
...  
Engine engine = new Engine();  
string output = engine.ProcessTemplate(templateString, host);  
```  
  
 응용 프로그램에서 템플릿을 찾아 제공해야 하며 출력을 처리해야 합니다.  
  
 `host` 매개 변수에서 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>를 구현하는 클래스를 제공해야 합니다. 이 클래스는 엔진에서 다시 호출됩니다.  
  
 호스트는 오류를 기록하고 어셈블리 및 포함 파일에 대한 참조를 확인할 있어야 하며 템플릿이 실행될 수 있는 응용 프로그램 도메인을 제공하고 각 지시문에 적절한 프로세서를 호출할 수 있어야 합니다.  
  
 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> 에 정의 된 **Microsoft.VisualStudio.TextTemplating.\*합니다. 0 dll**, 및 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> 에 정의 된 **Microsoft.VisualStudio.TextTemplating.Interfaces.\*합니다. 0 dll**합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 외부에서 텍스트 템플릿 기능을 사용할 수 있도록 하는 사용자 지정 텍스트 템플릿 호스트를 만드는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>  
  
## <a name="related-sections"></a>관련 단원  
 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)  
 텍스트 변형의 작동 방식과 사용자 지정할 수 있는 부분에 대해 설명합니다.  
  
 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 텍스트 템플릿 지시문 프로세서에 대해 간략하게 설명합니다.
