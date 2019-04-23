---
title: '방법: 배포 업데이트를 위한 대체 위치를 지정 합니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14a1c072cb8415e8e0a20615c0c963e683f48b56
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041356"
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>방법: 배포 업데이트를 위한 대체 위치 지정
설치할 수 있습니다 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] CD 또는 파일 공유에서 처음에 응용 프로그램 이지만 응용 프로그램 웹에 대 한 주기적인 업데이트를 확인 해야 합니다. 응용 프로그램을 처음 설치한 후 웹에서 자동으로 업데이트할 수 있도록 배포 매니페스트에 업데이트에 대 한 대체 위치를 지정할 수 있습니다.

> [!NOTE]
>  응용 프로그램은이 기능을 사용 하기 위해 로컬로 설치 하려면 구성 되어야 합니다. 자세한 내용은 [연습: 수동으로 ClickOnce 응용 프로그램을 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다. 또한 설치 하는 경우에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 대체 위치를 설정 하면 네트워크에서 응용 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 초기 설치 및 모든 후속 업데이트에 대 한 해당 위치를 사용 하도록 합니다. 응용 프로그램을 로컬로 (예: CD)에서 설치 하는 경우 원본 미디어를 사용 하 여 초기 설치를 수행 하 고 이후의 모든 업데이트는 대체 위치를 사용 하 여 합니다.

### <a name="specify-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>MageUI.exe (Windows Forms 기반 유틸리티)를 사용 하 여 업데이트에 대 한 대체 위치를 지정 합니다.

1. .NET Framework 명령 프롬프트를 열고 형식:

     **mageui.exe**

2. 에 **파일** 메뉴 선택 **엽니다** 응용 프로그램의 배포 매니페스트를 엽니다.

3. **배포 옵션** 탭을 선택합니다.

4. 텍스트 상자에 이름이 **시작 위치**, 응용 프로그램 업데이트에 대 한 배포 매니페스트를 포함 하는 디렉터리에 URL을 입력 합니다.

5. 배포 매니페스트를 저장 합니다.

### <a name="specify-an-alternate-location-for-updates-by-using-mageexe"></a>Mage.exe를 사용 하 여 업데이트에 대 한 대체 위치를 지정 합니다.

1. .NET Framework 명령 프롬프트를 엽니다.

2. 다음 명령을 사용 하 여 업데이트 위치를 설정 합니다. 이 예제에서는 *HelloWorld.exe.application* 경로인 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 항상.application 확장명에는 응용 프로그램 매니페스트 및 *<http://adatum.com/Update/Path>* 해당URL은[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 업데이트를 확인 합니다.

    **Mage -Update HelloWorld.exe.application -ProviderUrl http://adatum.com/Update/Path**

3. 파일을 저장합니다.

   > [!NOTE]
   >  사용 하 여 파일에 다시 서명 해야 *Mage.exe*합니다. 자세한 내용은 [연습: 수동으로 ClickOnce 응용 프로그램을 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다.

## <a name="net-framework-security"></a>.NET Framework 보안
 CD와 같은 오프 라인 미디어의 응용 프로그램을 설치 하 고 컴퓨터를 온라인으로 하는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 먼저 확인 하 여 지정 된 URL을 `<deploymentProvider>` 업데이트 위치의 최신 버전이 있는지 확인 하려면 배포 매니페스트에서 태그를 응용 프로그램입니다. 그렇지 않으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 초기 설치 디렉터리에서 대신 여기에서 직접 응용 프로그램의 설치는 CLR (공용 언어 런타임) 응용 프로그램의 신뢰를 확인 하 고 사용 하 여 수준 `<deploymentProvider>`. 컴퓨터를 오프 라인 상태인 경우 또는 `<deploymentProvider>` 에 연결할 수 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 CD에서 CLR 설치 지점을 기준으로 신뢰를 부여 즉 CD 설치의 경우 응용 프로그램에 완전 신뢰가 부여 합니다. 이후의 모든 업데이트에는 해당 신뢰 수준을 상속 합니다.

 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 를 사용 하는 응용 프로그램 `<deploymentProvider>` 응용 프로그램에서 서로 다른 수준의 다른 컴퓨터에서 신뢰 수신 하지 않도록 해당 응용 프로그램 매니페스트에서 필요한 권한만 명시적으로 선언 해야 합니다.

## <a name="see-also"></a>참고자료
- [연습: 수동으로 ClickOnce 응용 프로그램 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
- [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)
- [ClickOnce 애플리케이션 보안](../deployment/securing-clickonce-applications.md)
- [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)