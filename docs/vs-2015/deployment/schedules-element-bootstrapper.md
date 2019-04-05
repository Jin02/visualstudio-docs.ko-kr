---
title: '&lt;일정&gt; 요소 (부트스트래퍼) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 85ffab2272a55bfe77c5f2a73c6e25967a203c85
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981764"
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;일정&gt; 요소 (부트스트래퍼)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Schedules` 요소에 포함 되어 `Schedule` 특정 시간의 정의한 명령 정의 하는 요소는 `Command` 요소를 실행 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Schedules>  
    <Schedule  
        Name  
    >  
        <BuildList />  
        <BeforePackage />  
        <AfterPackage />  
    </Schedule>  
</Schedules>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 합니다 `Schedules` 요소인 자식은 `Product` 요소입니다. 각 `Product` 요소 하나만 있을 `Schedules` 요소입니다. `Schedules` 요소에는 특성이 없습니다.  
  
## <a name="schedule"></a>일정  
 합니다 `Schedule` 요소인 자식은 `Schedules` 요소입니다. A `Schedules` 요소 하나 이상이 있어야 `Schedule` 요소입니다.  
  
 `Schedule` 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수 요소. 일정 항목의 이름입니다. 이에 해당 합니다 `ScheduleName` 의 속성을 `Command` 요소. 경우는 `Command` 명명 된 일정을 참조 하 여 지정한 시간에만 실행 된다는 것 `Schedule` 요소입니다. 일정와 연결 될 수도 합니다 `FailIf` 및 `BypassIf` 지정된 된 일정에서 실행 하려면 이러한 조건부 테스트를 제한 하는 요소입니다. 자세한 내용은 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
  
 지정 된 `Schedule` 요소는 다음과 같은 자식이 하나만 있을 수 있습니다.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` 요소 설치 관리자를 부트스트래핑 응용 프로그램을 시작한 후에 즉시 명령을 실행 하도록 지시 합니다.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` 요소 설치 관리자를 지정된 된 패키지를 설치 하기 전에 명령을 실행 하도록 지시 합니다.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` 요소 설치 관리자를 지정된 된 패키지를 설치한 후 명령을 실행 하도록 지시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<제품 > 요소](../deployment/product-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)
