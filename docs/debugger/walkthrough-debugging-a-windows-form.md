---
title: Windows Form 디버깅 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- debugging managed code, Windows Forms
- debugging [Visual Studio], Windows Forms
- Attach to Process dialog box
- debugger, attaching to programs
- Attach to Process dialog box, walkthroughs
- Windows Forms, debugging
- debugging Windows Forms, walkthroughs
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d2f581582acfed38d55a2cfef351856cc0caa945
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65678917"
---
# <a name="walkthrough-debugging-a-windows-form"></a>연습: Windows Form 디버깅
Windows 폼에는 가장 일반적인 관리 되는 응용 프로그램 중 하나입니다. Windows 폼에 표준 Windows 응용 프로그램을 만듭니다. Visual Basic을 사용 하 여이 연습을 완료 하려면 C#, 또는 C++합니다.

 먼저, 열려 있는 솔루션을 닫아야 합니다.

### <a name="to-prepare-for-this-walkthrough"></a>이 연습을 준비하려면

- 이미 열려 있는 솔루션이 있으면 닫습니다. (에 **파일** 메뉴에서 **솔루션 닫기**.)

## <a name="create-a-new-windows-form"></a>새 Windows Form 만들기
 다음으로 새 Windows 폼을 만듭니다.

#### <a name="to-create-the-windows-form-for-this-walkthrough"></a>이 연습에 대 한 Windows 폼을 만들려면

1. 에 **파일** 메뉴 선택 **새로 만들기** 클릭 **프로젝트**합니다.

     **새 프로젝트** 대화 상자가 나타납니다.

2. 프로젝트 형식 창에서 엽니다는 **Visual Basic**를 **시각적 C#** , 또는 **Visual C++**  노드를 다음

    1. Visual Basic 또는 Visual C#을 선택 **Windows 바탕 화면** > **Windows 양식 앱**합니다.

    2. 시각적 개체에 대해 C++을 선택 **Windows 데스크톱 응용 프로그램**합니다.

3. 에 **이름을** 상자, 프로젝트 (예를 들어 Walkthrough_SimpleDebug) 고유한 이름을 지정 합니다.

4. **확인**을 클릭합니다.

     Visual Studio 새 프로젝트를 만들고 Windows Forms 디자이너에서 새 폼을 표시 합니다. 자세한 내용은 [Windows Forms 디자이너](/previous-versions/visualstudio/visual-studio-2010/e06hs424\(v\=vs.100\))합니다.

5. 에 **뷰** 메뉴에서 **도구 상자**합니다.

     도구 상자가 열립니다. 자세한 내용은 [도구 상자](../ide/reference/toolbox.md)를 참조하세요.

6. 도구 상자에서 클릭 합니다 **단추** 컨트롤과 폼 디자인 화면에 컨트롤을 끌어 옵니다. 폼에서 단추를 삭제 합니다.

7. 도구 상자에서 클릭 합니다 **텍스트 상자** 제어 하 고 양식 디자인 화면에 컨트롤을 끌어 옵니다. 삭제 합니다 **텍스트 상자** 양식의 합니다.

8. 폼 디자인 화면에서 단추를 두 번 클릭 합니다.

     이렇게 하면 코드 페이지입니다. 커서에 있어야 합니다. `button1_Click`합니다.

