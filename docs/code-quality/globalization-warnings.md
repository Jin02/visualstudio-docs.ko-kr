---
title: 전역화 경고
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- warnings, globalization
- globalization warnings
- globalization [Visual Studio], warnings
- managed code analysis warnings, globalization warnings
ms.assetid: a8d12d41-14bf-4b43-af24-168312d7c390
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fecc46ac6e1221cb547e98711d95b743010d4c6c
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75587578"
---
# <a name="globalization-warnings"></a>전역화 경고
세계화 경고는 전 세계에서 사용할 수 있는 라이브러리 및 응용 프로그램을 지원 합니다.

## <a name="in-this-section"></a>섹션 내용

|규칙|설명|
|----------|-----------------|
|[CA1300: MessageBoxOptions를 지정하십시오.](../code-quality/ca1300.md)|오른쪽에서 왼쪽으로 읽기 순서를 사용하는 문화권에 대해 메시지 상자를 올바로 표시하려면 MessageBoxOptions 열거형의 RightAlign 및 RtlReading 멤버를 Show 메서드로 전달해야 합니다.|
|[CA1301: 중복 액셀러레이터 키를 사용하지 마십시오.](../code-quality/ca1301.md)|액셀러레이터 키라고도 하는 선택키를 사용하면 Alt 키를 사용하여 키보드로 컨트롤에 액세스할 수 있습니다. 여러 컨트롤에 중복 된 액세스 키가 있는 경우에는 액세스 키의 동작이 제대로 정의 되지 않습니다.|
|[CA1302: 로캘별 문자열을 하드 코딩하지 마십시오.](../code-quality/ca1302.md)|System.Environment.SpecialFolder 열거형에는 특수 시스템 폴더를 참조하는 멤버가 포함되어 있습니다. 이러한 폴더의 위치는 운영 체제에 따라 값이 다를 수 있으며, 사용자가 위치 일부를 변경할 수 있고, 위치는 지역화됩니다. Environment. GetFolderPath 메서드는 현재 실행 중인 컴퓨터에 적합 한, 지역화 된 System.environment.specialfolder 열거형과 연결 된 위치를 반환 합니다.|
|[CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.](../code-quality/ca1303.md)|외부에서 볼 수 있는 메서드는 문자열 리터럴을 .NET 생성자 또는 메서드에 대 한 매개 변수로 전달 하 고 해당 문자열을 지역화할 수 있어야 합니다.|
|[CA1304: CultureInfo를 지정하십시오.](../code-quality/ca1304.md)|메서드 또는 생성자가 System.Globalization.CultureInfo 매개 변수를 받아들이는 오버로드가 있는 멤버를 호출하지만 CultureInfo 매개 변수를 사용하는 오버로드는 호출하지 않습니다. CultureInfo 또는 System.IFormatProvider 개체가 제공되지 않으면 오버로드된 멤버에서 제공하는 기본값이 모든 로캘에서 원하는 효과를 나타내지 않을 수 있습니다.|
|[CA1305: IFormatProvider를 지정하십시오.](../code-quality/ca1305.md)|메서드 또는 생성자가 System.IFormatProvider 매개 변수를 받아들이는 오버로드가 있는 하나 이상의 멤버를 호출하지만 IFormatProvider 매개 변수를 사용하는 오버로드는 호출하지 않습니다. System.Globalization.CultureInfo 또는 IFormatProvider 개체가 제공되지 않으면 오버로드된 멤버에서 제공하는 기본값이 모든 로캘에서 원하는 효과를 나타내지 않을 수 있습니다.|
|[CA1306: 데이터 형식에 맞는 로캘을 설정하십시오.](../code-quality/ca1306.md)|로캘은 숫자 값에 사용되는 서식, 통화 기호 및 정렬 순서 등과 같은 데이터의 문화권별 표현 요소를 결정합니다. DataTable 또는 DataSet를 만들 때는 로캘을 명시적으로 설정해야 합니다.|
|[CA1307: StringComparison을 지정하십시오.](../code-quality/ca1307.md)|문자열 비교 작업에서 StringComparison 매개 변수를 설정하지 않는 메서드 오버로드를 사용합니다.|
|[CA1308: 문자열을 대문자로 정규화하십시오.](../code-quality/ca1308.md)|문자열은 대문자로 정규화되어야 합니다. 일부 문자는 소문자로 변환될 때 다시 대문자로 변환될 수 없습니다.|
|[CA1309: 서수 StringComparison을 사용하십시오.](../code-quality/ca1309.md)|비언어 문자열 비교 작업에서는 StringComparison 매개 변수를 Ordinal 또는 OrdinalIgnoreCase로 설정하지 않습니다. 매개 변수가 명시적으로 StringComparison.Ordinal 또는 StringComparison.OrdinalIgnoreCase로 설정되기 때문에 코드 실행 속도, 정확도 및 신뢰도가 향상됩니다.|
|[CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정합니다.](../code-quality/ca2101.md)|플랫폼 호출 멤버는 부분적으로 신뢰할 수 있는 호출자를 허용 하 고 문자열 매개 변수를 포함 하며 문자열을 명시적으로 마샬링할 수 없습니다. 이렇게 하면 보안상 위험할 수 있습니다.|
