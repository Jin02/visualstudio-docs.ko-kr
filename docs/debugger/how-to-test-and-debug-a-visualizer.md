---
title: '방법: 시각화 도우미 테스트 및 디버그 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2a0d2fdcd0685b83f63e9354b96146c1c869b355
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72732402"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>방법: 시각화 도우미 테스트 및 디버깅
시각화 도우미를 작성한 후에는 이를 디버깅하고 테스트해야 합니다.

시각화 도우미를 테스트하는 한 가지 방법으로 이를 Visual Studio에 설치하고 디버거 창에서 호출할 수 있습니다. [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)를 참조 하세요. 이렇게 하는 경우 Visual Studio의 두 번째 인스턴스를 사용 하 여 디버거의 첫 번째 인스턴스에서 실행 되는 시각화 도우미를 연결 하 고 디버깅 해야 합니다.

시각화 도우미를 디버깅하기 위한 더 쉬운 방법으로는 테스트 드라이버에서 시각화 도우미를 실행하는 방법이 있습니다. 시각화 도우미 API를 사용하면 그와 같은 드라이버를 쉽게 만들 수 있습니다. 이 드라이버를 *시각화 도우미 개발 호스트*라고 합니다.

### <a name="to-create-a-visualizer-development-host"></a>시각화 도우미 개발 호스트를 만들려면

1. <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> 개체를 만들고 이 개체의 표시 메서드를 호출하는 정적 메서드를 디버거 쪽 클래스에 포함합니다.

    ```csharp
    public static void TestShowVisualizer(object objectToVisualize)
    {
        VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));
        myHost.ShowVisualizer();
    }
    ```

    호스트를 생성하는 데 사용되는 매개 변수는 시각화 도우미(`objectToVisualize`)에서 표시할 데이터 개체 및 디버거 쪽 클래스의 형식입니다.

2. 다음 문을 추가하여 `TestShowVisualizer`를 호출합니다. 클래스 라이브러리에서 시각화 도우미를 만든 경우 클래스 라이브러리를 호출하기 위한 실행 파일을 만들고 이 문을 실행 파일에 배치해야 합니다.

    ```csharp
    DebuggerSide.TestShowVisualizer(myString);
    ```

    자세한 예제는 [연습:에서 C#시각화 도우미 작성 ](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)을 참조 하세요.

## <a name="see-also"></a>참조
- [연습: C#에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)
- [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)
- [Create Custom Visualizers of Data](../debugger/create-custom-visualizers-of-data.md)(데이터의 사용자 지정 시각화 도우미 만들기)
