---
title: 레거시 언어 서비스 개요 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], about language services
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 496dcbd6f30f9b3b29b49cb9954c0434d0996836
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58971728"
---
# <a name="legacy-language-service-overview"></a>레거시 언어 서비스 개요
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

언어 서비스 제공 하는 특정 구현 하면 편집기 지 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 기능입니다. 자주 사용 하는 기능 및 기타 기능에 대 한 부분 지원에 대 한 전체 지원을 제공 하는 관리 패키지 프레임 워크 (MPF) 언어 서비스 클래스.  
  
## <a name="fully-supported-features-in-the-mpf"></a>MPF에서 완전히 지원 되는 기능  
 MPF 언어 서비스 클래스에는 다음 기능을 지원 합니다.  
  
-   구문 강조  
  
-   개요  
  
-   코드 블록을 주석 처리  
  
-   중괄호 일치  
  
-   코드 조각  
  
-   사용자 지정 문서 속성  
  
-   IntelliSense 매개 변수 정보  
  
-   IntelliSense 요약 정보  
  
-   IntelliSense 멤버 완성  
  
-   IntelliSense 단어 완성  
  
## <a name="partially-supported-features-in-the-mpf"></a>MPF에서 부분적으로 지원 되는 기능  
 MPF는 다음 기능에 대 한만 부분 지원 합니다. 이 MPF를 호출한 메서드를 구현 해야 한다는 것을 의미 합니다.  
  
-   코드 서식 다시 지정 합니다. 다시 구현 하는 코드를 제공 합니다.  
  
-   유효한 코드 범위를 식별 하 여 중단점 유효성 검사 합니다. 코드 범위를 식별 하는 코드를 제공 합니다.  
  
-   디버거가 지 원하는 **자동** 창 변수를 표시 합니다. 창에 표시를 결정 하는 코드를 제공 합니다.  
  
-   지원 합니다 **탐색 모음** 형식 및 멤버 간의 빠른 탐색에 대 한 합니다. 구현 하 고 목록에서 채우는 도우미 클래스를 반환 합니다 **탐색 모음** 콤보 상자입니다.  
  
## <a name="implementation"></a>구현  
 언어 서비스 자체 및 언어에 대 한 지원 하려는 언어 서비스 기능을 구현 하려면 몇 가지 단계를 완료 해야 합니다. 이러한 단계는 다음 항목에 설명 합니다.  
  
-   [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [레거시 언어 서비스 등록](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 중괄호 일치](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 개요 표시](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 주석 처리](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 서식 다시 지정](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 사용자 지정 문서 속성](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 조각 지원](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 탐색 모음 지원](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 멤버 완성](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [레거시 언어 서비스의 빠른 정보](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 자동 창 지원](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 중단점 유효성 검사](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 확장성](../../extensibility/internals/legacy-language-service-extensibility.md)
