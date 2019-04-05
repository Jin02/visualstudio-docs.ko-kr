---
title: 웹 사이트 지원 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 91deb6d2e3ec58533ac9339c8c94634db23ec996
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58986471"
---
# <a name="web-site-support"></a>웹 사이트 지원
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

웹 사이트 프로젝트 시스템은 웹 프로젝트를 만드는 프로젝트 시스템. 웹 프로젝트는 웹 응용 프로그램에 만듭니다. 웹 사이트 프로젝트 코드를 연결 된 각 웹 페이지에 대 한 하나의 실행 파일을 생성 합니다. 추가 파일 /App_Code 폴더의 소스 코드 파일에서 생성 됩니다.  
  
 웹 사이트 프로젝트 시스템은 기존 프로젝트 시스템에 템플릿 및 등록 특성을 추가 하 여 생성 됩니다. 이러한 특성 중 하나는 언어에 대 한 IntelliSense 공급자를 선택합니다. IntelliSense 공급자 구현 참조를 처리 하 고 캐시 되지 않은 스마트 웹 페이지를 요청 하는 경우 언어 컴파일러를 호출 합니다.  
  
 웹 페이지를 컴파일하는 데 사용 되는 언어 컴파일러를 사용 하 여 등록 해야 [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]합니다. 사용할 수는 [ \<컴파일러 > 요소](http://msdn.microsoft.com/library/7a151659-b803-4c27-b5ce-1c4aa0d5a823) 다음 예제와 같이 컴파일러에 등록 하는 Web.config 파일에서:  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>섹션 내용  
 [웹 사이트 지원 템플릿](../../extensibility/internals/web-site-support-templates.md)  
 새 웹 사이트 프로젝트와 연결 된 항목을 만드는 데 사용할 수 있는 템플릿을 나열 합니다.  
  
 [웹 사이트 지원 특성](../../extensibility/internals/web-site-support-attributes.md)  
 웹 사이트 프로젝트를 연결 하는 등록 특성을 제공 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 고 [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [웹 프로젝트](../../extensibility/internals/web-projects.md)  
 두 종류의 웹 프로젝트, 웹 사이트 프로젝트와 웹 응용 프로그램 프로젝트의 개요를 제공 합니다.
