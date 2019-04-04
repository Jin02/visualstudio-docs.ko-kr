---
title: 'ASP.NET 디버깅: 시스템 요구 사항 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 455ed4c8fc4129c4e21123d359a088f6eac5cfca
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604967"
---
# <a name="aspnet-debugging-system-requirements"></a>ASP.NET 디버깅: 시스템 요구 사항
이 항목에서는 다음과 같은 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 디버깅 시나리오에 대한 소프트웨어 및 보안 요구 사항을 설명합니다.

- 로컬 디버깅: [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 와 웹 애플리케이션이 동일한 컴퓨터에서 실행됩니다. 이 시나리오에는 다음 두 가지 경우가 있습니다.

  - [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 코드가 파일 시스템에 상주하는 경우

  - [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 코드가 IIS 웹 사이트에 상주하는 경우

- 원격 디버깅: [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 클라이언트 컴퓨터에서 실행되며 원격 서버 컴퓨터에서 실행되는 웹 애플리케이션을 디버깅합니다.

## <a name="security-requirements"></a>보안 요구 사항
 원격 디버깅을 수행하려면 로컬 및 원격 컴퓨터가 도메인 설정 또는 작업 그룹 설정에 있어야 하며,

 디버깅 하는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스 (응용 프로그램 풀에서 호스트 됨) 해당 프로세스를 디버깅할 수 있는 권한이 있어야 합니다. 기본적으로 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] IIS 6.0 이전 응용 프로그램으로 실행 합니다 **ASPNET** 사용자입니다. IIS 6.0 및 IIS 7.0에는 **네트워크 서비스** 계정이 기본값. 작업자 프로세스가 **ASPNET**또는 **NETWORK SERVICE**로 실행되는 경우 이 프로세스를 디버깅하려면 관리자 권한이 필요합니다.

 > [!IMPORTANT]
 > Windows Server 2008 R2부터 좋습니다 사용 합니다 [ApplicationPoolIdentity](/iis/manage/configuring-security/application-pool-identities) 각 응용 프로그램 풀의 id로 합니다.

 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스의 이름은 디버깅 시나리오와 IIS 버전에 따라 다릅니다. 자세한 내용은 [방법: ASP.NET 프로세스의 이름 찾기](../debugger/how-to-find-the-name-of-the-aspnet-process.md)을 참조하세요.

 IIS를 실행 중인 서버의 machine.config 파일을 편집하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스를 실행하는 사용자 계정을 변경할 수 있습니다. **IIS(인터넷 정보 서비스) 관리자**를 사용하여 이 작업을 수행하는 것이 가장 좋습니다. 자세한 내용은 [방법:는 작업자 프로세스 사용자 계정으로 실행](../debugger/how-to-run-the-worker-process-under-a-user-account.md)합니다.

 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스가 고유한 사용자 계정에서 실행되도록 변경하는 경우에는 IIS를 실행하는 서버의 관리자가 아니어도 됩니다.

> [!CAUTION]
>  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스가 다른 계정에서 실행되도록 변경하기 전에 해당 계정에서 실행되는 동안 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스가 해킹될 경우의 가능한 결과를 고려하십시오. ASPNET 및 NETWORK SERVICE 사용자 계정은 최소 권한으로 실행되므로 프로세스가 해킹되는 경우 가능한 손실을 줄일 수 있습니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스가 보다 많은 권한을 가진 계정에서 실행되도록 변경해야 하는 경우에는 더 큰 손실이 발생할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [ASP.NET 애플리케이션 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [방법: 사용자 계정으로 작업자 프로세스 실행](../debugger/how-to-run-the-worker-process-under-a-user-account.md)