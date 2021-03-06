---
title: 'CA1306: 데이터 형식에 대 한 로캘 설정 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: edd1d6a7623f96f03403883ee2585d245414bb3b
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85539024"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: 데이터 형식에 맞는 로캘을 설정하세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|항목|값|
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|범주|Microsoft 세계화|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 메서드나 생성자가 하나 이상의 <xref:System.Data.DataTable?displayProperty=fullName> 또는 인스턴스를 만들었으며 <xref:System.Data.DataSet?displayProperty=fullName> 로캘 속성 ( <xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> 또는)을 명시적으로 설정 하지 않은 <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName> 경우

## <a name="rule-description"></a>규칙 설명
 로캘은 숫자 값, 통화 기호 및 정렬 순서에 사용 되는 형식 지정과 같이 데이터에 대 한 문화권별 프레젠테이션 요소를 결정 합니다. 또는를 만들 때는 <xref:System.Data.DataTable> <xref:System.Data.DataSet> 로캘을 명시적으로 설정 해야 합니다. 기본적으로 이러한 형식의 로캘은 현재 문화권입니다. 데이터베이스 또는 파일에 저장 되 고 전역적으로 공유 되는 데이터의 경우에는 일반적으로 로캘을 고정 문화권 ()으로 설정 해야 합니다 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> . 데이터가 문화권에서 공유 되는 경우 기본 로캘을 사용 하면 또는의 내용이 <xref:System.Data.DataTable> <xref:System.Data.DataSet> 잘못 표시 되거나 해석 될 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 또는에 대 한 로캘을 명시적으로 <xref:System.Data.DataTable> 설정 <xref:System.Data.DataSet> 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 라이브러리나 응용 프로그램이 제한 된 로컬 대상에 대 한 것 이거나, 데이터가 공유 되지 않거나, 기본 설정이 지원 되는 모든 시나리오에서 원하는 동작을 생성 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
 다음 예에서는 두 개의 <xref:System.Data.DataTable> 인스턴스를 만듭니다.

 [!code-csharp[FxCop.Globalization.DataTable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DataTable/cs/FxCop.Globalization.DataTable.cs#1)]

## <a name="see-also"></a>참고 항목
 <xref:System.Data.DataTable?displayProperty=fullName> <xref:System.Data.DataSet?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
