---
title: 예외 후 실행 계속 Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7be214a950c8cc93d986f97834a848bd9ab824e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745653"
---
# <a name="continuing-execution-after-an-exception"></a>예외 후 실행 계속
예외로 인해 디버거가 실행을 중단 하면 기본적으로 **예외 도우미가**표시 됩니다. **옵션** 대화 상자에서 **예외 도우미** 를 사용 하지 않도록 설정한 **경우 예외 도우미 (** C# 또는 Visual Basic) 또는 **예외** 대화 상자 (C++)가 표시 됩니다.

 **예외 도우미가** 표시 되 면 예외를 발생 시킨 문제를 해결할 수 있습니다.

## <a name="managed-and-native-code"></a>관리 코드 및 네이티브 코드
 관리 코드와 네이티브 코드에서는 처리 되지 않은 예외가 발생 한 후 같은 스레드에서 실행을 계속할 수 있습니다. **예외 도우미** 는 예외가 throw 된 지점까지 호출 스택을 해제 합니다.

## <a name="mixed-code"></a>혼합 코드
 네이티브 및 관리 코드가 혼합된 코드를 디버깅하는 동안 처리되지 않은 예외가 발생하면 운영 체제 제한에 따라 호출 스택을 해제할 수 없습니다. 바로 가기 메뉴를 사용하여 호출 스택을 해제하려고 하면 혼합 코드 디버깅 중에 처리되지 않은 예외가 발생하면 디버거가 호출 스택을 해제할 수 없다는 내용의 오류 메시지가 나타납니다.

## <a name="see-also"></a>참조

- [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)