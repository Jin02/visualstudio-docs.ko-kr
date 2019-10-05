---
title: 콘솔 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e947fb28c92323f0d4d66c697c272699fc63450e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68161321"
---
# <a name="console"></a>콘솔
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe **콘솔** 옵션은 새 명령 프롬프트 창에서 지정된 애플리케이션을 시작합니다. **콘솔**은 VSPerfCmd **Launch** 옵션에만 사용할 수 있습니다. 애플리케이션이 명령줄 애플리케이션이 아닌 경우 **콘솔**에 영향을 주지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="required-options"></a>필수 옵션  
 **콘솔**은 **Launch** 옵션도 포함하는 명령줄에서만 지정할 수 있습니다.  
  
 **Launch:** `AppName`  
 프로파일러 및 `AppName`에서 지정한 애플리케이션을 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 애플리케이션 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 애플리케이션 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)
