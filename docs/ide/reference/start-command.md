---
title: 시작 명령
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f7488353cd4c64b0afca27060c364a1f9ddc6f8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62950431"
---
# <a name="start-command"></a>시작 명령
시작 프로젝트 디버깅을 시작합니다.

## <a name="syntax"></a>구문

```cmd
Debug.Start [address]
```

## <a name="arguments"></a>인수
 `address`

 선택 사항입니다. 소스 코드의 중단점처럼 프로그램에서 실행을 일시 중단하는 주소입니다. 이 인수는 디버그 모드에서만 유효합니다.

## <a name="remarks"></a>주의
 **시작** 명령을 실행하면 지정된 주소로 RunToCursor 작업을 수행합니다.

## <a name="example"></a>예제
 이 예제에서는 디버거를 시작하고 발생하는 모든 예외를 무시합니다.

```cmd
>Debug.Start
```

## <a name="see-also"></a>참고 항목

- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)
- [찾기/명령 상자](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)