10. `button1_Click` 함수에 다음 코드를 추가합니다.

    ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";
    ```

11. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.

     프로젝트가 오류 없이 빌드되어야 합니다.

## <a name="debug-your-form"></a>폼을 디버그
 이제 디버깅을 시작할 준비가 되었습니다.

#### <a name="to-debug-the-windows-form-created-for-this-walkthrough"></a>이 연습에서 만든 Windows Form을 디버깅 하려면

1. 소스 창에서 추가한 텍스트와 동일한 줄의 왼쪽된 여백을 클릭 합니다.

     ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";
    ```

     빨간 점이 나타나며 해당 줄의 텍스트가 빨간색으로 강조 표시됩니다. 빨간 점은 중단점을 나타냅니다. 자세한 내용은 [중단점](https://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583)을 참조하세요. 디버거에서 응용 프로그램을 실행하면 코드가 적중되는 위치에서 디버거가 실행을 중단합니다. 그런 다음 응용 프로그램의 상태를 보고 디버깅할 수 있습니다.

    > [!NOTE]
    > 모든 줄을 마우스 오른쪽 단추로 클릭 코드의 가리킨 **중단점**, 클릭 하 고 **중단점 삽입** 해당 줄에 중단점을 추가 하려면.

2. **디버그** 메뉴에서 **시작**을 선택합니다.

     Windows 폼 실행 되기 시작 합니다.

3. Windows 폼에 추가한 단추를 클릭 합니다.

     Visual Studio에서이 줄으로 이동 된 코드 페이지에 중단점을 설정한 합니다. 이 줄은 노란색으로 강조 표시되어 있어야 합니다. 이제 응용 프로그램의 변수를 보고 해당 응용 프로그램의 실행을 제어할 수 있습니다. 응용 프로그램 실행, 사용자 작업에 대 한 대기에 이제 중지 되었습니다.

4. 에 **디버그** 메뉴에서 선택 **Windows**, 한 다음 **조사식**, 클릭 **조사식 1**.

5. 에 **조사식 1** 창에서 빈 행을 클릭 합니다. 에 **이름** 열, 형식 `textBox1.Text` (Visual Basic 또는 시각적 개체를 사용 하는 경우 C#) 또는 `textBox1->Text` (사용 중인 경우 C++), 한 다음 ENTER 키를 누릅니다.

     합니다 **조사식 1** 창으로 인용 부호 안에이 변수의 값을 표시 합니다.

    `""`

6. **디버그** 메뉴에서 **한 단계씩 코드 실행**을 선택합니다.

     변경 내용 textBox1.Text의 값을 **조사식 1** 창:

    `Button was clicked!`

7. 에 **디버그** 메뉴 선택 **계속** 프로그램 디버깅을 다시 시작 합니다.

8. Windows 폼에 단추를 다시 클릭 합니다.

     Visual Studio는 다시 실행을 중단합니다.

9. 중단점을 나타내는 빨간색 점을 클릭 합니다.

     이 코드에서 중단점을 제거합니다.

10. **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.

## <a name="attach-to-your-windows-form-application-for-debugging"></a>디버깅을 위해 Windows Form 응용 프로그램에 연결
 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 실행 중인 프로세스에 디버거를 연결할 수 있습니다. Express 버전을 사용 하는 경우이 기능은 지원 되지 않습니다.

#### <a name="to-attach-to-the-windows-form-application-for-debugging"></a>디버깅에 대 한 Windows Form 응용 프로그램에 연결

1. 위에서 만든 프로젝트에서 다시 한 번 추가한 줄에 중단점을 설정 하려면 왼쪽된 여백을 클릭 합니다.

     ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";
    ```

2. 에 **디버그** 메뉴에서 **디버깅 하지 않고 시작**합니다.

     Windows 폼 것 처럼 해당 실행 파일을 두 번 클릭 했습니다를 Windows에서 실행을 시작 합니다. 디버거가 연결 되지 않습니다.

3. 에 **디버그** 메뉴에서 **프로세스에 연결**합니다. (이 명령에서 사용할 수 있는 이기도 합니다 **도구** 메뉴.)

     **프로세스에 연결** 대화 상자가 나타납니다.

4. 에 **사용 가능한 프로세스** 창, 프로세스 이름 (Walkthrough_SimpleDebug.exe) 찾기 합니다 **프로세스** 열 클릭 합니다.

5. 클릭 합니다 **연결** 단추입니다.

6. Windows 폼에서 및만 단추를 클릭 합니다.

     디버거가는 중단점에서 Windows Form의 실행을 중단 합니다.

## <a name="see-also"></a>참고 항목
- [관리 코드 디버그](../debugger/debugging-managed-code.md)
- [디버거 보안](../debugger/debugger-security.md)
