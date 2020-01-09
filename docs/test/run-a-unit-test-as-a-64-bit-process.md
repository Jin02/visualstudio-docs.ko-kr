---
title: 단위 테스트를 64비트 프로세스로 실행
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 67a614ed164b12070fe40f24cdba09a3051e36a5
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75566256"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>단위 테스트를 64비트 프로세스로 실행

64비트 컴퓨터를 사용하는 경우에는 단위 테스트를 실행하고 코드 검사 정보를 64비트 프로세스로 캡처할 수 있습니다.

## <a name="to-run-a-unit-test-as-a-64-bit-process"></a>단위 테스트를 64비트 프로세스로 실행하려면

1. 코드 또는 테스트를 32비트/x86으로 컴파일했지만 64비트 프로세스로 실행하려면 **모든 CPU** 또는 원한다면 **64비트**로 다시 컴파일합니다.

    > [!TIP]
    > 유연성을 극대화하려면 **Any CPU** 구성으로 테스트 프로젝트를 컴파일합니다. 그러면 32비트 및 64비트 에이전트 모두에서 테스트를 실행할 수 있습니다. **64비트** 구성으로 테스트 프로젝트를 컴파일하는 것은 아무 이점이 없습니다.

2. Visual Studio 메뉴에서 **테스트**, **설정**, **프로세서 아키텍처**를 차례로 선택합니다. **x64**를 선택해서 테스트를 64비트 프로세스로 실행합니다.

   - 또는

   *.runsettings* 파일에서 `<TargetPlatform>x64</TargetPlatform>`을 지정합니다. 이 메서드의 장점은 서로 다른 파일에서 설정 그룹을 지정하고 각 설정 간에 빠르게 전환할 수 있다는 점입니다. 또한 솔루션 간에 설정을 복사할 수도 있습니다. 자세한 내용은 [.runsettings 파일을 사용하여 단위 테스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)을 참조하세요.

## <a name="see-also"></a>참조

- [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)
- [코드 단위 테스트](../test/unit-test-your-code.md)
