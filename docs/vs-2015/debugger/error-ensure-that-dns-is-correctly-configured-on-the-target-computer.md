---
title: '오류: 대상 컴퓨터에서 DNS가 올바르게 구성 되어 있는지 확인 하십시오. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2d364caf-73af-4186-bf9b-af186331cbe8
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 35c258a018bec8bd38f8b43690c18b37ee9d6c39
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75851927"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>오류: 대상 컴퓨터에서 DNS가 올바르게 구성되었는지 확인하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

원격으로 디버깅할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 이 오류는 대상 컴퓨터가 Visual Studio 디버거 호스트 컴퓨터의 이름을 확인할 수 없는 경우에 발생합니다. 대상 컴퓨터의 DNS 설정을 확인하십시오.  
  
- Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 또는 Windows Server 2008 R2에서 DNS 설정을 확인하는 방법을 보려면 **시작** 메뉴에서 **도움말 및 지원**을 선택하고 **TCP/IP 설정 변경**을 검색하세요.  
  
- 자세한 내용은 [Microsoft Windows 웹 사이트](https://windows.microsoft.com/)를 방문하거나 **TCP/IP 설정 변경**을 검색하세요.  
  
  DNS 문제를 해결할 수 없는 경우 다른 계정으로 원격 디버거를 실행해 볼 수 있습니다. 이 오류는 로컬 시스템 또는 네트워크 서비스 계정으로 원격 디버거를 실행하는 경우에만 발생합니다. 다른 계정으로 원격 디버거를 실행하는 경우 DNS를 요구하지 않는 NTLM 인증을 사용할 수 있습니다. 의 기본 클래스입니다. 절차에 대 한 자세한 내용은 [오류: 대상 컴퓨터의 Visual Studio 원격 디버거 서비스가이 컴퓨터에 다시 연결할 수 없습니다](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
