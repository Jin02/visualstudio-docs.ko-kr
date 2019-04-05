---
title: 도메인 클래스의 속성 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1a5f2b2fa8c2ff39b0a7ec3e982145567602ab10
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981211"
---
# <a name="properties-of-domain-classes"></a>도메인 클래스의 속성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

도메인 클래스는 다음 표의 속성을 가집니다. 도메인 클래스에 대 한 자세한 내용은 [모델, 클래스 및 관계 이해](../modeling/understanding-models-classes-and-relationships.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|액세스 한정자|도메인 클래스의 액세스 수준입니다(`public` 또는 `internal`).|`public`|  
|사용자 지정 특성|이 도메인 클래스에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|  
|이중 생성 파생|경우 `True`, 기본 클래스와 지원 사용자 지정 재정의 통해) 하는 것 (하는 partial 클래스를 생성 됩니다. 자세한 내용은 [생성 된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|사용자 지정 생성자|경우 `True`, 소스 코드에서 사용자 지정 생성자를 제공 됩니다. 자세한 내용은 [생성 된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|상속 한정자|도메인 클래스에서 생성 되는 소스 코드 클래스의 상속의 종류에 설명 합니다 (`none`하십시오 `abstract` 또는 `sealed`).|`none`|  
|기본 클래스|이 도메인 클래스가 파생 되는 경우 기본 클래스의 이름입니다.|\<없음 >|  
|이름|이 도메인 클래스의 이름입니다.|현재 이름|  
|네임스페이스|이 도메인 클래스의 네임 스페이스입니다.|현재 네임 스페이스|  
|노트|이 도메인 클래스와 연결 된 비공식 메모입니다.|\<없음 >|  
|설명|생성된 된 디자이너의 UI를 문서화 하는 데 사용 되는 설명입니다.|\<없음 >|  
|표시 이름|이 도메인 클래스에 대해 생성된 된 디자이너에서 표시 되는 이름입니다.|\<없음 >|  
|Help Keyword|이 도메인 클래스에 대 한 F1 도움말을 인덱싱하는 데는 선택적 키워드입니다.|\<없음 >|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
