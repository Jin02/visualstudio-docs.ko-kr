---
title: 코드 분석 체크 인 정책에 대 한 버전 호환성 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a63ead03baffaa0ce8047220ff1ce8a33c88be8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201191"
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>코드 분석 체크 인 정책에 대한 버전 호환성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

코드 분석 체크 인 정책의 서로 다른 버전을 사용 하 여 작성 하 고 평가 해야 하는 경우 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)], 하는 방법의 차이점을 알아야 [!INCLUDE[vstsTfsOrcasLong](../includes/vststfsorcaslong-md.md)] 및 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 체크 인 정책을 평가 합니다.  
  
## <a name="version-compatibility-for-evaluating-check-in-policies"></a>체크 인 정책을 평가 하는 것에 대 한 버전 호환성  
  
- 코드 분석 체크 인 정책을 평가 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]에 존재 하는 모든 규칙이 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 에 존재 하지 않습니다 하지만 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] 무시 됩니다.  
  
- 코드 분석 체크 인 정책을 평가 하는 경우 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]에 적용 되는 모든 새 규칙 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] 무시 됩니다.  
  
- 코드 분석 체크 인 정책에 따라 규칙 어셈블리를 지정 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] 는 인식할 수 없는 어셈블리에서 지정 된 모든 규칙을 무시 합니다.  
  
- 코드 분석 체크 인 정책에 따라 규칙 어셈블리를 지정 하는 경우는 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 인식할 수 없는 메시지가 표시 됩니다.  
  
## <a name="version-compatibility-for-authoring-check-in-policies"></a>체크 인 정책을 작성 하는 것에 대 한 버전 호환성  
  
- 사용 하 여 코드 분석 체크 인 정책을 만든 경우는 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] 버전의 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)]를 사용할 수 없습니다는 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 버전의 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] 수정 합니다. 또한 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 정책을 평가할 수 없습니다.  
  
- 사용 하 여 코드 분석 체크 인 정책을 만든 경우 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] 에서 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]를 사용할 수 있습니다 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] 에서 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] , 및 정책을 수정 하려면도 평가할 수 있습니다 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]. 정책을 사용 하 여 수정한 후 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] 에 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]를 사용 하 여 더 이상 정책을 편집할 수 없습니다 [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] 에서 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]합니다. [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]은 강력한 이름이 일치하지 않는 문제 없이 정책을 평가할 수 있습니다.  
  
- 둘 다에 적용 되는 규칙 설정을 사용 하 여 코드 분석 체크 인 정책을 만들려면 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 하 고 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]에서 정책을 만들어야 합니다 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]필요한 모든 변경 내용을 확인 하 고 정책을 저장 합니다. 규칙 변경에만 존재 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]를 수정 하 고 정책에 저장 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]합니다.  
  
     정책을 저장 한 후 [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], 더 이상에 존재 하는 규칙에 대 한 설정을 변경할 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 만 합니다.
