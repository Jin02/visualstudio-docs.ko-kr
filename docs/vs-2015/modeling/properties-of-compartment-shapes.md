---
title: 구획 모양의 속성 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords:
- Domain-Specific Language, compartment shape
ms.assetid: 9a9e112d-210d-413b-a44f-0e976a4a78bc
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b3caf9828f678c72bf756063183f7d867c5c0e66
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652058"
---
# <a name="properties-of-compartment-shapes"></a>구획 모양의 속성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

구획 도형은 도메인 특정 언어로 도메인 클래스를 표시 하는 데 사용할 수 있는 도형 중 하나입니다. 구획을 확장 하거나 축소할 수 있습니다.

 자세한 내용은 [도메인별 언어를 정의 하는 방법](../modeling/how-to-define-a-domain-specific-language.md)을 참조 하세요. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)을 참조 하세요.

 구획 모양에는 다음 표에 나열 된 속성이 있습니다.

|속성|설명|기본|
|--------------|-----------------|-------------|
|기본 확장 축소 상태|@No__t_0 경우 구획이 생성 시 표시 됩니다. @No__t_0 경우에는 그렇지 않습니다.|넓게|
|채우기 색|이 도형의 채우기 색입니다.|하얀|
|채우기 그라데이션 모드|이 도형의 채우기 그라데이션 모드입니다.|가로|
|기하학|이 도형의 기 하 도형 (사각형 또는 모퉁이가 둥근 사각형)입니다.|사각형|
|기본 연결 지점이 있음|@No__t_0 경우이 셰이프는 생성 된 디자이너에서 위쪽, 아래쪽, 왼쪽 및 오른쪽 연결 위치를 사용 합니다.|False|
|단일 구획 헤더 표시|@No__t_0 하 고 도형에 단일 구획이 있으면 구획의 헤더가 표시 되지 않습니다.|True|
|윤곽선 색|이 도형의 윤곽선 색입니다.|검정|
|윤곽선 파선 스타일|이 도형의 윤곽선 대시 스타일 (단색, 대시, 점, 일점 Dot, DashDotDot, 사용자 지정)입니다.|단색|
|윤곽선 두께|이 도형의 윤곽선 두께입니다.|0.03125|
|텍스트 색|이 모양과 연결 된 텍스트 데코레이터에 사용 되는 색입니다.|검정|
|액세스 한정자|구획 모양 (`public` 또는 `internal`)의 액세스 수준입니다.|Public|
|사용자 지정 특성|이 구획 셰이프에서 생성 된 소스 코드 클래스에 특성을 추가 하는 데 사용 됩니다.|\<none >|
|Double 파생을 생성 합니다.|@No__t_0 경우 재정의를 통한 사용자 지정을 지원 하기 위해 기본 클래스와 partial 클래스가 모두 생성 됩니다. 자세한 내용은 [생성 된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)을 참조 하세요.|False|
|사용자 지정 생성자 있음|@No__t_0 경우 소스 코드에서 사용자 지정 생성자가 제공 됩니다. 자세한 내용은 [생성 된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)을 참조 하세요.|False|
|상속 한정자|구획 모양 (`none`, `abstract` 또는 `sealed`)에서 생성 되는 소스 코드 클래스의 상속 종류에 대해 설명 합니다.|없음|
|기본 구획 도형|이 도형의 기본 클래스입니다.|(없음)|
|name|이 셰이프의 이름입니다.|현재 이름|
|네임스페이스|이 모양과 관련 된 네임 스페이스입니다.|현재 네임 스페이스|
|도구 설명 형식|도구 설명을 정의 하는 방법 (고정, 변수 또는 없음)입니다. 고정 된 경우 `Fixed Tooltip Text` 속성의 값이 도구 설명으로 사용 됩니다. 변수 이면 도구 설명이 사용자 지정 코드에 정의 됩니다.|없음|
|노트|이 셰이프와 연결 된 비공식 메모입니다.|\<none >|
|초기 높이|이 도형의 초기 높이 (인치)입니다. 구획 도형의 경우 헤더 섹션의 높이가 며 크기를 조정할 수 없습니다.|1|
|초기 너비|이 도형의 초기 너비 (인치)입니다.|1.5|
|속성으로 노출 된 채우기 색<br /><br /> 노출 된 채우기 그라데이션 모드<br /><br /> 제공 된 윤곽선 색을 속성으로 표시<br /><br /> 노출 된 윤곽선 대시 스타일을 속성으로<br /><br /> 개요 두께를 속성으로 노출<br /><br /> 텍스트 색을 노출 합니다.|@No__t_0 경우 사용자는 셰이프의 설명 된 속성을 설정할 수 있습니다. 이를 설정 하려면 셰이프 정의를 마우스 오른쪽 단추로 클릭 하 고 **노출 추가**를 클릭 합니다.|False|
|설명|생성 된 디자이너를 문서화 하는 데 사용 됩니다.|\<none >|
|표시 이름|이 셰이프에 대해 생성 된 디자이너에 표시 되는 이름입니다.|\<none >|
|고정 도구 설명 텍스트|고정 도구 설명에 사용 되는 텍스트입니다.|\<none >|
|Help Keyword|이 모양에 대 한 F1 도움말을 인덱싱하는 데 사용 되는 키워드입니다.|\<none >|

## <a name="see-also"></a>관련 항목:
 [도메인 특정 언어 도구 용어집](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
