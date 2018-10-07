---
title: 프로파일링 도구 사용 규칙 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d508fdfe1845a75f0ef7e0ba36730afbaa4e157
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555891"
---
# <a name="profiling-tools-usage-rules"></a>프로파일링 도구 사용 규칙
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [프로 파일링 도구 사용 규칙](https://docs.microsoft.com/visualstudio/profiling/profiling-tools-usage-rules)합니다.  
  
프로파일링 도구 사용 범주의 성능 규칙은 프로파일러를 사용하여 데이터를 가장 효율적으로 수집하기 위한 지침을 제공합니다.  
  
|||  
|-|-|  
|[DA0002: VSPerfCorProf.dll이 없습니다.](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|명령줄 프로파일링에 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 이진 파일에 대한 불완전한 데이터가 포함되어 있을 수 있습니다. 올바른 환경 변수를 설정하지 않은 경우 이러한 현상이 발생할 수 있습니다.|  
|[DA0003: 커널 샘플이 많습니다.](../profiling/da0003-many-kernel-samples.md)|대상 이진 파일 실행 외부에서 발생한 여러 프로파일링 샘플이 기록되었습니다. 보다 정확한 데이터를 수집하려면 계측 방법을 사용해 보세요.|  
|[DA0004: 프로세서 사용률이 높습니다.](../profiling/da0004-high-processor-usage.md)|프로파일링 데이터에서 프로파일링 실행 중에 프로세서의 사용량이 계속 많았음을 나타내고 있습니다. 보다 정확한 데이터를 수집하려면 샘플링 방법을 사용해 보세요.|  
|[DA0008: 수집되는 샘플 수가 적습니다.](../profiling/da0008-few-samples-collected.md)|프로파일링 실행에서 수집되는 샘플의 수가 통계적으로 중요할 만큼 충분하지 않습니다. 다시 프로파일링하고 더 오랫동안 응용 프로그램을 실행해 보세요. 계측 방법을 사용하여 데이터를 수집할 수도 있습니다.|  
|[DA0026: 커널 CPU 시간 처리 수준이 너무 높습니다.](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|프로파일링 실행에서 상당 시간이 프로세서 커널 모드에서 소요되었습니다. 시간을 기준으로 사용하는 대신 시스템 호출을 기준으로 사용하여 샘플링해 보세요.|  
|[DA0029: 지원되지 않는 CLR 버전입니다.](../profiling/da0029-unsupported-clr-version.md)|프로파일링된 이진 파일이 프로파일러가 지원하지 않는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전을 사용하고 있습니다. 프로파일러 보고서는 기호 이름을 확인할 수 없습니다.|  
|[DA0030: 데이터베이스 개체의 계층 상호 작용 측정값을 수집하십시오.](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|<xref:System.Data?displayProperty=fullName> 네임스페이스에서 메서드에 대한 많은 수의 호출이 수집되었습니다. 데이터베이스 호출에 대한 데이터를 포함하려면 프로파일 실행에서 계층 상호 작용 데이터를 수집해 보세요.|


