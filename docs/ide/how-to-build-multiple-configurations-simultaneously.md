---
title: '방법: 여러 구성 동시 빌드'
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ac8d27397c6e4748546e21baf84abd7578ce8762
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547803"
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>방법: 여러 구성 동시 빌드

**일괄 빌드** 대화 상자를 통해 여러 빌드 구성 또는 모든 빌드 구성을 동시에 사용하여 대부분의 프로젝트 형식을 빌드할 수 있습니다. 그러나 다음과 같은 유형의 프로젝트는 여러 빌드 구성에서 동시에 빌드할 수 없습니다.

1. JavaScript를 사용하여 빌드된 Windows용 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱

2. 모든 Visual Basic 프로젝트

   빌드 구성에 대한 자세한 내용은 [빌드 구성 이해](../ide/understanding-build-configurations.md)를 참조하세요.

## <a name="to-build-a-project-in-multiple-build-configurations"></a>여러 빌드 구성에서 프로젝트를 빌드하려면

1. 메뉴 모음에서 **빌드** > **일괄 빌드**를 선택합니다.

2. **빌드** 열에서 프로젝트를 빌드할 구성에 대한 확인란을 선택합니다.

    > [!TIP]
    > 솔루션에 대한 빌드 구성을 만들거나 편집하려면 메뉴 모음에서 **빌드** > **Configuration Manager**를 선택하여 **Configuration Manager** 대화 상자를 엽니다. 솔루션에 대한 빌드 구성을 편집한 후 **일괄 빌드** 대화 상자에서 **다시 빌드** 단추를 클릭하여 솔루션의 프로젝트에 대한 모든 빌드 구성을 업데이트할 수 있습니다.

3. **빌드** 또는 **다시 빌드** 단추를 선택하여 지정한 구성으로 프로젝트를 빌드합니다.

## <a name="see-also"></a>참고 항목

- [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)
- [빌드 구성 이해](../ide/understanding-build-configurations.md)
- [병렬로 여러 프로젝트 빌드](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)