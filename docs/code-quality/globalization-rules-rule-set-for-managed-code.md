---
title: 관리 코드에 대한 전역화 규칙 규칙 집합
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 28199eb9fa09e2096939ffa8e678eb9812a61b1f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62816402"
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>관리 코드에 대한 전역화 규칙 규칙 집합
Microsoft 전역화 규칙 규칙 집합 다른 언어, 로캘 및 문화권에서 올바르게 표시 응용 프로그램에서 데이터를 방해할 수 있는 문제에 초점을 사용할 수 있습니다. 응용 프로그램 전역화, 지역화 된 경우이 규칙 집합 또는 둘 다 포함 해야 합니다.

|규칙|설명|
|----------|-----------------|
|[CA1300](../code-quality/ca1300-specify-messageboxoptions.md)|MessageBoxOptions를 지정하세요.|
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|중복 액셀러레이터 키를 사용하지 마십시오.|
|[CA1302](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|로캘별 문자열을 하드코드하지 마세요.|
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|리터럴을 지역화된 매개 변수로 전달하지 마세요.|
|[CA1304](../code-quality/ca1304-specify-cultureinfo.md)|CultureInfo를 지정하세요.|
|[CA1305](../code-quality/ca1305-specify-iformatprovider.md)|IFormatProvider를 지정하세요.|
|[CA1306](../code-quality/ca1306-set-locale-for-data-types.md)|데이터 형식에 맞는 로캘을 설정하세요.|
|[CA1307](../code-quality/ca1307-specify-stringcomparison.md)|StringComparison 지정하세요.|
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|대문자로 문자열을 정규화하세요.|
|[CA1309](../code-quality/ca1309-use-ordinal-stringcomparison.md)|서수 StringComparison을 사용하세요.|
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.|