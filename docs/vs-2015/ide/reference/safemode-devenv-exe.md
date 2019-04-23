---
title: -SafeMode(devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94e8e87f4440644f76906a70ea09a46282b109c2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670357"
---
# <a name="safemode-devenvexe"></a>/SafeMode(devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

안전 모드에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]을(를) 시작하고 기본 환경 및 서비스만 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>주의  
 이 스위치는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]이(가) 시작될 때 모든 타사 VSPackages의 로드를 차단하므로 안정적으로 실행되도록 합니다.  
  
## <a name="description"></a>설명  
 다음 예제에서는 안전 모드에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]을(를) 시작합니다.  
  
## <a name="code"></a>코드  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
