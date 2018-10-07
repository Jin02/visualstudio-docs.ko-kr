---
title: '방법: 혼합된 모드에서 디버그 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ce056b60a3e080490a2ad60f4aee5a7b5c8dd63
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542508"
---
# <a name="how-to-debug-in-mixed-mode"></a>How to: Debug in Mixed Mode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 혼합 모드에서 디버깅](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-in-mixed-mode)합니다.  
  
다음 절차에서는 관리 코드와 네이티브 코드를 모두 디버깅하는 방법에 대해 설명합니다. 이러한 디버깅을 혼합 모드 디버깅이라고도 합니다. 네이티브 코드로 작성된 것이 DLL인지 응용 프로그램인지 여부에 따라 혼합 모드 디버깅에는 두 가지 시나리오가 있습니다.  
  
-   DLL을 호출하는 호출 응용 프로그램이 네이티브 코드로 작성된 경우 DLL이 관리 코드로 작성된 것입니다. 이 경우 관리되는 디버거와 네이티브 디버거가 둘 모두를 디버깅할 수 있어야 합니다. 이 확인할 수 있습니다 합니다  **\<프로젝트 > 속성 페이지** 대화 상자. 이를 수행하는 방법은 DLL 프로젝트에서 디버깅을 시작하는지 아니면 호출 응용 프로그램 프로젝트에서 디버깅을 시작하는지에 따라 달라집니다.  
  
-   DLL을 호출하는 응용 프로그램이 관리 코드로 작성된 경우 DLL이 네이티브 코드로 작성된 것입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-enable-mixed-mode-debugging"></a>혼합 모드 디버깅을 사용하도록 설정하려면  
  
1.  **솔루션 탐색기**, 프로젝트를 선택 합니다.  
  
2.  에 **뷰** 메뉴에서 클릭 **속성 페이지**합니다.  
  
3.  에  **\<프로젝트 > 속성 페이지** 대화 상자를 확장 합니다 **구성 속성** 노드를 선택한 후 **디버깅**.  
  
4.  설정 **디버거 형식** 하 **혼합** 하거나 **자동**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)


