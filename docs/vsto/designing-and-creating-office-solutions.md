---
title: Office 솔루션을 만들고 디자인
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], creating
- Office development in Visual Studio, creating solutions
- solutions [Office development in Visual Studio], creating
- Office project types in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6ea209b380948196ee20cc4e2085fa46fab76efc
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441839"
---
# <a name="design-and-create-office-solutions"></a>Office 솔루션을 만들고 디자인

Visual Studio에서는 몇 가지 유형의 Office 솔루션을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. 설명서의 이 섹션에서는 프로젝트 템플릿에 대해 설명하고 Office 프로젝트를 만드는 지침을 제공합니다. 프로젝트를 만든 후 코드 및 사용자 인터페이스 사용자 지정을 구현 하는 방법에 대 한 정보를 참조 하세요 [개발 Office 솔루션](../vsto/developing-office-solutions.md)합니다.

[!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

> [!NOTE]
> Office 환경을 확장 하는 솔루션을 개발 하는 데 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 새 확인해 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능의 VSTO 추가 기능 및 솔루션에 비해 작은 사용 공간이 있고 거의 모든 웹 프로그래밍 기술을, HTML5, JavaScript, CSS3, XML 등을 사용 하 여 빌드할 수 있습니다.

## <a name="create-office-projects"></a>Office 프로젝트 만들기
 시작하기 전에 요구 사항을 결정하고 가장 적합한 기능을 제공하는 솔루션의 유형을 찾아야 합니다. 예를 들어 Office 솔루션이 응용 프로그램을 사용할 때마다 실행되어야 하는 경우 VSTO 추가 기능이 요구 사항에 가장 적합합니다. 코드가 단일 문서와 긴밀하게 통합된 경우 문서 수준 사용자 지정을 만듭니다. 이러한 프로젝트 형식은 Visual Studio 프로젝트 템플릿으로 사용할 수 있습니다. Visual Studio를 사용 하 여 포함 된 Office 프로젝트 템플릿에 대 한 자세한 내용은 참조 하세요. [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)합니다. Office 프로젝트를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.

 Office 프로젝트에는 Visual Studio의 기타 프로젝트 형식과 다른 기능과 프로젝트 항목이 있습니다. 예를 들어 문서 수준 프로젝트를 만들 때 프로젝트의 문서나 통합 문서는 Visual Studio 내에서 열고 편집할 수 있습니다. 자세한 내용은 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)합니다.

## <a name="choose-a-net-framework-version"></a>.NET Framework 버전을 선택 합니다.
 요구 사항에 가장 적합한 프로젝트 형식을 선택한 후 개발 프로세스에서 사용할 .NET Framework의 버전을 선택할 수 있습니다. Office 프로젝트에서는 다음과 같은 .NET Framework 버전을 대상으로 지정할 수 있습니다.

- [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]

- [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]

