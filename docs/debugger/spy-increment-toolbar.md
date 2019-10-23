---
title: Spy + + 도구 모음 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Spy++ toolbar
ms.assetid: 949c18fb-bb25-42ed-9130-c4a47869f24d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fa1dfe0917fece3c814678295c5abd6013b426b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72729731"
---
# <a name="spy-toolbar"></a>Spy++ 도구 모음
도구 모음은 Spy + +의 메뉴 모음 아래에 나타납니다. 도구 모음을 표시 하거나 숨기려면 **보기** 메뉴에서 **도구 모음**을 클릭 합니다.

 도구 모음에서 사용할 수 있는 컨트롤은 다음과 같습니다.

## <a name="uielement-list"></a>UI 요소 목록

|단추|효과|
|------------|------------|
|![Spy&#43; &#43; 창 단추](../debugger/media/icon_spy--_windows.gif "Icon_Spy + + _Windows")|시스템의 창 및 컨트롤 트리 뷰를 표시 합니다. 자세한 내용은 [Windows 뷰](../debugger/windows-view.md)를 참조 하세요.|
|![감시&#43; &#43; 프로세스 단추](../debugger/media/icon_spy--_processes.gif "Icon_Spy + + 프로세스 (_e)")|시스템의 프로세스 트리 뷰를 표시 합니다. 자세한 내용은 [프로세스 뷰](../debugger/processes-view.md)를 참조 하세요.|
|![Spy&#43; &#43; 스레드 단추](../debugger/media/icon_spy--_threads.gif "Icon_Spy + + 스레드 (_e)")|시스템에 있는 스레드의 트리 뷰를 표시 합니다. 자세한 내용은 [스레드 뷰](../debugger/threads-view.md)를 참조 하세요.|
|![Spy&#43; &#43; 메시지 단추](../debugger/media/icon_spy--_messages.gif "Icon_Spy + + 메시지 (_e)")|창 메시지를 표시 하는 창을 만들고 메시지 **옵션** 대화 상자를 엽니다 .이 대화 상자에서 메시지가 표시 될 창을 선택 하 고 다른 옵션도 선택할 수 있습니다. 자세한 내용은 [메시지 뷰](../debugger/messages-view.md)를 참조 하세요.|
|![Spy&#43; &#43; 로그 시작 단추](../debugger/media/icon_spy--_startlog.gif "Icon_Spy + + _StartLog")|메시지 로깅을 시작 하 고 메시지 스트림을 표시 합니다. 이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다. 자세한 내용은 [방법: 메시지 로그 표시 시작 및 중지](../debugger/how-to-start-and-stop-the-message-log-display.md)를 참조 하세요.|
|![Spy&#43; &#43; 로그 중지 단추](../debugger/media/icon_spy--_stoplog.gif "Icon_Spy + + _StopLog")|메시지 로깅 및 메시지 스트림의 표시를 중지 합니다. 이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다. 자세한 내용은 [방법: 메시지 로그 표시 시작 및 중지](../debugger/how-to-start-and-stop-the-message-log-display.md)를 참조 하세요.|
|![Spy&#43; &#43; 로그 옵션 단추](../debugger/media/icon_spy--_logoptions.gif "Icon_Spy + + _LogOptions")|[메시지 옵션](../debugger/message-options-dialog-box.md) 대화 상자를 표시 합니다. 이 대화 상자를 사용 하 여 볼 수 있는 창 및 메시지 유형을 선택할 수 있습니다. 이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.|
|![Spy&#43; &#43; 로그 지우기 단추](../debugger/media/spy--_clearlog.gif "Spy + + _ClearLog")|활성 **메시지** 창의 내용을 지웁니다. 이 컨트롤은 **메시지** 창이 활성 창인 경우에만 사용할 수 있습니다.|
|![Spy&#43; &#43; 창 찾기 단추](../debugger/media/icon_spy--_findwindow.gif "Icon_Spy + + _FindWindow")|창 검색 조건을 설정 하 고 속성 또는 메시지를 표시할 수 있는 [창 찾기](../debugger/find-window-dialog-box.md) 대화 상자를 엽니다. 자세한 내용은 [방법: Finder 도구 사용](../debugger/how-to-use-the-finder-tool.md)을 참조 하세요.|
|![Spy&#43; &#43; 첫 번째 창 찾기 단추](../debugger/media/icon_spy--_window.gif "Icon_Spy + + 창 (_l)")|현재 뷰에서 일치 하는 창, 프로세스, 스레드 또는 메시지를 검색 합니다.|
|![Spy&#43; &#43; 다음 창 찾기 단추](../debugger/media/icon_spy--_nextwindow.gif "Icon_Spy + + _NextWindow")|현재 뷰에서 일치 하는 다음 창, 프로세스, 스레드 또는 메시지를 검색 합니다. 이 컨트롤 (및 관련 메뉴 명령)은 고유 하지 않은 유효한 검색 결과가 있는 경우에만 사용할 수 있습니다. 예를 들어 창 트리에서 창 핸들을 검색 조건으로 사용 하는 경우 창 트리에 해당 핸들이 있는 창이 하나 뿐 이기 때문에 고유한 결과가 생성 됩니다. 이 인스턴스에서 **다음 찾기** 는 사용할 수 없습니다.|
|![Spy&#43; &#43; 이전 창 찾기 단추](../debugger/media/icon_spy--_prevwindow.gif "Icon_Spy + + _PrevWindow")|현재 뷰에서 일치 하는 이전 창, 프로세스, 스레드 또는 메시지를 검색 합니다. 이 컨트롤 (및 관련 메뉴 명령)은 고유 하지 않은 유효한 검색 결과가 있는 경우에만 사용할 수 있습니다. 예를 들어 창 트리에서 창 핸들을 검색 조건으로 사용 하는 경우 창 트리에 해당 핸들이 있는 창이 하나 뿐 이기 때문에 고유한 결과가 생성 됩니다. 이 인스턴스에서는 **이전 찾기** 를 사용할 수 없습니다.|
|![Spy&#43; &#43; 속성 탐색기 단추](../debugger/media/icon_spy--_propexp.gif "Icon_Spy + + _PropExp")|Windows 보기에서 선택한 창의 속성을 표시 합니다.|
|![Spy&#43; &#43; 새로 고침 단추](../debugger/media/icon_spy--_refresh.gif "Icon_Spy + + 새로 고침 (_s)")|시스템 뷰를 새로 고칩니다.|

## <a name="see-also"></a>참조
- [Spy++ 사용](../debugger/using-spy-increment.md)
- [Spy++ 뷰](../debugger/spy-increment-views.md)
- [Spy++ 참조](../debugger/spy-increment-reference.md)