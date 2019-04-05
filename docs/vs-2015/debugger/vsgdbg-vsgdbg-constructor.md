---
title: 'Vsgdbg:: Vsgdbg (생성자) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f3bd179aea7d961df6145b7af2f074927fcdc3e3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981279"
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg(생성자)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

그래픽 진단의 사용자 앱 구성 요소를 준비하거나 준비하지 않고 `VsgDbg` 클래스의 인스턴스를 생성하여 지정된 Boolean 매개 변수에 따라 그래픽 정보를 캡처하고 기록합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bDefaultInit`  
 그래픽 정보를 캡처하고 기록하기 위해 그래픽 진단의 사용자 앱 구성 요소가 준비되도록 지정하려면 `true`이고, 이번에 그래픽 정보를 캡처하고 기록하기 위해 앱을 준비해서는 안 되도록 지정하려면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여 생성자가 호출 하는 경우 `bDefaultInit` 로 설정 `true`, 그래픽 로그 파일의 파일 이름 방식에 따라 결정 됩니다 `DONT_SAVE_VSGLOG_TO_TEMP` 하 고 `VSG_DEFAULT_RUN_FILENAME` 하기 전에 정의 된 전처리기 기호 `vsgcapture.h` 앱에 포함 됩니다.  
  
 `bDefaultInit`이 `false`로 설정된 상태로 생성자가 호출되면 `Init` 함수를 호출하여 나중에 그래픽 정보를 캡처하고 기록하도록 그래픽 진단의 사용자 앱 구성 요소를 준비할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [VsgDbg::~VsgDbg(소멸자)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init](../debugger/init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)