- [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]

  프로젝트에 대해 선택한.NET Framework 버전을 실행 하 여 솔루션에 대 한 최종 사용자 컴퓨터에 필요 합니다. 예를 들어 경우 프로젝트의 대상이 합니다 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 최종 사용자 컴퓨터에 필요 합니다. 이 예제에서는.NET Framework 3.5가 최종 사용자 컴퓨터에 설치 된 경우 솔루션이 실행 되지 않습니다.

  .NET Framework 3.5를 대상으로 하는 VSTO 추가 기능 프로젝트를 마이그레이션하는 경우 Visual Studio에서는 설치한 Office 버전에 따라 프로젝트의 대상 프레임워크를 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경합니다.

  그러나 Visual Studio에서 대상 프레임워크를 변경한 후 특정 기능을 사용하는 프로젝트의 일부 코드를 수정해야 할 수 있습니다. 대상 프레임 워크를 변경 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요. 프로젝트에서 필요할 수 있는 변경 내용에 대 한 자세한 정보를 참조 하세요. [.NET Framework 4 이상으로 마이그레이션 Office 솔루션](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)합니다.

  Visual Studio 프로젝트의 대상.NET Framework를 변경 하 고 ClickOnce를 사용 하 여 솔루션을 배포 하는 경우 확인에.NET Framework의 해당 버전도 선택 해야 합니다 **필수 구성 요소** 대화 상자. 이 선택은 프로젝트의 대상 프레임워크를 변경할 때 자동으로 변경되지 않습니다. 자세한 내용은 [방법: Office 솔루션을 실행 하려면 최종 사용자 컴퓨터에서 필수 구성 요소 설치](https://msdn.microsoft.com/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98)합니다.

> [!NOTE]
> [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]을 사용하여 만드는 Office 프로젝트에서 .NET Framework 3.5 또는 이전 버전을 대상으로 지정할 수 없습니다. [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]을 사용하여 만드는 Office 프로젝트에는 [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]에서 처음 도입된 기능이 필요합니다.

### <a name="understand-when-the-office-pias-are-required-on-end-user-computers"></a>Office Pia가 최종 사용자 컴퓨터에서 필요한 경우 이해
 기본적으로 Office Pia (주 interop 어셈블리) 않아도 최종 사용자 컴퓨터에 설치 되어야 합니다 **Interop 형식 포함** 프로젝트에서 각 Office PIA 참조의 속성이로 설정 되어 **True**, 기본 값입니다. 이 시나리오에서는 솔루션에서 사용되는 PIA 형식에 대한 형식 정보가 프로젝트를 빌드할 때 솔루션 어셈블리에 포함됩니다. 런타임 시 Office 응용 프로그램의 COM 기반 개체 모델을 호출에 포함된 된 형식 정보는 Pia 대신 사용 됩니다. 솔루션에 Pia의 형식이 포함 되는 방법에 대 한 자세한 내용은 참조 하세요. [형식 동등성 및 포함 된 interop 형식](/dotnet/framework/interop/type-equivalence-and-embedded-interop-types)합니다.

 경우는 **Interop 형식 포함** 프로젝트에서 각 Office PIA 참조의 속성이로 설정 되어 **False**, Office Pia를 설치 하 고 각 최종 사용자 컴퓨터에서 전역 어셈블리 캐시에 등록 해야 하는 솔루션을 실행 합니다. 대부분의 경우 PIA는 Office와 함께 기본적으로 설치되지만 PIA 재배포 가능 파일을 솔루션에 대한 필수 구성 요소로 포함할 수도 있습니다. 자세한 내용은 [Office 솔루션 배포 필수 조건](https://msdn.microsoft.com/9f672809-43a3-40a1-9057-397ce3b5126e)합니다.

### <a name="understand-the-client-profile"></a>Client profile 이해
 .NET Framework Client Profile은 전체 .NET Framework의 하위 집합입니다. .NET Framework의 클라이언트 기능만 사용해야 하고 Office 솔루션에 대한 가장 빠른 배포 환경을 제공하려는 경우 .NET Framework Client Profile을 대상으로 지정할 수 있습니다. 자세한 내용은 [.NET Framework 클라이언트 프로필](/dotnet/framework/deployment/client-profile)합니다.

 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]를 대상으로 하는 Office 프로젝트를 만들 때 기본적으로 [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]가 대상으로 지정됩니다. 전체 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]에 대해 개발하려는 경우 프로젝트가 만들어진 후 이 옵션을 설정해야 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.

## <a name="create-solutions-for-the-64-bit-edition-of-microsoft-office"></a>64 비트 버전의 Microsoft Office 솔루션 만들기
 Microsoft Office는 64비트 및 32비트 버전에서 사용할 수 있습니다. 두 버전 중 하나에서 실행할 수 있는 Office 솔루션을 만들려면 프로젝트에 대 한 플랫폼 대상 설정을로 설정 해야 합니다 **Any CPU**합니다. 이 값은 Office 프로젝트에 대한 기본값입니다. 자세한 내용은 [빌드 Office 솔루션](../vsto/building-office-solutions.md)합니다.

 64비트 및 32비트 버전의 Microsoft Office에서 사용되는 64비트 및 32비트 버전의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]이 별도로 있습니다. 자세한 내용은 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)합니다.

