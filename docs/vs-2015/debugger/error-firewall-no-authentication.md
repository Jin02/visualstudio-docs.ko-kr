---
title: '오류: 방화벽 인증 안 함 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eb963afb4a1cbc029ee8490a9c35d1b09e8c3338
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63447332"
---
# <a name="error-firewall-no-authentication"></a>오류: 방화벽 인증 안 함
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

원격 컴퓨터의 인터넷 연결 방화벽이 원격 디버깅을 허용하도록 설정되어 있지 않습니다. `No Authentication`을 사용하여 원격으로 디버깅하는 경우 msvsmon.exe가 예외 목록에 추가되어 있어야 합니다. 일부 IPSEC 포트를 열어야 할 수도 있습니다.  
  
> [!NOTE]
> 원격 디버거는 Windows 방화벽을 자동으로 구성할 수 있습니다. 타사 소프트웨어 방화벽이나 하드웨어 방화벽과 같은 Windows 방화벽 이외의 방화벽을 사용하는 경우 원격 디버깅을 허용하도록 방화벽을 수동으로 구성해야 합니다. 이렇게 하려면 msvsmon.exe가 수신 대기하는 TCP/IP 포트에서 트래픽을 허용합니다. 기본적으로 이러한 포트는 포트 4018 및 4019입니다. 4018은 모든 운영 체제에서 사용되고, 4019는 x86 프로세스의 디버깅을 허용하기 위해 Windows x64에서만 사용됩니다.  
  
 자세한 내용은 [설정 Up the Remote Tools 장치의](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)합니다.
