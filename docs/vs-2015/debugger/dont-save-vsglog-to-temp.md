---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 449c6c1ecdb0644b9b52b6ec12ce867dc34d66c4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985774"
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

그래픽 로그 파일이 사용자의 임시 파일 디렉터리에 저장되는지 여부를 존재로 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>값  
 존재 또는 부재를 그래픽 로그 파일을 사용 하는지 여부를 결정 하는 전처리기 기호는 사용자의 임시 파일 디렉터리에 저장 됩니다. 이 기호가 정의 된 경우 파일 이름을 정의한 `VSG_DEFAULT_RUN_FILENAME` 캡처된 앱의 현재 디렉터리에 상대적이 아니거나 절대 경로입니다; 그렇지 않으면 파일 이름을 정의한 `VSG_DEFAULT_RUN_FILENAME` 사용자의 임시 파일 디렉터리에 상대적 이며 일 수 없습니다 절대 경로입니다.  
  
## <a name="remarks"></a>설명  
 사용자의 권한에 따라 그래픽 로그 파일 못할 임의의 위치에 저장 합니다. 여부 선택 위치에 쓸 수는 사용자가 확실 하지 않은 경우 사용자의 임시 파일 디렉터리 또는 다른 알려진 올바른 위치에 그래픽 로그를 저장 하려면 선호 하는 것이 좋습니다.  
  
 그래픽 로그 파일 임시 파일 디렉터리에 저장 되 고을 방지 하려면 정의 해야 합니다 `DONT_SAVE_VSGLOG_TO_TEMP` 포함 하기 전에 `vsgcapture.h`입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 호스트 컴퓨터의 절대 경로를 그래픽 로그 파일을 저장 하는 방법을 보여 줍니다.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)
