---
title: 'CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9377dcf03bcbb8087d152ef98986f31c12c94c45
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841923"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

식별자에는 접미사입니다.

기본적으로이 규칙만 살펴봅니다 식별자 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

규칙에 따라 특정 기본 형식을 확장 하거나 특정 인터페이스 또는 이러한 형식에서 파생 된 형식을 구현 하는 형식의 이름만 예약 된 특정 접미사로 끝나야 합니다. 다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.

다음 표에서 예약 된 접미사 및 기본 형식 및 연결 된 인터페이스를 나열 합니다.

|접미사|기본 형식/인터페이스|
|------------|--------------------------|
|특성|<xref:System.Attribute?displayProperty=fullName>|
|컬렉션|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|사전|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|이벤트 처리기|이벤트 처리기 대리자를|
|예외|<xref:System.Exception?displayProperty=fullName>|
|사용 권한|<xref:System.Security.IPermission?displayProperty=fullName>|
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|
|스택|<xref:System.Collections.Stack?displayProperty=fullName>|
|스트림|<xref:System.IO.Stream?displayProperty=fullName>|

또한 다음 접미사 해야 **되지** 사용:

- `Delegate`

- `Enum`

- `Impl` (사용 하 여 `Core` 대신)

- `Ex` 또는 동일한 유형의 이전 버전을 구분 하기 위해 유사한 접미사

명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

형식 이름에서 접미사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

접미사가 응용 프로그램 도메인에서 명확한 의미를 갖지 않는 한 이 규칙의 경고를 숨기지 마십시오.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1711.api_surface = private, internal
```

이 범주 (이름 지정)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1710: 식별자에는 올바른 접미사를 사용 해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>참고자료

- [특성](/dotnet/standard/design-guidelines/attributes)
- [이벤트 처리 및 발생](/dotnet/standard/events/index)