---
title: 웹 사이트 지원 템플릿 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- we site projects, templates
ms.assetid: 37173c97-486b-4b3c-8ed3-cf5890c4de23
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0e3c139ae6f2f9ec618e6382a1551a9e35eee7ec
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80703460"
---
# <a name="web-site-support-templates"></a>웹 사이트 지원 템플릿
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]웹 사이트 프로젝트 및 항목 템플릿은 새 웹 사이트 프로젝트 및 항목을 처음부터 만들 필요가 없으므로 개발 프로세스를 가속화하는 재사용 가능하고 사용자 지정 가능한 웹 사이트 프로젝트 및 항목 스텁을 제공합니다. 템플릿에 대한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 자세한 내용은 [프로젝트 및 항목 템플릿 만들기를](../../ide/creating-project-and-item-templates.md)참조하십시오.

## <a name="project-template-folder"></a>프로젝트 템플릿 폴더
 웹 프로젝트 템플릿은 일반적으로 *[Visual Studio 설치*경로]\Common7\IDE\ProjectTemplates\Web에\\설치되며, 각 템플릿은 웹 프로그래밍 언어의 이름을 따서 명명된 하위 폴더에 있습니다.

## <a name="project-file"></a>프로젝트 파일
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 개발 환경(IDE)에는 올바른 프로젝트 유형에 템플릿을 매핑하는 방법으로 프로젝트 파일 확장이 필요합니다. 웹 프로젝트에는 프로젝트 파일이 없기 때문에 더미 프로젝트 파일 확장자 .webproj가 등록되어 템플릿을 프로젝트 유형에 매핑합니다.

 선택적으로 언어 이름 문자열을 템플릿에 추가하여 웹 프로젝트 시스템에서 템플릿을 기반으로 하는 항목에 대한 **새 항목 추가** 대화 상자에서 언어 기본값을 설정할 수 있습니다. 문자열은 파일의 첫 번째 줄이어야 합니다. IntelliSense 엔진 등록에서 AddItemLanguageName에 등록된 이름과 프로젝트 하위 유형(VsTemplate)에 등록된 이름과 일치해야 합니다. 자세한 내용은 [웹 사이트 지원 특성을](../../extensibility/internals/web-site-support-attributes.md)참조하십시오.

 문자열이 없는 경우 웹 프로젝트 시스템은 프로젝트 템플릿에 의해 웹 프로젝트에 추가된 페이지의 언어 특성 및 파일 확장명에 따라 기본 언어를 확인하려고 시도합니다.

## <a name="project-templates"></a>프로젝트 템플릿
 웹 사이트 프로젝트 템플릿은 **파일** 메뉴의 새 **웹 사이트** 명령에 대한 응답으로 새 웹 사이트를 빌드하는 데 사용됩니다. 현재 세 가지 웹 사이트 프로젝트 유형이 지원됩니다.

- 빈 웹 사이트 프로젝트

- 웹 사이트 프로젝트

- 웹 서비스 프로젝트

### <a name="empty-web-site-projects"></a>빈 웹 사이트 프로젝트
 이러한 파일은 **빈 웹 사이트** 명령에 대한 응답으로 새 빈 웹 사이트를 만들며, 이 명령은 **새 웹** > **사이트**파일을 선택한 후 사용할 수 있습니다.

- 빈웹.vs템플릿

     새 빈 웹 사이트 만들기를 안내하는 템플릿 파일입니다.

- 빈웹.웹프로즈

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. EmptyWeb.vs 템플릿 파일에서 프로젝트 파일 참조를 다정합니다.

### <a name="web-site-projects"></a>웹 사이트 프로젝트
 이러한 파일은 **ASP.NET 웹 사이트** 명령에 대한 응답으로 새 웹 사이트를 만들며, 새 **웹** > **사이트**파일을 선택한 후 사용할 수 있습니다.

- Default.aspx

     새 웹 사이트의 기본 홈 페이지입니다. Language 특성은 codebehind 언어를 지정하고 CodeFile 특성은 이 페이지와 연결된 코드 behind 코드를 포함하는 종속 파일을 지정합니다.

- Default.aspx. *확장 프로그램*

     기본 홈 페이지에 대한 코드 behind 코드가 포함된 종속 파일입니다. 코드 뒤에 언어는이 파일의 *확장을* 결정합니다.

- web.config

     루트 web.site 구성 파일입니다.

- 웹 응용 프로그램.vs 템플릿

     웹 사이트 솔루션의 내용을 결정하고 App_Data 폴더를 만드는 템플릿 파일입니다.

- 웹 응용 프로그램.webproj

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. WebApplication.vs 템플릿 파일에서 프로젝트 파일 참조를 다정합니다.

### <a name="web-service-projects"></a>웹 서비스 프로젝트
 이러한 파일은 **ASP.NET 웹 서비스** 명령에 대한 응답으로**새 웹 사이트를**만들며, 새 웹 사이트 **파일을** > 선택한 후 사용할 수 있습니다.

- 서비스.asmx

     새 웹 서비스의 HTML 페이지입니다. Language 특성은 codebehind 언어를 지정하고 CodeBehind 특성은 이 서비스와 연결된 코드 behind 코드를 포함하는 종속 파일을 지정합니다.

- 서비스. *확장*

     서비스 클래스를 구현하는 종속 파일입니다. 코드 뒤에 언어는이 파일의 *확장을* 결정합니다.

- web.config

- 루트 web.site 구성 파일입니다.

