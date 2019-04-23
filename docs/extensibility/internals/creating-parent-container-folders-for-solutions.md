---
title: 솔루션에 대 한 부모 컨테이너 폴더 만들기 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- solutions, creating parent containers
- source control plug-ins, creating parent containers
ms.assetid: 961e68ed-2603-4479-a306-330eda2b2efa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6c23ec3101baac033cbef47f6f1c3ad6f717a15d
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59661063"
---
# <a name="create-parent-container-folders-for-solutions"></a>부모 솔루션에 대 한 컨테이너 폴더 만들기
원본 제어 플러그 인 API 버전 1.2에는 사용자 솔루션 내에서 모든 웹 프로젝트에 대 한 단일 루트 원본 제어 대상을 지정할 수 있습니다. 이 단일 루트를 슈퍼 통합 루트 (도메인 이름 얻기) 라고 합니다.

 원본 제어 플러그 인 API 버전 1.1에서 사용자 다중 프로젝트 솔루션을 소스 제어에 추가 하는 경우 사용자가 지정 하 라는 메시지가 각 웹 프로젝트에 대 한 하나의 원본 제어 대상.

## <a name="new-capability-flags"></a>새 기능 플래그
 `SCC_CAP_CREATESUBPROJECT`

 `SCC_CAP_GETPARENTPROJECT`

## <a name="new-functions"></a>새 함수
- [SccCreateSubProject](../../extensibility/scccreatesubproject-function.md)

- [SccGetParentProjectPath](../../extensibility/sccgetparentprojectpath-function.md)

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어에 솔루션을 추가 하는 경우 거의 항상 IDE 도메인 이름 얻기 폴더를 만듭니다. 구체적으로 다음과 같은 경우:

-   프로젝트에 웹 프로젝트를 파일 공유입니다.

-   프로젝트 및 솔루션 파일에 대 한 다양 한 드라이브가 있습니다.

-   프로젝트 및 솔루션 파일에 대 한 다른 공유 있습니다.

-   프로젝트에에서 추가 된 별도로 (소스 제어 솔루션).

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 도메인 이름 얻기 폴더의 이름을 동일 하 게 솔루션 이름과 확장명이 없는 것이 좋습니다. 다음 표에서 두 가지 버전의 동작을 보여 줍니다.

|기능|소스 제어 플러그 인 API 버전 1.1|소스 제어 플러그 인 API 버전 1.2|
|-------------| - | - |
|소스 코드 제어에 솔루션 추가|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccGetProjPath()<br /><br /> SccOpenProject()|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccCreateSubProject()<br /><br /> SccCreateSubProject()<br /><br /> SccOpenProject()|
|소스 제어 중인 솔루션에 프로젝트 추가|SccGetProjPath()<br /><br /> OpenProject()|SccGetParentProjectPath()<br /><br /> SccOpenProject()<br /><br />  **참고:**  Visual Studio 솔루션을 SUR.의 직계 자식이 있다고 가정|

## <a name="examples"></a>예제
 다음 표에서 두 가지 예제를 나열합니다. 두 경우 모두를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 될 때까지 소스 제어에서 솔루션에 대 한 대상 위치를 묻는 메시지가 합니다 *user_choice* 대상으로 지정 됩니다. user_choice를 지정 하면 솔루션 및 프로젝트가 원본 제어 대상에 대 한 사용자 프롬프트 없이 추가 됩니다.

|솔루션에 포함 된|디스크 위치에|데이터베이스 기본 구조|
|-----------------------|-----------------------|--------------------------------|
|*sln1.sln*<br /><br /> Web1<br /><br /> Web2|*C:\Solutions\sln1*<br /><br /> *C:\Inetpub\wwwroot\Web1*<br /><br /> \\\server\wwwroot$\Web2|$/<user_choice>/sln1<br /><br /> $/ < user_choice >/C/w e b 1<br /><br /> $/<user_choice>/Web2|
|*sln1.sln*<br /><br /> Web1<br /><br /> Win1|*C:\Solutions\sln1*<br /><br /> *D:\Inetpub\wwwroot\Web1*<br /><br /> *C:\solutions\sln1\Win1*|$/<user_choice>/sln1<br /><br /> $/ < user_choice >/D/w e b 1<br /><br /> $/<user_choice>/sln1/win1|

 도메인 이름 얻기 폴더 및 하위 작업의 취소 되거나 오류로 인해 실패 여부에 관계 없이 생성 됩니다. 자동으로 취소 또는 오류 조건에서 제거 되지 않습니다.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인을 반환 하지 않는 경우 버전 1.1의 동작을 기본값으로 `SCC_CAP_CREATESUBPROJECT` 고 `SCC_CAP_GETPARENTPROJECT` 기능 플래그입니다. 또한 사용자 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에 다음 키의 값을 설정 하 여 버전 1.1 동작으로 되돌릴 수 있습니다 *dword:00000001*:

 **[HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] DoNotCreateSolutionRootFolderInSourceControl** = *dword:00000001*

## <a name="see-also"></a>참고자료
- [원본 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)