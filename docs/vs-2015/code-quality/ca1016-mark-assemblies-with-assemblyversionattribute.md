---
title: 'CA1016: System.assemblyversionattribute를 사용 하 여 어셈블리 표시 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f1498624d4f79a60854a624ee5c4053a3343f515
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663163"
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: AssemblyVersionAttribute로 어셈블리 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithAssemblyVersion|
|CheckId|CA1016|
|범주|Microsoft 디자인|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 어셈블리에 버전 번호가 없습니다.

## <a name="rule-description"></a>규칙 설명
 어셈블리의 id는 다음 정보로 구성 됩니다.

- 어셈블리 이름

- 버전 번호

- culture

- 공개 키 (강력한 이름의 어셈블리의 경우)

  [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]에서는 버전 번호를 사용하여 어셈블리를 고유하게 식별하고 강력한 이름이 지정된 어셈블리의 형식에 바인딩합니다. 버전 번호는 버전 및 게시자 정책과 함께 사용됩니다. 기본적으로 응용 프로그램은 해당 응용 프로그램이 빌드될 때 사용된 어셈블리 버전으로만 실행됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> 특성을 사용 하 여 어셈블리에 버전 번호를 추가 합니다. 다음 예제를 참조하세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 타사 또는 프로덕션 환경에서 사용 하는 어셈블리에 대해서는이 규칙의 경고를 표시 하지 마십시오.

## <a name="example"></a>예제
 다음 예제에서는 <xref:System.Reflection.AssemblyVersionAttribute> 특성이 적용 된 어셈블리를 보여 줍니다.

 [!code-cpp[FxCop.Design.AssembliesVersion#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/cpp/FxCop.Design.AssembliesVersion.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesVersion#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/cs/FxCop.Design.AssembliesVersion.cs#1)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/vb/FxCop.Design.AssembliesVersion.vb#1)]

## <a name="see-also"></a>관련 항목:
 [어셈블리 버전 관리](https://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903) [방법: 게시자 정책 만들기](https://msdn.microsoft.com/library/8046bc5d-2fa9-4277-8a5e-6dcc96c281d9)
