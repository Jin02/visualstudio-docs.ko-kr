---
title: '방법: 게시 버전 자동 증가 ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ab2dc62add13db9af1186a8974ffe5694a98e62e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083508"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>방법: ClickOnce 게시 버전 자동 증가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

게시 하는 경우는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 응용 프로그램을 변경 합니다 `Publish Version` 속성 하면 응용 프로그램이 업데이트로 게시 합니다. 기본적으로 Visual Studio 자동으로 증가 합니다 `Revision` 횟수는 `Publish Version` 응용 프로그램을 게시할 때마다 합니다.  
  
 이 동작을 비활성화할 수는 **게시** 페이지를 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>게시 버전 자동 증가 사용 하지 않도록 설정  
  
1. **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2. **게시** 탭을 클릭합니다.  
  
3. 에 **게시 버전** 섹션의 선택을 취소는 **자동 릴리스마다 수정 번호 증가** 확인란 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 게시 버전 설정 ClickOnce](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
