---
title: '방법: CD 설치를 위한 자동 시작 사용 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6266f487e2e0c66e532297c3fdae3fd3e5498052
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58982868"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>방법: CD 설치를 위한 자동 시작 사용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

배포 하는 경우는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 설정할 수 있습니다. 예: CD-ROM 또는 DVD-ROM 이동식 미디어를 사용 하 여 응용 프로그램 `AutoStart` 있도록는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 에 미디어를 삽입 하는 경우 응용 프로그램은 자동으로 시작 됩니다.  
  
 `AutoStart` 사용할 수 있습니다 합니다 **게시** 페이지의 **프로젝트 디자이너**합니다.  
  
### <a name="to-enable-autostart"></a>자동 시작 기능을 사용 하도록 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **옵션** 단추를 클릭합니다.  
  
     합니다 **게시 옵션** 대화 상자가 나타납니다.  
  
4.  클릭 **배포**합니다.  
  
5.  선택 된 **CD 설치는 자동으로 설치를 시작 CD를 삽입 하면** 확인란 합니다.  
  
     Autorun.inf 파일을 응용 프로그램을 게시할 때 게시 위치에 복사 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
