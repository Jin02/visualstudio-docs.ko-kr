---
title: DslTextTransform 명령 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8a565fa6226348a1fe1b6dcfcbb67f704e74abc8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553589"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 명령
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [The DslTextTransform 명령](https://docs.microsoft.com/visualstudio/modeling/the-dsltexttransform-command)입니다.  
  
DslTextTransform.cmd은 TextTransform.exe를 호출 하 고 일반 옵션을 사용 하 여 실행 하는 스크립트. DslTextTransformation.cmd를 사용 하 여의 야간 빌드를 자동화 하 여 [!INCLUDE[dsl](../includes/dsl-md.md)] 프로젝트입니다. 자세한 내용은 [TextTransform 유틸리티를 사용 하 여 파일 생성](../modeling/generating-files-with-the-texttransform-utility.md)합니다.  
  
 DslTextTransform.cmd은 다음 디렉터리에 있습니다.  
  
 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**  
  
 DslTextTransform.cmd 입력으로는 다음 인수를 지정할 수 있습니다.  
  
-   도메인 모델 프로젝트의 출력 디렉터리입니다.  
  
-   디자이너 정의 프로젝트의 출력 디렉터리입니다.  
  
-   텍스트 템플릿 파일의 위치입니다.  
  
 DslTextTransform.cmd 기본 지시문 프로세서 및 어셈블리를 사용 하 여 지정 된 텍스트 템플릿 파일을 처리 합니다. 사용자 지정 지시문 프로세서를 만드는 경우 TextTransform.exe를 호출 하는 일괄 처리 파일을 만들 수 있습니다. 이 배치 파일에서 어셈블리 및 연관 된 사용자 지정 지시문 프로세서를 지정할 수 있습니다.


