---
title: "Visual Studio에서 클래스 또는 형식 생성 | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vsl.GenerateFromUsage
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 77b6feef7556950d121e462cb1e8e81e8c4bfe7f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="generate-a-class-or-type-in-visual-studio"></a>Visual Studio에서 클래스 또는 형식 생성

이 코드 생성은 다음에 적용됩니다.

- C#

- Visual Basic

**대상:** 클래스 또는 형식에 대한 코드를 즉시 생성할 수 있습니다.

**시기:** 새 클래스 또는 형식을 소개하고 자동으로 클래스 또는 형식을 제대로 선언하려고 합니다.

**이유:** 클래스 또는 형식을 사용하기 전에 사용자가 클래스 또는 형식을 선언할 수 있지만, 이 기능은 클래스 또는 형식을 자동으로 생성합니다.

## <a name="how-to"></a>방법

1. 빨간색 구부러진 곡선이 있는 줄에 커서를 놓습니다. 빨간색 구부러진 곡선은 아직 존재하지 않는 클래스를 나타냅니다.

   - C#: 

    ![강조 표시된 코드 C#](media/class-highlight-cs.png)

   - Visual Basic:

    ![강조 표시된 코드 VB](media/class-highlight-vb.png)

1. 다음 작업 중 하나를 수행합니다.

   - **키보드**
     - **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.
   - **마우스**
     - 마우스 오른쪽 단추로 클릭하고 **빠른 작업 및 리팩터링** 메뉴를 선택합니다.
     - 빨간색 구부러진 곡선 위로 마우스를 이동하고 표시되는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.
     - 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.

    ![클래스 생성 미리 보기](media/class-preview-cs.png)

1. 드롭다운 목록에서 옵션 중 하나를 선택합니다.

   - 새 파일에 클래스 '*TypeName*' 생성 &mdash;*TypeName*.cs/.vb라는 파일에 *TypeName*라는 클래스 만들기
   - 클래스 '*TypeName*' 생성 &mdash;현재 파일에 *TypeName*이라는 클래스를 만듭니다.
   - 중첩된 '*TypeName*' 클래스 생성 &mdash;현재 클래스 내에 중첩된 *TypeName*이라는 클래스를 만듭니다.
   - 새 형식 생성... &mdash;지정한 모든 속성을 사용하여 새 클래스 또는 구조체를 만듭니다.

   > [!TIP]
   > 미리 보기 창 맨 아래에 있는 **변경 내용 미리 보기** 링크를 사용하여 선택하기 전에 적용될 [모든 변경 내용을 확인](../../ide/preview-changes.md)합니다.

1. **새 형식 생성...** 항목을 선택한 경우 **형식 생성** 대화 상자가 열립니다. 새 형식의 내게 필요한 옵션, 종류 및 위치를 구성합니다.

   ![형식 생성](media/class-newtype-cs.png)

   선택 | 설명
   --- | ---
   액세스 | *기본*, *내부* 또는 *공용* 액세스 권한을 가지도록 형식을 설정합니다.
   종류 | *클래스* 또는 *구조체*로 설정할 수 있습니다.
   name | 이를 변경할 수 없으며 이미 입력한 이름이 사용됩니다.
   프로젝트 | 솔루션에 여러 프로젝트가 있는 경우 클래스/구조체를 활성화할 위치를 선택할 수 있습니다.
   파일 이름 | 새 파일을 만들거나 기존 파일에 형식을 추가할 수 있습니다.

클래스 또는 구조체가 만들어집니다. C#의 경우 생성자도 만들어집니다.

- C#

   ![클래스 생성 결과 C#](media/class-result-cs.png)

- Visual Basic

   ![클래스 생성 결과 VB](media/class-result-vb.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)