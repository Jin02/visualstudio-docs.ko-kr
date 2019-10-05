---
title: IDE 정의 명령, 메뉴 및 그룹 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5158a9d1a06ec6f08c67777e4f1ce2e4d37220e3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315654"
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE 정의 명령, 메뉴 및 그룹
여러 메뉴, 명령 및 명령 그룹에서 사용 하기 위해 이미 정의 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. 확장 하는 경우이 명령은 사용 가능한도 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.

## <a name="finding-environment-defined-commands"></a>환경 정의 명령 찾기
 환경 명령 4 개.vsct 파일 집합이 정의 됩니다.

- SharedCmdDef.vsct

- SharedCmdPlace.vsct

- ShellCmdDef.vsct

- ShellCmdPlace.vsct

  이러한 파일이  *\<Visual Studio SDK 설치 경로 >* \VisualStudioIntegration\Common\Inc\\합니다. 이러한 파일의 정의와 메뉴 및 메뉴, 그룹 및 명령을 컨테이너로 VSPackage의 명령 테이블 (.vsct) 구성 파일에서 사용할 수 있는 그룹의 Guid를 제공 합니다.

## <a name="in-this-section"></a>섹션 내용
- [Visual Studio 메뉴의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

 Visual Studio 메뉴 모음에서 메뉴 및 포함 된 그룹의 GUID 및 ID 값을 제공 합니다.

- [Visual Studio 도구 모음의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)

 Visual Studio IDE에서 도구 모음 및 포함 된 그룹의 GUID 및 ID 값을 제공 합니다.

- [Visual Studio 명령의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)

 Visual Studio IDE에 의해 정의 되는 명령의 GUID 및 ID 값을 제공 합니다.

## <a name="see-also"></a>참고 항목
- [Visual Studio 명령 테이블(.Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [프로젝트 시스템 확장을 위한 IDE 정의 명령](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
- [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)