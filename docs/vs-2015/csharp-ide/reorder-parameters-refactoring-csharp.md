---
title: 매개 변수 리팩터링 다시C#정렬 () | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
helpviewer_keywords:
- refactoring [C#], Reorder Parameters
- Reorder Parameters refactoring [C#]
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e39564fb108b63859620e2c4a650608cdf1e7e82
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72673142"
---
# <a name="reorder-parameters-refactoring-c"></a>매개 변수 리팩터링 다시 정렬(C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Reorder Parameters`는 메서드, C# 인덱서 및 대리자에 대 한 매개 변수의 순서를 변경 하는 쉬운 방법을 제공 하는 시각적 리팩터링 작업입니다. `Reorder Parameters` 선언을 변경 하 고 멤버가 호출 되는 위치에서 새 순서를 반영 하도록 매개 변수를 다시 정렬 합니다.

 @No__t_0 작업을 수행 하려면 커서를 메서드, 인덱서 또는 대리자의 앞 이나 뒤에 배치 합니다. 커서가 위치에 있는 경우 바로 가기 키를 누르거나 바로 가기 메뉴에서 명령을 클릭 하 여 `Reorder Parameters` 작업을 호출 합니다.

> [!NOTE]
> 확장 메서드의 첫 번째 매개 변수를 다시 정렬할 수 없습니다.

### <a name="to-reorder-parameters"></a>매개 변수를 다시 정렬 하려면

1. @No__t_0 이라는 클래스 라이브러리를 만든 후 `Class1`를 다음 예제 코드로 바꿉니다.

    ```csharp
    class ProtoClassA
    {
        // Invoke on 'MethodB'.
        public void MethodB(int i, bool b) { }
    }

    class ProtoClassC
    {
        void D()
        {
            ProtoClassA MyClassA = new ProtoClassA();

            // Invoke on 'MethodB'.
            MyClassA.MethodB(0, false);
        }
    }
    ```

2. 메서드 선언 또는 메서드 호출에서 `MethodB`에 커서를 놓습니다.

3. **리팩터링** 메뉴에서 **매개 변수 다시 정렬**을 클릭 합니다.

     **매개 변수 다시 정렬** 대화 상자가 나타납니다.

4. **매개 변수 다시 정렬** 대화 상자의 **매개 변수** 목록에서 `int i`을 선택 하 고 아래로 단추를 클릭 합니다.

     또는 **매개 변수** 목록에서 `bool b` 후 `int i`를 끌 수 있습니다.

5. **매개 변수 다시 정렬** 대화 상자에서 **확인**을 클릭 합니다.

     **매개 변수 다시 정렬** 대화 상자에서 **참조 변경 내용 미리 보기** 옵션을 선택 하면 **변경 내용 미리 보기-매개 변수 다시 정렬** 대화 상자가 표시 됩니다. 이 파일은 시그니처와 메서드 호출의 `MethodB`에 대 한 매개 변수 목록의 변경 내용에 대 한 미리 보기를 제공 합니다.

    1. **변경 내용 미리 보기-매개 변수 다시 정렬** 대화 상자가 나타나면 **적용**을 클릭 합니다.

         이 예제에서는 메서드 선언과 `MethodB`에 대 한 모든 메서드 호출 사이트가 업데이트 됩니다.

## <a name="remarks"></a>주의
 메서드 선언 또는 메서드 호출에서 매개 변수 순서를 변경할 수 있습니다. 커서를 메서드 또는 대리자 선언 옆에 배치 하 고 본문에서는 배치 하지 않습니다.

## <a name="see-also"></a>관련 항목:
 [리팩터링(C#)](../csharp-ide/refactoring-csharp.md)