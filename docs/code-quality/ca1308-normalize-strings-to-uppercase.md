---
title: 'CA1308: 대문자로 문자열을 정규화하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c33f4b0b55728d659c34e0ffc8723f555a6d074d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234923"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: 대문자로 문자열을 정규화하세요.

|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|범주|Microsoft.Globalization|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인
작업은 문자열을 소문자로 정규화 합니다.

## <a name="rule-description"></a>규칙 설명
문자열은 대문자로 정규화되어야 합니다. 소문자로 변환 된 작은 문자 그룹은 라운드트립을 수행할 수 없습니다. 라운드트립 하려면 문자 데이터를 다르게 나타내는 다른 로캘로 문자를 변환한 다음 변환 된 문자에서 원래 문자를 정확 하 게 검색 하는 것을 의미 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
문자열을 소문자로 변환 하는 작업을 변경 하 여 문자열을 대문자로 변환 합니다. 예를 들어, `String.ToLower(CultureInfo.InvariantCulture)`를 `String.ToUpper(CultureInfo.InvariantCulture)`로 변경합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
결과에 따라 보안을 결정 하지 않는 경우 (예: UI에 표시 되는 경우) 경고 메시지를 표시 하지 않는 것이 안전 합니다.

## <a name="see-also"></a>참고 항목
[전역화 경고](../code-quality/globalization-warnings.md)