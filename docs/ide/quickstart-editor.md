---
title: "Visual Studio의 편집 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.workload: multiple
ms.openlocfilehash: 614e8856fa8d4c674e40703448399265f2adc456
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-coding-in-the-editor"></a>빠른 시작: 편집기에서 코딩

편집기에 대한 이 10분 소개에서 코드를 파일에 추가하여 Visual Studio에서 코드를 보다 쉽게 작성, 탐색 및 이해하는 몇 가지 방법을 살펴봅니다.

## <a name="create-a-new-code-file"></a>새 코드 파일 만들기

새 파일을 만들고 일부 코드를 추가하여 시작합니다. 편집기에서 제공하는 이점 중 일부를 사용하기 위해 프로젝트를 만들 필요가 없습니다.

1. Visual Studio를 열고, 메뉴 모음의 **파일** 메뉴에서 **새로 만들기** > **파일...**을 선택합니다.

1. **새 파일** 대화 상자의 **일반** 범주 아래에서 **Visual C# 클래스**를 선택한 다음 **열기**를 선택합니다.

   C# 클래스의 구조를 사용하여 편집기에서 새 파일이 열립니다.

## <a name="using-code-snippets"></a>코드 조각 사용

Visual Studio에서는 일반적으로 사용되는 코드 블록을 쉽고 빠르게 생성하는 데 사용할 수 있는 유용한 코드 조각을 제공합니다. [코드 조각](../ide/code-snippets.md)은 C#, Visual Basic 및 C++를 포함하여 다양한 프로그래밍 언어에서 사용할 수 있습니다. C# `void Main` 코드 조각을 파일에 추가하겠습니다.

1. `Class1` 생성자의 닫는 중괄호 아래에 커서를 놓고 `svm` 문자를 입력합니다.

   `svm` 코드 조각에 대한 정보와 함께 IntelliSense 대화 상자가 표시됩니다.

   ![IntelliSense 코드 조각](media/quickstart-intellisense-snippet.png)

1. **탭** 키를 두 번 눌러 코드 조각을 삽입합니다.

   `static void Main()` 메서드 서명이 파일에 추가됩니다. `Main()` 메서드는 C# 응용 프로그램의 진입점입니다.

사용 가능한 코드 조각은 언어마다 다릅니다. **편집**, **IntelliSense**, **코드 조각 삽입...**을 선택한 다음 언어의 폴더를 선택하여 프로그래밍 언어에 사용 가능한 코드 조각에서 확인할 수 있습니다. C#의 경우 목록은 다음과 같습니다.

![C# 코드 조각 목록](media/quickstart-code-snippet-list.png)

목록에는 클래스, 생성자 `Console.WriteLine()`, `for` 루프, `if` 및 `switch` 문 등을 만들기 위한 코드 조각이 포함됩니다.

## <a name="commenting-out-code"></a>코드 주석 처리

도구 모음에서는 더 생산적으로 코딩할 수 있는 여러 단추를 제공합니다. 예를 들어 IntelliSense 완성 모드를 설정/해제하거나, 들여쓰기 또는 내어쓰기를 설정하거나, 책갈피를 설정하거나, 코드를 주석으로 처리할 수 있습니다. 이 섹션에서 컴파일하지 않으려는 일부 코드를 주석으로 처리합니다.

![편집기 도구 모음](media/quickstart-editor-toolbar.png)

1. 다음 코드를 `Main()` 메서드 본문에 붙여넣습니다.

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    }

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. `morewords` 변수를 사용하지 않지만 나중에 사용할 것이므로 삭제하지 않습니다. 대신 해당 줄을 주석으로 처리해 보겠습니다. 닫는 세미콜론에 대한 `morewords`의 전체 정의를 선택하거나, 도구 모음에서 **선택한 줄 주석 처리** 단추를 선택하거나 **Ctrl**+**K**, **Ctrl**+**C** 키를 누릅니다.

   ![단추 주석 처리](media/quickstart-comment-out.png)

   C# 주석 문자 `//`를 선택한 각 줄의 시작 부분에 추가하여 코드를 주석으로 처리합니다.

## <a name="collapsing-code-blocks"></a>코드 블록 축소

코드의 보기를 정리하도록 생성된 `Class1`에 대한 빈 생성자를 표시하지 않으려면 축소할 수 있습니다. 생성자의 첫 번째 줄 여백에 있는 작은 회색 상자 안에 빼기 기호를 선택합니다. 또는 키보드 사용자인 경우 생성자 코드의 아무 곳에 커서를 두고 **Ctrl**+**M**, **Ctrl**+**M** 키를 누릅니다.

![축소 단추 개요](media/quickstart-collapse.png)

코드 블록은 줄임표(`...`) 뒤에 있는 첫 번째 줄로 축소됩니다. 코드 블록을 다시 확장하려면 더하기 기호가 있는 동일한 회색 상자를 클릭하거나 **Ctrl**+**M**, **Ctrl**+**M**을 다시 누릅니다. 이 기능은 [개요](../ide/outlining.md)라고 하고 긴 메서드 또는 전체 클래스를 축소하는 경우에 특히 유용합니다.