## <a name="assemblies-in-office-solutions"></a>Office 솔루션의 어셈블리
 Visual Studio에서 Office 개발 도구를 사용하여 Office 프로젝트를 만들 때 작성하는 코드는 결국 어셈블리로 컴파일됩니다. 어셈블리는 공유 서버 또는 클라이언트 컴퓨터의 디렉터리에 배포 됩니다.

 Office 솔루션의 어셈블리는 Office 응용 프로그램에서 로드됩니다. 어셈블리가 로드된 후 어셈블리의 코드는 응용 프로그램에서 발생하는 이벤트(예: 사용자가 메뉴 항목을 클릭할 때)에 응답할 수 있습니다. 어셈블리의 코드는 응용 프로그램을 자동화하고 확장하기 위해 개체 모델을 호출할 수도 있으며 [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)]의 클래스 중 하나를 사용할 수 있습니다. 자세한 내용은 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md) 하 고 [Architecture of VSTO add-ins](../vsto/architecture-of-vsto-add-ins.md)합니다.

 Office 솔루션은 배포 매니페스트와 응용 프로그램 매니페스트를 사용하여 어셈블리를 식별합니다. 매니페스트에는 응용 프로그램이 올바른 어셈블리를 찾고 연결하고 실행할 수 있도록 어셈블리의 이름, 버전 및 위치에 대한 정보가 포함되어 있습니다. 자세한 내용은 [Office 솔루션에서 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)합니다.

 문서 수준 프로젝트에는 어셈블리 외에도 문서가 포함되어 있습니다. 문서는 응용 프로그램의 프런트 엔드로 작동하며 모든 사용자 조작이 이뤄지는 곳입니다. 각 문서에는 연결된 주 프로젝트 어셈블리가 하나만 있을 수 있지만 여러 문서가 동일한 어셈블리를 가리킬 수 있습니다.

 문서 수준 프로젝트의 어셈블리는 문서에 포함되지 않고 대신 다른 곳에 저장되며 문서의 응용 프로그램 매니페스트에 의해 식별됩니다.

## <a name="security-considerations-for-assemblies"></a>어셈블리에 대 한 보안 고려 사항
 Office 솔루션이 컴퓨터에서 실행되려면 솔루션에서 사용되는 어셈블리를 실행하도록 신뢰할 수 있어야 합니다. 보안에 대 한 자세한 내용은 참조 하세요. [Secure Office 솔루션](../vsto/securing-office-solutions.md)합니다.

 기본적으로 솔루션 어셈블리와 프로젝트의 출력 폴더에 있는 모든 참조된 어셈블리는 프로젝트를 빌드할 때 개발 컴퓨터에서 실행하도록 신뢰할 수 있어야 합니다. 자세한 내용은 [빌드 Office 솔루션](../vsto/building-office-solutions.md)합니다.

 보안상의 이유로 프로젝트를 공유 위치에서 개발하는 것보다는 로컬 컴퓨터에서 만드는 것이 가장 좋습니다. 자세한 내용은 [Office 솔루션 공동 개발](../vsto/collaborative-development-of-office-solutions.md)합니다.

## <a name="referenced-assemblies"></a>참조된 어셈블리
 어셈블리는 프로젝트의 참조에 나열된 다른 어셈블리를 참조할 수 있습니다. 그러나 하나의 문서 수준 프로젝트 어셈블리가 다른 문서 수준 프로젝트 어셈블리를 참조할 수 없습니다.

## <a name="see-also"></a>참고자료
- [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)
- [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Visual Studio 환경의 office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)
- [Office 프로젝트의 속성](../vsto/properties-in-office-projects.md)
- [다른 버전의 Microsoft Office에서 솔루션을 실행 합니다.](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)
- [방법: 주 interop 어셈블리를 통해 대상 Office 응용 프로그램](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [Office 솔루션에서 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)
- [방법: Office 솔루션에 대 한 구성 정보 설정](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md)
- [Visual Studio 내에서 Office 기능 사용](../vsto/using-office-functionality-inside-of-visual-studio.md)
- [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)
- [Office 프로그래밍의 일반적인 작업](../vsto/common-tasks-in-office-programming.md)
- [Office 솔루션 개발](../vsto/developing-office-solutions.md)
- [Visual Studio에서 Office 솔루션의 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)
