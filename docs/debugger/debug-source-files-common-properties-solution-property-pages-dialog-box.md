---
title: 디버그 소스 파일을 공용 속성, 솔루션 속성 페이지 대화 상자 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83bed0588a0959ab85906d949e1b0752396223ae
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62852918"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>솔루션 속성 페이지 대화 상자, 공용 속성, 소스 파일 디버그
이 속성 페이지에서는 솔루션을 디버깅할 때 디버거가 소스 파일을 찾을 위치를 지정합니다.

 **원본 파일 디버그** 속성 페이지에 액세스하려면 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다. **공용 속성** 폴더를 확장하고 **원본 파일 디버그** 페이지를 클릭합니다.

 **소스 코드를 포함 하는 디렉터리** 솔루션을 디버깅할 때 디버거가 소스 파일을 검색할 디렉터리 목록을 포함 합니다. 지정한 디렉터리의 모든 하위 디렉터리도 검색됩니다.

 **다음 소스 파일을 찾지 않음** 디버거가 읽지 않으려면 파일의 이름을 입력 합니다. 디버거가 이러한 파일 중 하나를 위에서 지정한 디렉터리 중 하나에서 찾는 경우 해당 파일을 무시합니다. 디버깅하는 동안 **소스 찾기** 대화 상자가 나타나는 경우 **취소**를 클릭하면 검색하고 있던 파일이 이 목록에 추가되어 디버거가 더 이상 해당 파일을 검색하지 않습니다.

## <a name="see-also"></a>참고 항목

- [디버거 보안](../debugger/debugger-security.md)
- [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)