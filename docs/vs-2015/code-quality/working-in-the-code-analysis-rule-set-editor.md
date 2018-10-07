---
title: 집합 편집기에서 코드 분석 규칙 작업 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 098cf799ad99eb61a8aa53112eb7e44ee200c6c9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551609"
---
# <a name="working-in-the-code-analysis-rule-set-editor"></a>코드 분석 규칙 집합 편집기에서 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [코드 분석 규칙 집합 편집기에서 작업](https://docs.microsoft.com/visualstudio/code-quality/working-in-the-code-analysis-rule-set-editor)합니다.  
  
코드 분석 규칙 집합 편집기를 사용 하면 사용자 지정 규칙 집합에 포함 된 규칙을 지정 하 고 작업을 지정할 수 있습니다. 또한 코드 분석 규칙 위반이 발생할 때 수행할 동작을 지정할 수 있습니다.  
  
|작업|설명|  
|------------|-----------------|  
|**경고**|경고를 생성 합니다 **오류 목록** 창입니다.|  
|**오류**|오류를 생성 합니다 **오류 목록** 창입니다.|  
|**없음**|규칙을 사용 하지 않도록 설정 합니다.|  
  
 편집기는 그룹 규칙에서 규칙을 지정 하는 필드를 설정 하는 트리 구조에서 규칙을 표시 합니다. 를 추가 하거나 규칙 집합에서 규칙을 제거 하려면 다음 단계 중 하나 이상을 수행 합니다.  
  
-   선택 또는 추가 하거나 그룹의 모든 규칙을 제거 하려면 그룹 노드의 확인란의 선택을 취소 합니다. 모든 규칙은로 그룹을 선택 합니다 **경고** 작업 합니다.  
  
-   클릭 합니다 **동작** 그룹의 필드 그룹의 모든 규칙에 적용할 동작을 지정 합니다.  
  
-   선택 하거나 개별 규칙에 대 한 확인란의 선택을 취소 합니다. 규칙에 대 한 확인란을 선택 하면 규칙은 경고 작업으로 설정 됩니다.  
  
## <a name="rule-set-editor-toolbar"></a>규칙 집합 편집기 도구 모음  
 그룹화, 필터링 하 고 규칙 집합 표에 표시 되는 데이터를 검색 하 여 규칙 집합 편집기의 도구 모음을 사용할 수 있습니다.  
  
 다음 표에서 규칙 집합 편집기 도구 모음에서 컨트롤을 설명 합니다.  
  
|도구 모음 컨트롤|설명|  
|---------------------|-----------------|  
|**모두 확장**|모든 그룹의 규칙을 보여 줍니다.|  
|**모두 축소**|모든 그룹의 규칙을 숨깁니다.|  
|**Group By**|규칙은 그룹화 필드를 지정 합니다. 클릭  **\<없음 >** 그룹 사용 하지 않고 규칙을 표시 합니다.|  
|**열 옵션**|표시할 규칙 필드를 지정 합니다.|  
|**현재 솔루션에 적용 되지 않는 규칙 숨기기**|표시 하거나 솔루션으로 동일한 대상 형식의 되지 않는 규칙을 숨깁니다.|  
|**코드 분석 오류를 생성할 수 있는 규칙 표시**|표시 하거나 오류 동작을 지정 된 규칙을 숨깁니다.|  
|**코드 분석 경고를 생성할 수 있는 규칙 표시**|표시 하거나 경고 작업이 할당 되는 규칙을 숨깁니다.|  
|**활성화 되지 않은 규칙 표시**|표시 하거나 숨깁니다 없음 할당 된 규칙의 동작입니다.|  
|**자식 규칙 집합 추가 또는 제거**|추가 하거나 선택한 규칙 집합에서 규칙을 제거 합니다.|  
|**검색 규칙**|지정 된 문자열에 대 한 모든 필드 값을 검색 합니다.|  
  
## <a name="rule-set-fields"></a>규칙 집합 필드  
 규칙 집합 필드를 규칙에 대 한 정보 표시 설정 및 정렬 규칙은 그룹을 사용할 수 있습니다. 클릭을 표시 하거나 필드를 숨기려면 **열 옵션** 규칙 집합 편집기 도구 모음 및 확인 또는 필드를 표시 하거나 숨기려면 확인란의 선택을 취소 합니다.  
  
 다음 표에서 규칙 집합의 필드를 설명합니다.  
  
|필드|설명|  
|-----------|-----------------|  
|**ID**|규칙의 식별자입니다.|  
|**범주**|규칙 집합의 멤버 자격은, 외에도 코드 분석 규칙 또한 범주별으로 그룹화 됩니다. 자세한 내용은 [관리 코드 경고에 대 한 코드 분석](../code-quality/code-analysis-for-managed-code-warnings.md)합니다.|  
|**이름**|규칙의 제목입니다.|  
|**네임스페이스**|규칙의 네임 스페이스입니다.|  
|**대상 유형**|규칙의 네이티브, 관리 되는 여부 데이터베이스 코드를 나타냅니다.|  
|**작업**|실행할 코드 분석에서 규칙을 위반 하는 경우 수행할 동작입니다.<br /><br /> **경고** -경고를 생성 합니다.<br /><br /> **오류** -오류를 생성 합니다.<br /><br /> **None** -규칙을 사용 하지 않도록 설정 합니다.<br /><br /> 작업 필드를 편집할 수 있습니다. 값을 None으로 설정 된 규칙에 대 한 확인란의 선택을 취소와 같습니다.|  
|**소스 규칙 집합**|규칙을 포함 하는 규칙 집합입니다.|  
  
## <a name="sorting-and-filtering-rule-sets"></a>정렬 및 필터링 규칙 집합  
 규칙 집합 그리드의 열 머리글에서 정렬할 수 있으며 필드의 값을 기준으로 규칙을 필터링 합니다.  
  
-   규칙 집합 목록을 정렬 하려면 정렬 하려는 필드의 열 머리글을 클릭 합니다. 규칙 집합이 그룹화 되어 각 그룹 개별적으로 정렬 됩니다.  
  
-   규칙 집합을 기준으로 필터링 된 필드의 값을 필터링 할 필드의 열 머리글에서 필터 단추를 클릭 합니다. 를 표시 하려는 값의 확인란을 선택 하 고 숨길 하는 값의 확인란의 선택을 취소 합니다.


