---
title: DA0012 - 많은 양의 리플렉션 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: df8b9c80b3d3b12cb556947a7ca77b3141fb853d
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85520643"
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: 리플렉션 양이 많습니다.

|항목|값|
|-|-|
|규칙 ID|DA0012|
|범주|.NET Framework 사용|
|프로파일링 방법|샘플링|
|메시지|리플렉션을 과도하게 사용하는 것 같습니다. 이 작업은 부담이 큰 작업입니다.|
|규칙 유형|경고|

## <a name="cause"></a>원인
 InvokeMember, GetMember 등의 System.Reflection 메서드 호출이나 MemberInvoke 등의 Type 메서드 호출이 프로파일링 데이터의 상당한 부분을 차지합니다. 가능할 경우 이러한 메서드를 종속 어셈블리의 메서드에 대한 초기 바인딩으로 바꿔 보세요.

## <a name="rule-description"></a>규칙 설명
 리플렉션은 종속 런타임 어셈블리에 대한 애플리케이션의 런타임 바인딩을 수행하거나 런타임에 새 형식을 만들고 동적으로 실행하는 데 사용될 수 있는 .NET Framework의 유연한 기능입니다. 그러나 이러한 기술이 빈번히 사용되거나 타이트 루프에서 호출될 경우 성능이 저하될 수 있습니다.

 자세한 내용은 MSDN의 Microsoft Patterns and Practices 라이브러리에 있는 .NET 애플리케이션 성능 및 확장성 볼륨에서 5장 - 관리되는 코드 성능 향상의 [리플렉션 및 런타임 바인딩](/previous-versions/msp-n-p/ff647790(v=pandp.10)#reflection-and-late-binding) 섹션을 참조하세요.

## <a name="how-to-investigate-a-warning"></a>경고를 조사하는 방법
 [오류 목록] 창에서 메시지를 두 번 클릭하여 프로파일링 데이터의 [함수 정보 뷰](../profiling/function-details-view.md)로 이동합니다. System.Type 또는 System.Reflection 메서드의 호출 함수를 검사하여 .NET Reflection API를 가장 빈번히 사용하는 프로그램의 섹션을 찾습니다. 메타데이터를 반환하는 메서드를 사용하지 마세요. 애플리케이션 성능이 중요할 경우 런타임 바인딩을 사용하고 런타임에 형식을 동적으로 만드는 방식을 피해야 합니다.
