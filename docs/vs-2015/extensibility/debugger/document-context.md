---
title: 컨텍스트 문서 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 96d5e3e34a6827e7871b053501c61e9c4c98ae26
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972291"
---
# <a name="document-context"></a>문서 컨텍스트
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 디버깅 하는 **문서 컨텍스트**:  
  
-   소스 파일의 위치를 나타냅니다. 문서 컨텍스트를 사용 하는 원본 파일을 나타날 수 없는 언어에 대 한 런타임 환경에서 일반적으로 생성 된 문서의 위치를 식별 합니다. 예를 들어, 스크립팅 엔진에서 스크립트 문서를 생성할 수 있습니다. 자세한 내용은 [문서 위치](../../extensibility/debugger/document-position.md)합니다.  
  
-   코드 컨텍스트에 해당 하는 소스 문서의 위치를 설명 합니다. 기호 처리기 코드 컨텍스트를 컨텍스트 설명서, 컴파일러 또는 인터프리터에서 생성 되는 정보를 사용 하 여 매핑됩니다.  
  
-   에 의해 구현 되는 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)   
 [기호 공급자 인터페이스](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)
