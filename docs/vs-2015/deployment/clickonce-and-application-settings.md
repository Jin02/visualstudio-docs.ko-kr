---
title: ClickOnce 및 응용 프로그램 설정 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, application settings
ms.assetid: 891caba6-faef-4a3c-8f71-60e6fadb60eb
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 07be583099627bbff4f67a4c040f4c44ddbc6224
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "58971932"
---
# <a name="clickonce-and-application-settings"></a>ClickOnce 및 응용 프로그램 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows Forms에 대 한 응용 프로그램 설정을 쉽게 만들고, 저장 및 사용자 지정 응용 프로그램 및 클라이언트에서 사용자 기본 설정을 유지 합니다. 다음 문서에는 ClickOnce 응용 프로그램에서는 응용 프로그램 설정 파일을 작업 하는 방법 및 다음 버전으로 업그레이드 하는 경우 ClickOnce가 설정을 마이그레이션하는 방법을 설명 합니다.  
  
 아래 정보는 기본 응용 프로그램 설정 공급자에만 적용 됩니다는 <xref:System.Configuration.LocalFileSettingsProvider> 클래스입니다. 사용자 지정 공급자를 제공 하는 경우 해당 공급자는 해당 데이터를 저장 하는 방법 및 설정 버전 간에 업그레이드 하는 방법을 결정 합니다. 응용 프로그램 설정 공급자에 대 한 자세한 내용은 참조 하세요. [응용 프로그램 설정 아키텍처](http://msdn.microsoft.com/library/c8eb2ad0-fac6-4ea2-9140-675a4a44d562)합니다.  
  
## <a name="application-settings-files"></a>응용 프로그램 설정 파일  
 두 파일을 사용 하는 응용 프로그램 설정: *앱*. exe.config 및 user.config, 여기서 *앱* Windows Forms 응용 프로그램의 이름입니다. user.config 응용 프로그램에 사용자 범위 설정을 저장 하는 클라이언트에 처음으로 생성 됩니다. *앱*..exe.config 반면가 배포 하기 전에 설정에 대 한 기본값을 정의 하는 경우. Visual Studio는이 파일을 자동으로 포함 사용 하는 경우 해당 **게시** 명령입니다. 이 파일은 포함 되어 있는지 확인 해야 Mage.exe 또는 MageUI.exe를 사용 하는 ClickOnce 응용 프로그램을 만드는 경우 응용 프로그램의 다른 파일을 응용 프로그램 매니페스트를 채울 때.  
  
 ClickOnce를 사용 하는 응용 프로그램의 배포 되지 않은 Windows Forms 응용 프로그램에서 *앱*. exe.config 파일은 user.config 파일은 사용자에 저장 하는 동안 응용 프로그램 디렉터리에 저장 **Documents and Settings**  폴더입니다. ClickOnce 응용 프로그램에서는 *앱*. exe.config ClickOnce 응용 프로그램 캐시 내에서 응용 프로그램 디렉터리에 있으며 해당 응용 프로그램에 대 한 ClickOnce 데이터 디렉터리에서 user.config 상주 합니다.  
  
 응용 프로그램을 배포 하는 방법에 관계 없이 응용 프로그램 설정에 안전 하 게 읽기 액세스를 보장 *앱*..exe.config 이며 user.config 안전 하 게 읽기/쓰기 액세스 합니다.  
  
 ClickOnce 응용 프로그램에서는 응용 프로그램 설정에서 사용 하는 구성 파일의 크기는 ClickOnce 캐시의 크기에 따라 제한 됩니다. 자세한 내용은 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)합니다.  
  
## <a name="version-upgrades"></a>버전 업그레이드  
 ClickOnce 응용 프로그램의 각 버전은 다른 모든 버전에서 격리, 처럼 ClickOnce 응용 프로그램에 대 한 응용 프로그램 설정도 다른 버전에 대 한 설정을 격리 됩니다. 사용자 응용 프로그램의 이후 버전으로 업그레이드 하는 경우 응용 프로그램 설정 병합 설정 새 설정 파일 집합으로 확인 하 고 업데이트 된 버전을 사용 하 여 제공 된 설정에 대해 최신 (가장 높은 번호) 버전의 설정을 비교 합니다.  
  
 다음 표에서 응용 프로그램 설정을 복사 하는 설정을 결정 하는 방법 설명.  
  
|변경 형식|업그레이드 작업|  
|--------------------|--------------------|  
|설정에 추가할 *앱*. exe.config|현재 버전의 새 설정을 병합할 *앱*. exe.config|  
|설정에서 제거 *앱*. exe.config|현재 버전의 기존 설정이 제거 될 *앱*. exe.config|  
|설정의 기본값 변경 로컬 설정은 여전히 user.config에서 원래 기본으로 설정합니다.|설정 값으로 새 기본값을 사용 하 여 현재 버전의 user.config에 병합 됩니다.|  
|설정의 기본값 변경 기본이 아닌에서 user.config 설정합니다.|설정은 유지 하는 기본값이 아닌 값을 사용 하 여 현재 버전의 user.config에 병합 됩니다.|  
  
 있습니다 사용자 고유의 응용 프로그램 설정 래퍼 클래스를 만들고 업데이트 논리 사용자 지정 하려는 경우 재정의할 수 있습니다는 <xref:System.Configuration.ApplicationSettingsBase.Upgrade%2A> 메서드.  
  
## <a name="clickonce-and-roaming-settings"></a>ClickOnce 및 로밍 설정  
 ClickOnce 작동 하지 않습니다 로밍 설정을 사용 하 여 네트워크의 컴퓨터에서 수행 되도록 설정 파일을 수 있습니다. 로밍 설정에 필요한 경우 네트워크를 통해 설정을 저장 하는 응용 프로그램 설정 공급자를 구현 하거나 원격 컴퓨터에 설정을 저장 하기 위한 사용자 고유의 사용자 지정 설정 클래스를 개발 해야 합니다. 설정 공급자에 대 한 자세한 내용은 참조 하세요. [응용 프로그램 설정 아키텍처](http://msdn.microsoft.com/library/c8eb2ad0-fac6-4ea2-9140-675a4a44d562)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [애플리케이션 설정 개요](http://msdn.microsoft.com/library/0dd8bca5-a6bf-4ac4-8eec-5725d08b38dc)   
 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)   
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)
