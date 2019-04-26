---
title: 아랍어 및 히브리어 앱 지원
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Hebrew character display, creating applications
- bidirectional language support, about bidirectional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d09ad8644c30be76c38cf4b819d09ee1c470cb39
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62793441"
---
# <a name="create-applications-in-bidirectional-languages"></a>양방향 언어로 애플리케이션 만들기

Visual Studio를 사용하여 아랍어 및 히브리어와 같이 오른쪽에서 왼쪽으로 기록되는 언어로 텍스트를 제대로 표시하는 애플리케이션을 만들 수 있습니다. 일부 기능의 경우 속성만 설정하면 됩니다. 기타 경우에는 기능을 코드로 구현해야 합니다.

> [!NOTE]
> 양방향 언어를 입력 및 표시하려면 적절한 언어로 구성된 Windows 버전을 사용해야 합니다. 적절한 언어 팩이 설치된 Windows 영어 버전 또는 적절히 지역화된 Windows 버전 중 하나일 수 있습니다.

## <a name="types-of-applications-that-support-bidirectional-languages"></a>양방향 언어를 지원하는 애플리케이션 형식

- Windows 앱

   양방향 텍스트, 오른쪽에서 왼쪽 읽기 순서 및 미러링(창 레이아웃, 메뉴, 대화 상자 등 반전)에 대한 지원이 포함된 완전 양방향 애플리케이션을 만들 수 있습니다. 미러링을 제외하고 이러한 기능은 기본적으로 또는 속성 설정으로 사용할 수 있습니다. 미러링은 메시지 상자와 같은 일부 기능에만 기본적으로 지원됩니다. 다른 경우에는 미러링을 코드로 구현해야 합니다. 자세한 내용은 [Windows Forms 애플리케이션에 대한 양방향 지원](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications)을 참조하세요.

