---
title: '방법: ARM 장치의 그래픽 진단 사용 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 346fd3c0-9e92-4ab8-bb3b-1aa9000a2483
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7ae934de4a9f0dbcf4076d7402abd138eac20268
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104878"
---
# <a name="how-to-use-graphics-diagnostics-with-an-arm-device"></a>방법: ARM 장치의 그래픽 진단 사용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

그래픽 진단은 Windows RT 8.1 또는 Windows Phone 8.1을 실행하는 ARM 기반 장치에서 Direct3D 앱의 원격 디버깅을 제공합니다. 이 장치에서 Direct3D 앱을 실행 중에는 Direct3D 앱에서 그래픽 정보를 캡처하거나 해당 장치를 이전에 캡처된 그래픽 정보를 위한 재생 컴퓨터로 사용할 수 있습니다.  
  
## <a name="using-graphics-diagnostics-with-an-arm-based-device"></a>ARM 기반 장치에서 그래픽 진단 사용  
 Visual Studio는 ARM 기반 장치에서 실행되지 않으므로 이러한 장치에서 실행하는 앱을 분석하려면 원격 디버거를 사용해야 합니다. 원격 디버거는 그래픽 캡처 및 재생을 지원하므로 ARM 기반 장치에서 응용 프로그램을 쉽게 디버깅할 수 있는 것처럼 이러한 장치에서 렌더링 오류를 진단하고 그래픽 성능을 평가할 수 있습니다.  
  
 그래픽 진단 기능을 사용하려면 우선 장치에서 원격 디버깅을 사용하도록 설정합니다.  
  
#### <a name="to-enable-remote-debugging-on-your-arm-based-device"></a>ARM 기반 장치에서 원격 디버깅을 사용하도록 설정하려면  
  
1. 설치 합니다 [ARM 키트 정책](http://msdn.microsoft.com/windows/desktop/dn469188) ARM 기반 장치에서.  
  
2. 설치 합니다 [원격 디버깅 도구](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015) ARM 기반 장치에서.  
  
> [!IMPORTANT]
>  Windows Phone 8.1 장치의 경우 개발용으로 사용자의 휴대폰을 등록해야 할 수 있습니다. 그렇게 하려면 등록된 개발자여야 합니다. 자세한 내용은 [배포 및 Windows Phone 8 용 앱을 실행 하는 방법을](http://msdn.microsoft.com/library/windowsphone/develop/ff402565.aspx)합니다.  
  
 장치에서 원격 디버깅을 사용하도록 설정한 후에 해당 장치를 디버그 대상으로 지정하고 그래픽 진단을 시작합니다.  
  
#### <a name="to-configure-and-start-graphics-diagnostics-on-your-device"></a>장치에서 그래픽 진단을 구성한 후 시작하려면  
  
1. 에 **솔루션 플랫폼** 드롭 다운 목록에서 **ARM** ARM 기반 장치를 원격 디버깅 대상으로 사용할 수 있도록 합니다.  
  
2. 에 **디버그 대상** 드롭 다운 목록에서 ARM 장치를 선택 합니다.  
  
3. 메뉴에서 선택 **디버그**, **그래픽**하십시오 **진단 시작**. (키보드: Alt+F5)  
  
## <a name="see-also"></a>참고 항목  
 [원격 컴퓨터에서 Windows 스토어 앱 실행](../debugger/run-windows-store-apps-on-a-remote-machine.md)   
 [방법: 그래픽 진단 재생 머신 변경](../debugger/how-to-change-the-graphics-diagnostics-playback-machine.md)
