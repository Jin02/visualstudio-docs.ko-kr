---
title: 코어 뷰 범례 | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.cores.legend
helpviewer_keywords:
- Concurrency Visualizer, Cores View Legend
ms.assetid: e160384c-fcfe-49b3-86b7-229adb736c51
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6416b9bf96b3a23fce72df56190df9dfd5847531
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555981"
---
# <a name="cores-view-legend"></a>코어 뷰 범례
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [코어 뷰 범례](https://docs.microsoft.com/visualstudio/profiling/cores-view-legend)합니다.  
  
코어 뷰 범례는 색 및 이름으로 각 스레드를 식별합니다. 여기에는 코어 간 컨텍스트 전환 횟수, 총 컨텍스트 전환 및 코어 간 컨텍스트 전환 비율을 보여주는 열이 포함되어 있습니다. 범례의 행은 코어 간 컨텍스트 전환 횟수를 기준으로 내림차순으로 정렬됩니다.  
  
 범례에서 행을 선택하여 타임라인에 표시되는 스레드를 필터링할 수 있습니다. 선택한 스레드만 타임라인에 표시됩니다. 선택된 행이 없으면 타임라인에 모든 행이 표시됩니다.  
  
 코어 간 컨텍스트 전환은 동일한 논리적 코어에서 이뤄지는 전환보다 오버헤드 및 성능 비용이 높습니다. 컨텍스트 전환 중에는 프로세서 레지스터가 저장 및 복원되고, 운영 체제 커널 코드가 실행되며, 번역 내부 참조 버퍼 항목이 다시 로드되고 프로세서 파이프라인이 플러시됩니다. 코어 간 컨텍스트 전환은 캐시 데이터가 다른 코어에 있는 이 스레드에 대해 유효하지 않기 때문에 다른 컨텍스트 전환보다 비용이 높을 수 있습니다. 반면에, 스레드가 이전에 실행된 코어로 컨텍스트 전환되면 유용한 데이터가 캐시에 아직 있을 가능성이 있습니다. 스레드 선호도 관리를 위해 코어 간 컨텍스트 전환이 늘어나고, 성능이 저하될 때는 이 문제를 해결할지 여부를 고려해야 합니다. 먼저 스레드 선호도를 제거한 후 결과로 나타나는 코어 간 동작을 관찰합니다.  
  
 다음 표에서는 범례 요소에 대해 설명합니다.  
  
|요소|정의|  
|-------------|----------------|  
|스레드 이름|이전 코어 타임라인의 스레드 색 및 해당 스레드의 이름을 표시합니다.|  
|코어 간 컨텍스트 전환|논리 코어 간에 전환된 스레드에 대한 컨텍스트 전환 수입니다. 하나의 프로세서 다이에서 다른 프로세서 다이로 이동하는 코어 간 컨텍스트 스위치와 동일한 다이에 유지되는 코어 간 컨텍스트 전환은 구분되지 않습니다.|  
|전체 컨텍스트 전환|샘플링 기간 동안 지정된 스레드에 대한 컨텍스트 전환의 총 수입니다. 스레드가 컨텍스트를 변경할 때마다(예를 들어 실행에서 동기화로 변경) 한 번의 컨텍스트 전환으로 계산됩니다.|  
|코어 간 컨텍스트 전환 비율|코어 간 컨텍스트 전환 횟수를 총 컨텍스트 전환 수를 나눠 백분율로 계산합니다. 이 비율이 높을수록 이 특정 스레드의 성능에 대한 코어 간 컨텍스트 전환의 전반적인 오버헤드 영향이 커집니다.|  
  
## <a name="see-also"></a>참고 항목  
 [코어 뷰](../profiling/cores-view.md)


