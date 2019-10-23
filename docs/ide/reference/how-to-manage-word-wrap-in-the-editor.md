---
title: 단어 줄 바꿈
ms.date: 11/07/2018
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- editors, text viewing
- Code Editor, word wrap
ms.assetid: 442f33ef-9f52-4515-b55f-fb816d664645
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 30bfe549100a06df6b9a8163cad1e3d519c3a91b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663115"
---
# <a name="how-to-manage-word-wrap-in-the-editor"></a>방법: 편집기에서 자동 줄 바꿈 관리

**자동 줄 바꿈** 옵션을 설정 및 선택 취소할 수 있습니다. 이 옵션을 설정하면 코드 편집기 창의 현재 너비를 벗어나는 긴 줄의 해당 부분이 다음 줄에 표시됩니다. 예를 들어 줄 번호 매기기를 쉽게 사용하기 위해 이 옵션의 선택을 취소한 경우에는 오른쪽으로 스크롤하여 긴 줄의 끝을 확인할 수 있습니다.

> [!NOTE]
> 이 토픽은 Windows에서 Visual Studio에만 적용됩니다. Mac용 Visual Studio는 현재 자동 줄 바꿈을 지원하지 않습니다.

## <a name="to-set-word-wrap-preferences"></a>자동 줄 바꿈 기본 설정을 설정하려면

1. **도구** 메뉴에서 **옵션**을 선택합니다.

2. **텍스트 편집기** 폴더의 **모든 언어** 하위 폴더에서 **일반** 옵션을 선택하여 이 옵션을 전역으로 설정합니다.

     — 또는 —

     프로그래밍 중인 언어에 대한 하위 폴더에서 **일반** 옵션을 선택합니다.

3. **설정**에서 **자동 줄 바꿈 옵션**을 선택 또는 선택 취소합니다.

     **자동 줄 바꿈** 옵션을 선택하면 **자동 줄 바꿈 시각 문자 표시** 옵션을 사용할 수 있습니다.

4. 긴 줄이 두 번째 줄로 줄 바꿈되는 위치에 줄 바꿈 화살표 표시기를 표시하려면 **자동 줄 바꿈 시각 문자 표시** 옵션을 선택합니다. 표시기 화살표를 표시하지 않으려면 이 옵션의 선택을 취소합니다.

    > [!NOTE]
    > 이러한 미리 알림 화살표는 코드에 추가되지 않고 표시용으로만 사용됩니다.

## <a name="known-issues"></a>알려진 문제

Notepad++, Sublime Text 또는 Visual Studio Code에서 자동 줄 바꿈에 익숙한 경우 Visual Studio가 다른 편집기에 대해 다르게 동작하는 다음 문제에 유의하세요.

* [세 번 클릭해도 전체 줄을 선택하지 않습니다.](https://developercommunity.visualstudio.com/content/problem/268989/triple-click-doesnt-select-whole-line-when-word-wr.html)
* [Cut 명령이 전체 줄을 삭제하지 않습니다.](https://developercommunity.visualstudio.com/content/problem/138259/cut-command-should-delete-logical-line.html)
* [End 키를 두 번 눌러서 커서를 줄 끝으로 이동하지 않습니다.](https://developercommunity.visualstudio.com/content/problem/138274/pressing-end-key-twice-should-move-cursor-to-end-o.html)

## <a name="see-also"></a>참고 항목

- [코드 편집기의 기능](../../ide/writing-code-in-the-code-and-text-editor.md)
