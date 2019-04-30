---
title: 명령 배치 지침 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0c04ea981fc190b2e0074e767e086303e6950f2a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861665"
---
# <a name="command-placement-guidelines"></a>명령 배치 지침
Visual Studio 통합된 개발 환경 (IDE)에 명령을 배치에 대 한 모범 사례는 명령 집합의 크기에 따라 달라 집니다. 명령을 정의 하 고 정보에 따라 배치 *.vsct* 파일입니다.

## <a name="best-practices-for-all-command-sets"></a>모든 명령 집합에 대 한 모범 사례
 모든 명령 집합에 대 한 다음이 지침을 따르세요.

- 차트 명령 구조를 미리 준비 합니다. 명령, 콤보 상자, 명령 그룹 및 둘 이상의 위치에 사용할 바로 가기 메뉴를 식별 합니다.

- 동일한 그룹에 표시 되는 명령 관련 되어야 합니다.

- 하나의 명령만 포함 하는 그룹 허용 됩니다.

- 패키지를 기존 Visual Studio 메뉴 명령 많은 추가 해야 합니다. 대신, 메뉴 또는 하위 메뉴를 호스트할 새 명령을 만들 해야 있습니다.

- 경우 기존 명령을 사용 하 여 혼동 하지는 및 용도 분명히 알 수 있도록 기존 메뉴, 명령 이름에 명령을 배치 합니다.

## <a name="best-practices-for-small-command-sets"></a>작은 명령 집합에 대 한 모범 사례
 몇 가지 명령에 포함 된 VSPackage를 개발 하는 경우 또한 이러한 지침을 따릅니다.

- 사용 가능한 경우는 [부모](../../extensibility/parent-element.md) 명령, 콤보 상자, 그룹 또는 자식 메뉴 적절 한 그룹에 삽입할 요소입니다.

- 표시는 VSPackage에서 메뉴에 이러한 그룹을 할당 합니다.

- 부모 또는 자식 메뉴 명령 이어야 합니다는 [그룹](../../extensibility/group-element.md) 요소입니다. 그룹에 명령 및 하위 메뉴를 할당 하 고 부모 메뉴에 그룹을 할당 합니다.

- 추가 하 여 추가 그룹에 명령을 넣을 수 있습니다는 [CommandPlacements](../../extensibility/commandplacements-element.md) 요소 섹션 정의 후 명령 및 다음을 추가 합니다 `CommandPlacements` 요소를 [CommandPlacement](../../extensibility/commandplacement-element.md) 요소 각 추가 그룹입니다.

## <a name="best-practices-for-large-command-sets"></a>많은 명령 집합에 대 한 모범 사례
 VSPackage는 여러 컨텍스트에서 표시 되는 많은 명령에 있으면 또한 이러한 지침을 따릅니다.

- 메뉴, 그룹 및 자체 부모로 지정 하는 명령을 확인 합니다. 즉, 할당 하지 마십시오는 `Parent` 항목 정의의 요소입니다.

- 사용 하 여 `CommandPlacement` 의 요소 항목을 `CommandPlacements` 메뉴, 그룹 및 명령을 해당 부모 메뉴 및 그룹에 삽입할 요소 섹션입니다.

- 에 `CommandPlacements` 요소 섹션을 지정 된 메뉴 또는 그룹을 채우는 항목을 서로 인접 한 이어야 합니다. 이 쉬워지며는 `Priority` 순위 쉽게 확인할 수 있습니다.

## <a name="see-also"></a>참고자료
- [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Visual Studio 명령 테이블 (.vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)