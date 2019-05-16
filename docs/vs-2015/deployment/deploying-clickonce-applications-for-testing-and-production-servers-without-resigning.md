---
title: 테스트에 대 한 ClickOnce 응용 프로그램을 배포 하 고 다시 서명 하지 않고 프로덕션 서버 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, deploying without resigning
- ClickOnce deployment, without resigning
- application updates, ClickOnce
- update location [ClickOnce]
- deploymentProvider tag
- manifests [ClickOnce]
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2a65f2e39eac5889b287b082b4cad6842f44aa2e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65675542"
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>다시 서명하지 않고 테스트 및 프로덕션 서버용 ClickOnce 응용 프로그램 배포
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목에서는 clickonce 매니페스트 다시 서명 하거나 ClickOnce를 변경 하지 않고 여러 네트워크 위치에서 ClickOnce 응용 프로그램 배포를 사용할 수 있는 버전 3.5는.NET Framework에 도입 된 새로운 기능을 설명 합니다.  
  
> [!NOTE]
> 새 버전의 응용 프로그램을 배포 하기 위한 기본 방법은 그대로 다시 서명 합니다. 가능 하면 서명 메서드를 사용 합니다. 자세한 내용은 [Mage.exe(매니페스트 생성 및 편집 도구)](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)를 참조하세요.  
  
 타사 개발자 및 Isv에서 옵트인이 기능에 쉽게 고객이 응용 프로그램을 업데이트 합니다. 다음과 같은 상황에서이 기능을 사용할 수 있습니다.  
  
- 응용 프로그램을 응용 프로그램의 첫 번째 설치 되지 않습니다 업데이트 하는 경우.  
  
- 컴퓨터에서 응용 프로그램의 구성 하나만 있으면 됩니다. 예를 들어, 서로 다른 두 데이터베이스를 가리키도록 구성 된 응용 프로그램을 하는 경우에이 기능을 사용할 수 없습니다.  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>배포 매니페스트에 deploymentProvider 제외  
 .NET Framework 2.0 및.NET Framework 3.0에서 오프 라인 가용성을 위해 시스템에 설치 하는 ClickOnce 응용 프로그램 지정 해야 합니다는 `deploymentProvider` 배포 매니페스트에서 합니다. `deploymentProvider` 업데이트 위치; 라고도 ClickOnce는 응용 프로그램 업데이트를 확인 하는 위치입니다. 이 요구 사항으로 해당 배포에 서명 하도록 응용 프로그램 게시자에 대 한 필요와 결합 되어 공급 업체 또는 다른 제 3 자에서 ClickOnce 응용 프로그램을 업데이트 하는 회사 어려웠습니다. 하기가 동일한 네트워크의 여러 위치에서 동일한 응용 프로그램을 배포 하기가 더 어렵습니다.  
  
 .NET Framework 3.5에서 ClickOnce에 대 한 변경 내용으로 다음 자체 네트워크에서 응용 프로그램을 배포할 수 있는 다른 조직에 ClickOnce 응용 프로그램을 제공 하는 제 3 자에 대 한 가능성이 있습니다.  
  
 이 기능을 활용 하기 위해 ClickOnce 응용 프로그램 개발자는 제외 해야 `deploymentProvider` 해당 배포에서 매니페스트 합니다. 즉, 제외 합니다 `-providerUrl` Mage.exe 또는 확인을 사용 하 여 매니페스트 배포를 만들 때 인수를 **시작 위치** 텍스트 상자에는 **응용 프로그램 매니페스트** 탭 비어 경우 있습니다 MageUI.exe 사용 하 여 배포 매니페스트를 생성 됩니다.  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider 및 응용 프로그램 업데이트  
 .NET Framework 3.5 부터는 더 이상 지정 해야는 `deploymentProvider` 온라인 및 오프 라인 사용에 대 한 ClickOnce 응용 프로그램을 배포 하려면 배포 매니페스트에 합니다. 이 패키지를 직접 배포에 서명 하며 해당 네트워크를 통해 응용 프로그램을 배포 하도록 다른 회사를 허용 해야 하는 시나리오를 지원 합니다.  
  
 점을 기억해 야 합니다를 제외 하는 응용 프로그램을 `deploymentProvider` 포함 된 업데이트를 제공 될 때까지 업데이트 하는 동안 해당 설치 위치를 변경할 수 없습니다는 `deploymentProvider` 다시 태그입니다.  
  
 이 시점을 명확 하 게 두 가지 예는 다음과 같습니다. 첫 번째 예에서는 되지 않는 ClickOnce 응용 프로그램을 게시할 `deploymentProvider` 와 같은 태그에서 설치 하는 사용자 요청 http://www.adatum.com/MyApplication/합니다. 응용 프로그램의 다음 업데이트를 게시 하려는 경우 결정 http://subdomain.adatum.com/MyApplication/에 있는 배포 매니페스트의이 나타내는 방법이 해야 http://www.adatum.com/MyApplication/합니다. 두 가지 중 하나를 수행할 수 있습니다.  
  
- 이전 버전을 제거 하려면 사용자에 게 알릴 하 고 새 위치에서 새 버전을 설치 합니다.  
  
- 에 대 한 업데이트를 포함 http://www.adatum.com/MyApplication/ 포함 하는 한 `deploymentProvider` 가리키는 http://www.adatum.com/MyApplication/합니다. 그런 다음 사용 하 여 나중에 다른 업데이트를 릴리스 `deploymentProvider` 가리키는 http://subdomain.adatum.com/MyApplication/합니다.  
  
  두 번째 예제에서는 지정 하는 ClickOnce 응용 프로그램을 게시할 `deploymentProvider`, 후 제거 하려는 경우. 사용 하지 않는 새 버전에 한 번 `deploymentProvider` 다운로드 한 클라이언트에 됩니다 응용 프로그램의 버전을 해제할 때까지 업데이트를 사용 하는 경로 리디렉션할 수 `deploymentProvider` 복원 합니다. 첫 번째 예제에서와 마찬가지로 `deploymentProvider` 현재 업데이트 위치를 새 위치가 아니라 처음 가리켜야 합니다. 삽입 하려고 하면이 경우는 `deploymentProvider` 을 참조 하는 http://subdomain.adatum.com/MyApplication/, 다음 업데이트에 실패 합니다.  
  
## <a name="creating-a-deployment"></a>배포 만들기  
 다른 네트워크 위치에서 배포할 수 있는 배포를 만드는 단계별 지침을 참조 하세요. [연습: 다시 서명 하는 필요가 없고 브랜드 정보가 유지 되는 ClickOnce 응용 프로그램 수동 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required?view=vs-2015)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)   
 [MageUI.exe (매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](https://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14)
