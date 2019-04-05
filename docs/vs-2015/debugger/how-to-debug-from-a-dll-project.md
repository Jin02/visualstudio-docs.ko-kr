---
title: '방법: DLL 프로젝트에서 디버그 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4a9a3e7cd63e5a485063789d9f9eeaf1227d1b5d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58983522"
---
# <a name="how-to-debug-from-a-dll-project"></a>방법: DLL 프로젝트에서 디버그
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DLL 프로젝트 디버깅을 시작하려면 프로젝트 속성에서 호출 응용 프로그램을 지정해야 합니다. C++ 속성 페이지의 레이아웃과 콘텐츠는 C# 및 Visual Basic 속성 페이지와 다릅니다.  
  
 네이티브 코드를 사용하여 관리되는 DLL을 호출하고 네이티브 코드와 관리되는 DLL을 모두 디버그하려는 경우 프로젝트 속성에서 이를 지정할 수 있습니다. 자세한 내용은 [방법: 혼합된 모드에서 디버깅](../debugger/how-to-debug-in-mixed-mode.md)합니다.  
  
> [!NOTE]
>  Visual Studio Express Edition에서 외부 호출 응용 프로그램을 지정할 수 없습니다. 대신 실행 가능한 프로젝트를 솔루션에 추가하여 시작 프로젝트로 설정하고 실행 가능한 프로젝트에서 DLL의 메서드를 호출해야 합니다.  
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>C++ 프로젝트에서 호출 응용 프로그램을 지정하려면  
  
1.  프로젝트 노드를 마우스 오른쪽 단추로 클릭 합니다 **솔루션 탐색기** 선택한 **속성**합니다. 로 이동 합니다 **디버그** 탭 합니다.  
  
2.  창의 맨 위에 있는 **구성** 필드가 **디버그**로 설정되어 있는지 확인합니다.  
  
3.  로 이동 **구성 속성 / 디버깅**합니다.  
  
4.  에 **실행할 디버거** 목록에서 선택 **로컬 Windows 디버거** 하거나 **원격 Windows 디버거**합니다.  
  
5.  에 **명령** 또는 **원격 명령** 상자에서 응용 프로그램의 정규화 된 경로 이름을 추가 합니다.  
  
6.  필요한 프로그램 인수를 **명령 인수** 상자에 추가합니다.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>C# 또는 Visual Basic 프로젝트에서 호출 응용 프로그램을 지정하려면  
  
1.  프로젝트 노드를 마우스 오른쪽 단추로 클릭 합니다 **솔루션 탐색기** 선택한 **속성**합니다. 로 이동 합니다 **디버그** 탭 합니다.  
  
     선택 **시작 외부 프로그램**, 프로그램 실행의 정규화 된 경로 이름을 추가 합니다.  
  
     외부 프로그램의 명령줄 인수를 추가 해야 할 경우에 추가 합니다 **명령줄 인수** 필드입니다.  
  
2.  응용 프로그램을 URL로 호출할 수도 있습니다. 로컬 ASP.NET 응용 프로그램에 사용되는 관리되는 DLL을 디버그하는 경우에도 이 작업을 수행할 수 있습니다.  
  
     아래 **시작 작업**를 선택 합니다 **URL로 브라우저 시작:** 라디오 단추 및 URL을 입력 합니다.  
  
### <a name="to-start-debugging-from-the-dll-project"></a>DLL 프로젝트에서 디버깅을 시작하려면  
  
1.  필요한 중단점을 설정합니다.  
  
2.  디버깅을 시작 (F5 키를 눌러, 녹색 화살표를 클릭 하거나 클릭 **디버그 / 디버깅 시작**).  
  
## <a name="see-also"></a>참고 항목  
 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md)   
 [C# 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [C++ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)