- 웹 서비스.vs 템플릿

     웹 사이트 솔루션의 내용을 결정하고 App_Data 및 App_Code 폴더를 강제로 만드는 템플릿 파일입니다. 서비스입니다. *확장파일이* App_Code 폴더에 복사됩니다.

- 웹서비스.웹프로즈

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. WebService.vs 템플릿 파일에서 프로젝트 파일 참조를 다정합니다.

## <a name="project-item-template-folder"></a>프로젝트 항목 템플릿 폴더
 웹 프로젝트 항목 템플릿은 일반적으로 *[Visual Studio 설치*경로]\Common7\IDE\ItemTemplates\Web에\\설치되며, 각 템플릿은 웹 프로그래밍 언어의 이름을 따서 명명된 하위 폴더에 있습니다.

## <a name="project-item-templates"></a>프로젝트 항목 템플릿
 웹 사이트 프로젝트 항목 템플릿은 **기존 항목 추가** 명령에 대한 응답으로 웹 사이트에 새 웹 페이지를 추가하는 데 사용됩니다. 이러한 종류의 웹 페이지는 현재 지원됩니다.

- 새로운 클래스

- 새 HTML 페이지

- 새 웹 양식

- 새 마스터 페이지

### <a name="new-class"></a>새로운 클래스
 이 템플릿은 새 클래스 **추가** 명령에 대한 응답으로 빈 클래스를 정의하는 새 소스 파일을 만듭니다.

- 클래스입니다. *확장*

     빈 클래스를 구현하는 원본 파일입니다. 코드 뒤에 언어는이 파일의 *확장을* 결정합니다.

- 클래스 대 템플릿

     원본 파일을 만들고 해당 내용을 결정하는 템플릿 파일입니다.

### <a name="new-html-page"></a>새 HTML 페이지
 이 템플릿은 새 HTML 페이지 **추가** 명령에 대한 응답으로 새 웹 페이지를 만듭니다.

- HTMLPage.htm

     웹 페이지의 시작 내용입니다. 이 웹 페이지에는 일반적으로 연결된 코드 뒤에 종속 파일이 없습니다. 연결된 코드 뒤에 파일이 있는 스마트 페이지를 만들려면 대신 웹 양식 템플릿을 사용합니다.

- HTMLPage.vs 템플릿

     웹 페이지를 만들고 해당 내용을 결정하는 템플릿 파일입니다.

### <a name="new-webform"></a>새 웹 폼
 이 템플릿은 새 웹 **양식 추가** 명령에 대한 응답으로 새 스마트 웹 페이지를 만듭니다.

 종속 코드 뒤에 소스 파일을 만들려면 **별도의 파일에 코드 배치를**선택합니다. 그렇지 않으면 빈 스크립팅 블록이 있고 종속 \<파일을 연결하는 페이지 %> 지시문이 없는 단일 웹 페이지가 만들어집니다.

 선택한 마스터 페이지에 대한 콘텐츠 페이지를 만들려면 **마스터 페이지 선택을**선택합니다.

- 웹폼.aspx

     웹 페이지의 시작 내용입니다. 이 웹 페이지에는 연결된 코드 뒤에 종속 파일이 없습니다.

- WebForm_cb.aspx

     웹 페이지의 시작 내용입니다. 이 웹 페이지에는 연결된 코드 뒤에 종속 파일이 있습니다.

- 코드 뒤에 있습니다. *확장*

     웹 폼 클래스를 구현 하는 종속 파일입니다. 코드 뒤에 언어는이 파일의 *확장을* 결정합니다.

- 콘텐츠 페이지.aspx

     웹 페이지의 시작 내용을 콘텐츠 페이지로 합니다. 이 웹 페이지에는 연결된 코드 뒤에 종속 파일이 없습니다.

- ContentPage_cb.aspx

     웹 페이지의 시작 내용을 콘텐츠 페이지로 합니다. 이 웹 페이지에는 연결된 코드 뒤에 종속 파일이 있습니다.

- 웹폼.vs템플릿

     새 웹 페이지및 해당 종속 파일의 내용을 결정하는 템플릿 파일(있는 경우)입니다.

### <a name="new-master-page"></a>새 마스터 페이지
 이 템플릿은 새 마스터 페이지 **추가** 명령에 대한 응답으로 새 마스터 페이지를 만듭니다.

 종속 코드 뒤에 소스 파일을 만들려면 **별도의 파일에 코드 배치를**선택합니다. 그렇지 않으면 빈 스크립팅 블록이 있고 종속 \<파일을 연결하는 페이지 %> 지시문이 없는 단일 웹 페이지가 만들어집니다.

- 마스터페이지.마스터

     마스터 페이지의 시작 내용입니다. 이 마스터 페이지에는 종속 파일 뒤에 연결된 코드가 없습니다.

- MasterPage_cb.마스터

     마스터 페이지의 시작 내용입니다. 이 마스터 페이지에는 연결된 코드 뒤에 종속 파일이 있습니다.

- 코드 뒤에 있습니다. *확장 프로그램*

     마스터 페이지 클래스를 구현하는 종속 파일입니다. 코드 뒤에 언어는이 파일의 *확장을* 결정합니다.

- 마스터 페이지.vs 템플릿

     새 마스터 페이지와 해당 종속 파일의 내용을 결정하는 템플릿 파일(있는 경우)입니다.

## <a name="see-also"></a>참조
- [웹 사이트 지원](../../extensibility/internals/web-site-support.md)
