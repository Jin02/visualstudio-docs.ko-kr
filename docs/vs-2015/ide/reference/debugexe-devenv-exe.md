---
title: -DebugExe(devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f58db37f353cddd7444e7ea185dc07c0ec6cd603
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541879"
---
# <a name="debugexe-devenvexe"></a>/DebugExe(devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [-DebugExe (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/debugexe-devenv-exe)합니다.  
  
  
디버깅하도록 지정된 실행 파일을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>인수  
 `ExecutableFile`  
 필수. .exe 파일의 경로 및 파일 이름.  
  
 .exe 파일이 없거나 존재하지 않는 경우 경고 또는 오류가 표시되지 않고 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]이(가) 정상적으로 시작됩니다.  
  
## <a name="remarks"></a>설명  
 `ExecutableFile` 매개 변수 다음에 나오는 모든 문자열은 해당 파일에 인수로 전달됩니다.  
  
## <a name="example"></a>예제  
 다음 예제는 디버깅을 위해 `MyApplication.exe` 파일을 엽니다.  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)


