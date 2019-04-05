---
title: 소스 서버 보안 경고 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 76d61520bf17ad3230a437c295de387a910f808f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58971192"
---
# <a name="source-server-security-alert"></a>소스 서버 보안 경고
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

소스 서버를 사용할 경우 알 수 있고 신뢰할 수 있는 위치의 기호 파일만 사용합니다.  
  
 이 경고는 소스 서버 지원을 사용하는 경우에 나타납니다. 소스 서버 명령은 디버그 기호 파일(PDB 파일)에 포함되어 있습니다. PDB 파일의 출처를 확인해야 합니다.  
  
> [!IMPORTANT]
>  원본 서버를 사용 하는 경우 잠재적인 보안 위협은 계정 점을 고려해 야 합니다. 임의의 명령이 응용 프로그램의 PDB 파일에 포함 될 수 있습니다, 그리고 따라서 srcsrv.ini 파일에 실행 하려는 항목만 배치 해야 합니다. srcsvr.ini 파일에 포함되지 않은 명령을 실행하려고 하면 확인 대화 상자가 나타납니다. 자세한 내용은 참조 하세요. [보안 경고: 디버거가 신뢰할 수 없는 명령을 실행 해야 합니다](../debugger/security-warning-debugger-must-execute-untrusted-command.md)합니다. 명령 매개 변수 없는 유효성 검사가 수행 되는지, 수 없으므로 신뢰할 수 있는 명령을 사용 하 여 주의 해야 합니다. 예를 들어 cmd.exe를 신뢰한 경우 악의적인 사용자가 이 명령을 위험하게 만드는 매개 변수를 지정할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기호 파일(.pdb) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [디버거 보안](../debugger/debugger-security.md)   
 [원본 서버](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)
