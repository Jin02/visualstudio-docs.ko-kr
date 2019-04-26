---
title: IP(명령 포인터) 뷰 - 샘플링 데이터 | Microsoft 문서
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 579887c22df16d555c3f309b4326740060aefc1f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442229"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>IP(명령 포인터) 뷰 - 샘플링 데이터
샘플링 데이터의 IP 뷰에는 프로파일링 실행 시 샘플이 수집될 때 직접 실행되고 있던 어셈블리 명령에 대한 성능 데이터가 나열됩니다.

> [!NOTE]
> Windows 8 및 Windows Server 2012의 강화된 보안 기능을 위해 Visual Studio 프로파일러가 이러한 플랫폼에서 데이터를 수집하는 방법을 상당히 변경해야 했습니다. 또한 UWP 앱에는 새로운 수집 기술도 필요합니다. [Windows 8 및 Windows Server 2012 애플리케이션의 성능 도구](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하세요.

|열|설명|
|------------|-----------------|
|**프로세스 ID**|프로파일링 실행의 PID(프로세스 ID)입니다.|
|**프로세스 이름**|프로세스의 이름입니다.|
|**모듈 이름**|명령이 포함된 모듈의 이름입니다.|
|**모듈 경로**|명령이 포함된 모듈의 경로입니다.|
|**소스 파일**|명령이 포함된 소스 파일입니다.|
|**함수 이름**|명령이 포함된 함수의 이름입니다.|
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|
|**함수 주소**|로드된 이진에서 함수의 시작 메모리 주소입니다.|
|**소스 줄 시작**|소스 파일에서 이 샘플이 수집된 시작 줄 번호입니다.|
|**소스 줄 끝**|소스 파일에서 이 샘플이 수집된 끝 줄 번호입니다.|
|**소스 문자 시작**|소스 파일 줄에서 이 샘플이 수집된 시작 문자의 오프셋입니다.|
|**소스 문자 끝**|소스 파일 줄에서 이 샘플이 수집된 끝 문자의 오프셋입니다.|
|**명령 주소**|로드된 이진에 있는 명령의 주소입니다.|
|**전용 샘플**|명령이 실행될 때 수집된 샘플의 총 수입니다.|
|**전용 샘플 비율(%)**|프로파일링 실행 시 명령이 실행될 때 수집된 모든 샘플의 백분율입니다.|

## <a name="see-also"></a>참고 항목
- [IP(명령 포인터) 뷰 - 샘플링](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)