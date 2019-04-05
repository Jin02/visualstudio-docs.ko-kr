---
title: '방법: WCF 서비스 한 단계씩 실행 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0ad5ca2d74a1c141b9687d9b9eac5d8b3e268cc0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58971420"
---
# <a name="how-to-step-into-wcf-services"></a>방법: WCF 서비스 한 단계씩 코드 실행
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]에서는 WCF 서비스를 한 단계씩 실행할 수 있습니다. WCF 서비스가 클라이언트와 같은 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 솔루션인 경우에는 WCF 서비스 내의 중단점을 적중할 수 있습니다.  
  
 단계별 코드 실행이 제대로 작동하도록 하려면 app.config 또는 Web.config 파일에서 디버깅을 사용하도록 설정해야 합니다. 디버깅을 사용 하 고 WCF 서비스를 한 단계씩 실행할 때의 제한 사항, 참조 하는 방법에 대 한 자세한 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)합니다.  
  
### <a name="to-step-into-a-wcf-service"></a>WCF 서비스를 한 단계씩 실행하려면  
  
1.  WCF 클라이언트와 WCF 서비스 프로젝트가 모두 포함된 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 솔루션을 만듭니다.  
  
2.  솔루션 탐색기에서 WCF 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **시작 프로젝트로 설정**을 클릭합니다.  
  
3.  app.config 또는 web.config 파일에서 디버깅을 사용하도록 설정합니다. 자세한 내용은 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)합니다.  
  
4.  단계별 실행을 시작할 클라이언트 프로젝트의 위치에 중단점을 설정합니다. 이 위치는 일반적으로 WCF 서비스 호출 바로 앞입니다.  
  
5.  중단점까지 실행한 후 단계별 실행을 시작합니다. 디버거에서 서비스가 자동으로 한 단계씩 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스 디버그](../debugger/debugging-wcf-services.md)   
 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)   
 [방법: 자체 호스팅 WCF 서비스 디버그](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
