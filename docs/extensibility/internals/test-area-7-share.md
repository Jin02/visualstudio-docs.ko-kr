---
title: '시험 영역 7: 공유 | 마이크로 소프트 문서'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], sharing items
- source control plug-ins, sharing items
ms.assetid: 6ec4780a-bda4-4327-bb3e-c6c9e7eabf35
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fd4c48e94015d95f5e56d465cdbf98562108d3b3
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80704401"
---
# <a name="test-area-7-share"></a>테스트 영역 7: 공유
이 테스트 영역에서는 **공유** 명령을 통해 위치 간에 항목 공유를 다룹니다.

 hhare 작업은 소스 제어 파일 계층 구조 내에서 두 개 이상의 위치 간에 파일 및 폴더 항목의 명백한 중복입니다. 서버에서는 중복이 실제로 발생하지 않지만 사용자는 두 개 이상의 지정된 위치에서 동일한 파일을 볼 수 있습니다. 공유 항목이 변경될 때마다 해당 변경 사항은 다른 모든 공유 위치에 표시됩니다.

 폴더에 공유하는 것은 소스 제어하에 하나 이상의 파일이 있는 폴더를 선택하는 경우에 작동합니다. 공유 명령은 다음 조건에서 비활성화됩니다.

- 선택한 폴더가 빈 폴더인 경우.

- 실제 폴더가 있지만 소스 제어 파일이 없는 경우.

- 가상 폴더가 있는 경우 소스 제어 하에 있는 파일이 폴더에 있는지 여부입니다.

- 원격 사이트 웹 프로젝트가 있는 경우

## <a name="command-menu-access"></a>명령 메뉴 액세스
 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 개발 환경 메뉴 경로는 테스트 사례에 사용됩니다.

 공유: **파일**->**소스 제어**->**공유**.

## <a name="expected-behavior"></a>예상되는 동작

- 공유 파일이 공유 위치에 나타납니다.

- 소스 제어 버전 저장소 기록을 보면 파일이 공유된다는 것을 볼 수 있습니다.

- 공유 파일을 편집하여 파일의 두 위치를 모두 편집합니다.

## <a name="test-cases"></a>테스트 사례
 다음은 공유 테스트 영역에 대한 특정 테스트 사례입니다.

|작업|테스트 단계|확인할 예상 결과|
|------------|----------------|--------------------------------|
|소스 제어하에 로드된 한 프로젝트에서 다른 로드된 프로젝트로 파일 공유|1. 새 프로젝트를 만듭니다.<br />2. 솔루션에 두 번째 프로젝트를 추가합니다.<br />3. 첫 번째 프로젝트에 없는 이름으로 두 번째 프로젝트에서 파일을 만듭니다.<br />4. 소스 제어에 솔루션을 추가합니다.<br />5. 첫 번째 프로젝트를 선택합니다.<br />6. **공유** 대화 상자 열기(파일**File** -> **소스 제어** -> **공유).**<br />7. 두 번째 프로젝트에서 첫 번째 프로젝트로 파일을 공유합니다.<br />8. 메시지가 표시되면 **체크 아웃을** 수락합니다.|일반적인 예상 동작입니다.|
|한 프로젝트에서 다른 프로젝트로 파일 공유|1. 새 프로젝트를 만듭니다.<br />2. 소스 제어에 추가합니다.<br />3. 용액을 닫습니다.<br />4. 두 번째 프로젝트 만들기(새 솔루션)<br />5. 소스 제어에 솔루션을 추가합니다.<br />6. 프로젝트를 선택합니다.<br />7. **공유** 대화 상자(파일**File** -> **소스 제어** -> **공유)를**엽니다.<br />8. 이전에 추가된 프로젝트의 파일을 열린 프로젝트에 공유합니다.<br />9. 메시지가 표시되면 **체크 아웃을** 수락합니다.|일반적인 예상 동작입니다.|
|소스 제어에서 현재 로드된 프로젝트로 프로젝트의 일부가 아닌 파일 공유|1. 새 프로젝트를 만듭니다.<br />2. 소스 제어에 솔루션을 추가합니다.<br />3. 프로젝트 또는 솔루션의 일부가 아닌 소스 컨트롤에 파일을 추가합니다.<br />4. 프로젝트를 선택하고 **공유** 대화 상자(파일**File** -> **소스 제어** -> **공유)를**엽니다.<br />5. 현재 프로젝트 또는 솔루션 내에 존재하지 않는 **공유** 대화 상자 내에서 파일을 선택하고 공유합니다.<br />6. 메시지가 표시되면 **체크 아웃을** 수락합니다.|소스 제어 저장소에서 Get을 수행했기 때문에 이제 파일이 프로젝트의 로컬 위치에 있습니다.|
|동일한 프로젝트 내의 파일을 다른 폴더에 공유|1. **도구** -> **옵션** -> **소스 제어에서**자동으로 체크 **아웃을** 선택합니다.<br />2. 새 프로젝트를 만들고 소스 제어에 추가합니다.<br />3. 프로젝트에 폴더를 추가합니다.<br />4. 폴더에 파일을 추가하고 폴더를 체크 인합니다.<br />5. 폴더를 선택합니다.<br />6. **공유** 대화 상자 열기(파일**File** -> **소스 제어** -> **공유).**<br />7. 선택한 폴더에 파일을 공유합니다.|일반적인 예상 동작입니다.<br /><br /> 폴더를 공유에 사용하려면 먼저 폴더에 있는 파일로 체크 인해야 합니다.|
|로드된 프로젝트에 폴더 공유 — 재귀|1. 새 프로젝트를 만듭니다.<br />2. 소스 제어에 솔루션을 추가합니다.<br />3. 프로젝트를 선택합니다.<br />4. **공유** 대화 상자(파일**File** -> **소스 제어** -> **공유)를**엽니다.<br />5. 폴더를 선택합니다.<br />6. 폴더를 프로젝트에 재귀적으로 공유합니다.|일반적인 예상 동작입니다.|
|한 프로젝트에서 다른 프로젝트로 여러 파일 공유|1. 여러 파일이 있는 새 프로젝트를 만듭니다.<br />2. 소스 제어에 솔루션을 추가합니다.<br />3. 용액을 닫습니다.<br />4. 새 솔루션에서 새 프로젝트를 만듭니다.<br />5. 소스 제어에 솔루션을 추가합니다.<br />6. 프로젝트를 선택합니다.<br />7. **공유** 대화 상자(파일**File** -> **소스 제어** -> **공유)를**엽니다.<br />8. 이전에 만든 프로젝트에서 현재 열려 있는 프로젝트에 여러 파일을 공유합니다.|일반적인 예상 동작입니다.|

## <a name="see-also"></a>참조
- [소스 제어 플러그 인에 대한 테스트 가이드](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