## <a name="viewing-symbol-definitions"></a>기호 정의 보기

Visual Studio 편집기를 사용하면 형식, 메서드 등 정의를 쉽게 검사할 수 있습니다. 예를 들어 기호가 참조되는 **정의로 이동**을 선택하는 것이 정의가 포함되는 파일을 탐색하는 한 가지 방법입니다. [정의 피킹](../ide/go-to-and-peek-definition.md#peek-definition)을 사용하는 것도 작업 중인 파일에서 포커스를 이동하지 않는 더욱 빠른 방식입니다. `string`이라는 정의를 피킹해 보겠습니다.

1. `string`의 모든 항목을 마우스 오른쪽 단추로 클릭하고 콘텐츠 메뉴에서&mdash; **정의 피킹**을 선택하거나 **Alt**+**F12** 키를 누릅니다.

   `String` 클래스의 정의를 포함한 팝업 창이 표시됩니다. 팝업 창 내에서 스크롤하거나 피킹된 코드에서 다른 형식의 정의에 피킹할 수도 있습니다.

   ![정의 피킹 창](media/quickstart-peek-definition.png)

1. 팝업 창의 오른쪽 위에서 "x"가 포함된 작은 상자를 선택하여 피킹된 정의 창을 닫습니다.

## <a name="using-intellisense-to-complete-words"></a>IntelliSense를 사용하여 단어 자동 완성

[IntelliSense](../ide/using-intellisense.md)는 코딩할 때 매우 유용한 리소스입니다. 형식의 사용 가능한 멤버에 대한 정보 또는 메서드의 다른 오버 로드에 대한 매개 변수 세부 정보를 표시할 수 있습니다. 또한 IntelliSense를 사용하여 구분할 수 있을 정도로 문자를 입력한 후에 단어를 자동 완성할 수 있습니다. 콘솔 창에 순서가 지정된 문자열을 출력하는 코드 줄을 추가해 보겠습니다.

1. `query` 변수 아래에 다음 코드를 입력하기 시작합니다.

   ```csharp
   foreach (string str in qu
   ```

   IntelliSense에 `query` 기호에 대한 **요약 정보**가 표시됩니다.

   ![IntelliSense 단어 자동 완성](media/quickstart-intellisense-completion-list.png)

1. IntelliSense의 "단어 자동 완성" 기능을 사용하여 `query` 단어의 나머지 부분을 삽입하려면 **탭** 키를 누릅니다.

1. 코드 블록을 다음 코드와 같이 완성합니다. `Console.WriteLine` 코드를 생성하기 위해 `cw`을 입력한 다음 **탭** 키를 두 번 눌러서 using 코드 조각을 사용할 수 있습니다.

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactoring-a-name"></a>이름 리팩터링

누구도 처음부터 제대로 코딩할 수 없습니다. 변경할 수 있는 작업 중 하나는 변수 또는 메서드의 이름입니다. Visual Studio의 [리팩터링](../ide/refactoring-code-generation-quick-actions.md#refactoring) 기능을 사용하여 `_words` 변수 이름을 `words`로 변경해 보겠습니다.

1. `words` 변수의 정의 위에 커서를 두거나, 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **이름 바꾸기...**를 선택하거나, **Ctrl**+**R**, **Ctrl**+**R** 키를 누릅니다.

   편집기의 오른쪽 위에 팝업 **이름 바꾸기** 대화 상자가 나타납니다.

1. 원하는 이름 `words`를 입력합니다. 쿼리에서 `words`에 대한 참조 이름이 자동으로 바뀝니다. **Enter** 키를 누르기 전에 **이름 바꾸기** 팝업 상자에서 **주석 포함** 확인란을 선택합니다.

   ![이름 바꾸기 대화 상자](media/quickstart-rename.png)

1. **Enter** 키를 누릅니다.

   `words`의 두 항목 이름 및 코드 주석에서 `words`에 대한 참조도 변경했습니다.

## <a name="next-steps"></a>다음 단계

Visual Studio 편집기에 대한 이 빠른 시작을 완료했습니다. 다음으로 Visual Studio IDE에 대한 일부 다른 빠른 시작을 사용해 보겠습니다. [코드를 탐색](../ide/navigating-code.md)하는 다양한 방법을 살펴보고 살펴볼 기능의 자세한 정보에 대한 링크를 확인합니다. 그렇지 않으면 즐거운 코딩을 경험하시기 바랍니다!

## <a name="see-also"></a>참고 항목

[빠른 시작: 먼저 Visual Studio IDE 살펴보기](../ide/quickstart-ide-orientation.md)  
[빠른 시작: Visual Studio IDE 및 편집기 개인 설정](../ide/quickstart-personalize-the-ide.md)  
[빠른 시작: 프로젝트 및 솔루션](../ide/quickstart-projects-solutions.md)  
[코드 조각](../ide/code-snippets.md)  
[개요](../ide/outlining.md)  
[정의로 이동 및 정의 피킹(Peeking)](../ide/go-to-and-peek-definition.md)  
[리팩터링](../ide/refactoring-code-generation-quick-actions.md#refactoring)  
[IntelliSense 사용](../ide/using-intellisense.md)  