- 웹앱

   웹 서비스는 양방향 언어가 포함된 애플리케이션에 적합해지도록 UTF-8 및 유니코드 텍스트의 송수신을 지원합니다. 웹 클라이언트 애플리케이션은 브라우저를 기반으로 사용자 인터페이스를 제공하므로 웹 애플리케이션의 양방향 지원 정도는 사용자의 브라우저가 이 양방향 기능을 얼마나 잘 지원하는지에 따라 달라집니다. Visual Studio에서는 아랍어 및 히브리어 텍스트, 오른쪽에서 왼쪽 읽기 순서, 파일 인코딩 및 로컬 문화권 설정에 대한 지원을 사용하여 애플리케이션을 만들 수 있습니다. 자세한 내용은 [ASP.NET 웹 애플리케이션을 위한 양방향 지원](https://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03)을 참조하세요.

콘솔 앱에는 양방향 언어에 대한 텍스트 지원이 포함되지 않습니다. 이는 Windows가 콘솔 애플리케이션과 작동하는 방식 때문입니다.

## <a name="fully-supported-features"></a>완전히 지원되는 기능

Visual Studio에서 디자인 타임에 양방향 언어를 다음과 같은 방식으로 사용할 수 있습니다.

- **텍스트 입력**

   Visual Studio는 유니코드를 지원하므로 시스템이 적절한 로캘 및 입력 언어로 설정되면 아랍어 또는 히브리어로 텍스트를 입력할 수 있습니다. 아랍어 지원에는 Kashida 및 분음 부호가 포함됩니다.

- **개체 이름**

   양방향 언어를 사용하여 솔루션, 프로젝트, 파일, 폴더 등에 이름을 할당할 수 있습니다. 코드에서 변수, 클래스, 개체, 특성, 메타데이터 및 기타 요소의 이름에 양방향 언어를 사용할 수 있습니다.

- **파일 인코딩**

   언어별 또는 유니코드 인코딩을 사용하여 파일을 저장하고 열 수 있습니다. 자세한 내용은 [방법: 인코딩을 사용하여 파일 저장 및 열기](../ide/how-to-save-and-open-files-with-encoding.md)를 참조하세요.

## <a name="features-with-limited-support"></a>지원이 제한된 기능

### <a name="right-to-left-reading-order"></a>오른쪽에서 왼쪽 읽기 순서

기본적으로 Visual Studio의 텍스트 입력 컨트롤에는 왼쪽에서 오른쪽 읽기 순서가 사용됩니다. 대부분의 경우 표준 Windows 제스처를 사용하여 읽기 순서를 전환할 수 있습니다. 예를 들어 **Ctrl**+**RightShift**를 눌러 속성 값에 대한 오른쪽에서 왼쪽 읽기 순서를 지원하도록 **속성** 창을 전환할 수 있습니다. 그러나 Visual Studio에서는 오른쪽에서 왼쪽 읽기 순서가 지원되지 않습니다.

- Visual Studio 대화 상자의 확인란, 드롭다운 목록 및 기타 컨트롤에는 항상 왼쪽에서 오른쪽 읽기 순서가 사용됩니다.

- 코드 편집기(및 텍스트 편집기)는 오른쪽에서 왼쪽 읽기 순서를 지원하지 않습니다. 양방향 언어로 텍스트를 입력할 수 있지만 읽기 순서는 항상 왼쪽에서 오른쪽입니다.

## <a name="arabic-or-hebrew-object-names"></a>아랍어 또는 히브리어 개체 이름

아랍어 또는 히브리어 텍스트를 사용하여 폴더, 변수 또는 기타 개체에 이름을 할당할 수 있습니다. 아랍어를 사용할 경우 Kashida 및 분음 부호를 비롯한 아랍어 문자를 사용할 수 있습니다.

다음 요소는 아랍어 또는 히브리어를 사용하여 이름을 지정할 수 있고 Visual Studio에서 올바르게 처리됩니다.

- 프로젝트 경로에 포함하는 폴더를 비롯한 솔루션, 프로젝트 및 파일 이름. **솔루션 탐색기**에는 솔루션 및 요소 이름이 제대로 표시됩니다.

- 파일 콘텐츠. 유니코드 인코딩 또는 선택된 코드 페이지를 사용하여 파일을 열거나 저장할 수 있습니다.

    > [!NOTE]
    > 코드 편집기는 오른쪽에서 왼쪽 읽기 순서를 지원하지 않습니다.

- 데이터 요소. **서버 탐색기**에는 이러한 요소가 제대로 표시되고 이를 통해 요소를 편집할 수 있습니다.

- Windows 클립보드에 복사된 요소.

- 특성 및 메타데이터.

- 속성 값. **속성** 창에서 아랍어 또는 히브리어 텍스트를 사용할 수 있습니다. 이 창에서 표준 Windows 키 입력(오른쪽에서 왼쪽의 경우 **Ctrl**+**RightShift**, 왼쪽에서 오른쪽의 경우 **Ctrl**+**LeftShift**)을 사용하여 오른쪽에서 왼쪽 순서와 왼쪽에서 오른쪽 순서 간에 전환할 수 있습니다.

- 코드 및 리터럴 텍스트. 코드 편집기에서 아랍어 또는 히브리어를 사용하여 클래스, 함수, 변수, 속성, 문자열, 리터럴, 특성 등의 이름을 지정할 수 있습니다. 그러나 이 편집기는 오른쪽에서 왼쪽 읽기 순서를 지원하지 않고 텍스트는 항상 왼쪽 여백에서 시작됩니다.

    > [!TIP]
    > 문자열 리터럴을 프로그램에 하드 코딩하는 대신 리소스 파일에 배치해야 합니다. 자세한 내용은 [데스크톱 앱의 리소스(.NET Framework)](/dotnet/framework/resources/index)를 참조하세요.

    > [!NOTE]
    > 아랍어 및 히브리어로 명명된 개체를 참조하는 방법에 일관성이 있어야 합니다. 예를 들어 아랍어 변수 이름을 지정하는 데 Kashida를 사용할 경우 해당 변수를 참조할 때 항상 Kashida를 사용해야 합니다. 그렇지 않으면 오류가 발생합니다.

- 코드 주석입니다. 아랍어 또는 히브리어로 주석을 만들 수 있습니다. 주석 작성기 도구에서도 이러한 언어를 사용할 수 있습니다.