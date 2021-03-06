---
title: 모호성 해결 대화 상자 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.Disambig
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4257fd213d6401de381e25c74c126b8468b76057
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72729835"
---
# <a name="resolve-ambiguity-dialog-box"></a>모호성 해결 대화 상자
`Resolve Ambiguity` 대화 상자는 디버거에서 표시할 위치를 선택할 수 없을 때 표시됩니다. 예를 들어 C++ 템플릿을 사용하는 경우 단일 함수 템플릿을 사용하여 여러 함수를 만들 수 있습니다. 디버거가 템플릿의 소스 위치에서 중지되고 사용자가 `Go To Disassembly`을 선택하면 디버거에 여러 선택 사항이 주어집니다. 템플릿을 사용하여 만든 각 함수에는 고유한 디스어셈블리 코드가 있으므로 디버거는 사용자가 보려는 코드가 어떤 것인지 모릅니다. `Resolve Ambiguity` 대화 상자를 사용하면 해당하는 모든 위치의 목록에서 원하는 위치를 선택할 수 있습니다.

 `Choose the specific location` 명령에 해당하는 모든 위치를 나열합니다.

 `Address` 각 함수의 메모리 주소를 표시합니다.

 `Function` 각 함수의 이름을 표시합니다.

 `Module` 함수의 개체 코드가 포함된 모듈(EXE 또는 DLL)을 표시합니다.

## <a name="see-also"></a>참조
- [디버거의 식](../debugger/expressions-in-the-debugger.md)