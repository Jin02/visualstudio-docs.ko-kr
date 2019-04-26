---
title: '10단계: 추가 단추 및 확인란에 대한 코드 작성'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a397646823d133b66e66bb2bb5d10c2ae358ae53
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430875"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>10단계: 추가 단추 및 확인란에 대한 코드 작성
이제 다른 네 메서드를 완료할 준비가 되었습니다. 지금 이 코드를 복사하여 붙여넣을 수도 있지만 이 자습서의 내용을 최대한 학습하려면 이 코드를 입력하고 IntelliSense를 사용합니다.

 이 코드는 앞서 추가한 단추에 기능을 추가합니다. 이 코드가 없으면 단추로 어떤 작업도 수행되지 않습니다. 단추에서는 <xref:System.Windows.Forms.Control.Click> 이벤트의 코드를 사용하고 확인란에서는 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트를 사용하여 컨트롤을 활성화했을 때 서로 다른 작업을 수행합니다. 예를 들어 **그림 지우기** 단추를 선택하면 활성화되는 `clearButton_Click` 이벤트는 해당 **Image** 속성을 **null** 또는 **nothing**으로 설정하여 현재 이미지를 지웁니다. 코드의 각 이벤트에는 코드의 기능에 대해 설명하는 주석이 포함되어 있습니다.

 ![비디오 링크](../data-tools/media/playvideo.gif) 이 항목의 비디오 버전은 [자습서 1: Visual Basic에서 사진 뷰어 만들기 - 비디오5](http://go.microsoft.com/fwlink/?LinkId=205216) 또는 [자습서 1: C#에서 사진 뷰어 만들기 - 비디오5](http://go.microsoft.com/fwlink/?LinkId=205206)를 참조하세요. 이러한 비디오에서는 이전 버전의 Visual Studio를 사용하므로 일부 메뉴 명령과 기타 사용자 인터페이스 요소가 약간 다를 수 있습니다. 그러나 개념 및 절차는 Visual Studio의 현재 버전에서 비슷하게 작동합니다.

> [!NOTE]
> 모범 사례: 항상 코드를 주석으로 처리합니다. 주석은 코드를 읽는 사용자의 이해를 돕기 위한 것으로, 프로그램에서는 주석 줄에 있는 모든 내용을 무시합니다. Visual C#에서는 두 개의 슬래시(//)로 주석 줄을 시작하고, Visual Basic에서는 작은따옴표(')로 주석 줄을 시작합니다.

## <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>추가 단추 및 확인란에 대한 코드를 작성하려면

- 다음 코드를 **Form1** 코드 파일(*Form1.cs* 또는 *Form1.vb*)에 추가합니다. Visual Basic 코드를 보려면 **VB** 탭을 선택합니다.

     [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]

## <a name="to-continue-or-review"></a>계속하거나 검토하려면

- 다음 자습서 단계로 이동하려면 [11단계: 프로그램 실행 및 기타 기능 사용](../ide/step-11-run-your-program-and-try-other-features.md)을 참조하세요.

- 이전 자습서 단계로 돌아가려면 [9단계: 코드 검토, 주석 처리 및 테스트](../ide/step-9-review-comment-and-test-your-code.md)를 참조하세요.
