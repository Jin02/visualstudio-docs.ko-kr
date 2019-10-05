---
title: 'CA1824: NeutralResourcesLanguageAttribute로 어셈블리를 표시하세요.'
ms.date: 03/29/2018
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df5c0db4e9e141e5833893bbbb447328eab8851e
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233353"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: NeutralResourcesLanguageAttribute로 어셈블리를 표시하세요.

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|범주|Microsoft.Performance|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

어셈블리가 **ResX**기반 리소스를 포함 하지만이 리소스에는 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명

특성 <xref:System.Resources.NeutralResourcesLanguageAttribute> 은 응용 프로그램의 기본 문화권을 리소스 관리자에 게 알립니다. 기본 문화권의 리소스가 앱의 주 어셈블리에 포함 되어 있고 <xref:System.Resources.ResourceManager> 기본 문화권과 같은 문화권에 속하는 리소스를 검색 해야 하는 경우는 <xref:System.Resources.ResourceManager> 주 어셈블리에 있는 리소스를 자동으로 사용 합니다. 위성 어셈블리를 검색 하는 대신 이 일반적인 어셈블리 프로브 무시, 첫 번째 리소스를 로드 하 고 작업 집합을 줄일 수에 대 한 조회 성능이 향상 됩니다.

> [!TIP]
> 에서 리소스 파일을 검색 하는 데 사용 <xref:System.Resources.ResourceManager> 하는 프로세스에 대 한 [리소스 패키징 및 배포](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) 를 참조 하세요.

## <a name="fix-violations"></a>위반 수정

이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 하 고 중립 문화권의 리소스 언어를 지정 합니다.

### <a name="to-specify-the-neutral-language-for-resources"></a>리소스의 중립 언어를 지정 하려면

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.

2. **응용 프로그램** 탭을 선택 하 고 **어셈블리 정보**를 선택 합니다.

   > [!NOTE]
   > 프로젝트가 .NET Standard 또는 .NET Core 프로젝트인 경우 **패키지** 탭을 선택 합니다.

3. **중립 언어** 또는 **어셈블리 중립 언어** 드롭다운 목록에서 언어를 선택 합니다.

4. **확인**을 선택합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시 하지 않을 수 있습니다. 그러나 시작 성능이 저하 될 수 있습니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [데스크톱 앱의 리소스 (.NET)](/dotnet/framework/resources/)
- [CA1703-리소스 문자열의 철자가 정확한 지 확인 합니다.](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701-리소스 문자열 복합 단어의 대/소문자를 올바르게 지정 해야 합니다.](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)