---
title: 프로젝트 팩터리를 사용하여 프로젝트 인스턴스 만들기 | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project factories
- projects [Visual Studio SDK], project factories
ms.assetid: 94c90012-8669-459c-af8e-307ac242c8c4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 31ba5dd11af18f8a723b2271544eff2bd292e2e8
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80709057"
---
# <a name="create-project-instances-by-using-project-factories"></a>프로젝트 팩터리를 사용하여 프로젝트 인스턴스 생성
프로젝트 팩터리에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 형식을 사용하여 *프로젝트* 객체의 인스턴스를 작성합니다. 프로젝트 팩터리는 COCREATABLE COM 개체에 대한 표준 클래스 팩터리와 유사합니다. 그러나 프로젝트 개체는 공동으로 할 수 없습니다. 프로젝트 팩터리를 사용하여 만들 수 있습니다.

 사용자가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기존 프로젝트를 로드하거나 에서 새 프로젝트를 만들 때 IDE는 VSPackage에서 구현된 프로젝트 팩터리를 호출합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 새 프로젝트 개체는 **IDE에 솔루션 탐색기를**채울 수 있는 충분한 정보를 제공합니다. 또한 새 프로젝트 개체는 IDE에서 시작한 모든 관련 UI 작업을 지원하는 데 필요한 인터페이스를 제공합니다.

 프로젝트의 클래스에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 인터페이스를 구현할 수 있습니다. 일반적으로 자체 모듈에 있습니다.

 소유자가 집계하는 것을 지원하는 프로젝트는 프로젝트 파일에 소유자 키를 유지해야 합니다. 소유자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> 키가 있는 프로젝트에서 메서드가 호출되면 소유 된 프로젝트는 소유자 키를 프로젝트 팩터리 `CreateProject` GUID로 변환한 다음 이 프로젝트 팩터리의 메서드를 호출하여 실제 생성을 수행합니다.

## <a name="create-an-owned-project"></a>소유 프로젝트 만들기
 소유자는 다음 두 단계로 소유한 프로젝트를 만듭니다.

1. 메서드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.PreCreateForOwner%2A> 호출합니다. 이렇게 하면 소유 된 프로젝트에서 입력 제어에 `IUnknown`따라 집계 된 프로젝트 개체를 만들 수 있습니다. 소유된 프로젝트는 내부 `IUnknown` 및 집계된 개체를 소유자 프로젝트로 다시 전달합니다. 이렇게 하면 소유 된 프로젝트에 내부를 `IUnknown`저장할 수 있습니다.

2. 메서드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A> 호출합니다. 소유 된 프로젝트는 소유 하지 않은 프로젝트에 대 한 `IVsProjectFactory::CreateProject` 경우 처럼 호출 하는 대신이 메서드를 호출 하는 경우 모든 인스턴스화를 수행 합니다. 입력 `VSOWNEDPROJECTOBJECT` 열거형은 일반적으로 집계된 소유 프로젝트입니다. 소유 된 프로젝트는 이 변수를 사용하여 프로젝트 개체가 이미 만들어졌는지 (쿠키가 NULL과 같지 않음) 만들어야 하는지(쿠키는 NULL과 같음) 만들 수 있습니다.

   프로젝트 유형은 COCREATABLE COM 개체의 CLSID와 유사한 고유한 프로젝트 GUID로 식별됩니다. 일반적으로 한 프로젝트 팩터리는 하나의 프로젝트 팩터리에서 하나 이상의 프로젝트 형식 GUID를 처리할 수 있지만 단일 프로젝트 형식의 인스턴스를 만드는 것을 처리합니다.

   프로젝트 유형은 특정 파일 이름 확장명명수와 연결됩니다. 사용자가 기존 프로젝트 파일을 열려고 시도하거나 템플릿을 복제하여 새 프로젝트를 만들려고 하면 IDE는 파일의 확장자를 사용하여 해당 프로젝트 GUID를 결정합니다.

   IDE가 새 프로젝트를 만들거나 특정 유형의 기존 프로젝트를 열어야 하는지 여부를 결정하자마자 IDE는 **[HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\프로젝트]에서** 시스템 레지스트리의 정보를 사용하여 필요한 프로젝트 팩터리를 구현하는 VSPackage를 찾습니다. IDE는 이 VSPackage를 로드합니다. 메서드에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> VSPackage 메서드를 호출 하 여 IDE에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes.RegisterProjectType%2A> 프로젝트 팩터리를 등록 해야 합니다.

   `IVsProjectFactory` 인터페이스의 기본 방법은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>기존 프로젝트를 열고 새 프로젝트를 만드는 두 가지 시나리오를 처리해야 하는 것입니다. 대부분의 프로젝트는 프로젝트 파일에 프로젝트 상태를 저장합니다. 일반적으로 새 프로젝트는 메서드에 전달된 템플릿 파일의 `CreateProject` 복사본을 만든 다음 복사본을 열어 만들어집니다. 기존 프로젝트는 메서드에 전달된 프로젝트 파일을 직접 `CreateProject` 열어 인스턴스화됩니다. 메서드는 `CreateProject` 필요에 따라 사용자에게 추가 UI 기능을 표시할 수 있습니다.

   또한 프로젝트는 파일을 사용할 수 없으며 대신 해당 프로젝트 상태를 데이터베이스 또는 웹 서버와 같은 파일 시스템 이외의 저장소 메커니즘에 저장할 수 있습니다. 이 경우 메서드에 `CreateProject` 전달된 파일 이름 매개 변수는 실제로 파일 시스템 경로가 아니라 프로젝트 데이터를 식별하는 고유한 문자열인 URL입니다. 실행될 적절한 구성 순서를 트리거하기 `CreateProject` 위해 전달되는 템플릿 파일을 복사할 필요가 없습니다.

## <a name="see-also"></a>참조
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>
- [검사 목록: 새 프로젝트 유형 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)
