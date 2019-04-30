---
title: 템플릿 정책 및 속성 창 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 769a665e98fe2aaa5cb3ad75947caa177182f4cf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62908682"
---
# <a name="template-policy-and-the-properties-window"></a>템플릿 정책 및 속성 창
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

엔터프라이즈 템플릿 프로젝트 내에서 프로젝트를 억제 되 면 해당 엔터프라이즈 템플릿 프로젝트에는 정책을 적용할 수 있습니다. 템플릿 정책 속성에 대 한 기본값을 설정, 속성, 속성을 추가 숨기고 등에 사용할 수 있는 시스템을 제한 됩니다.  
  
 템플릿 정책을 사용 하 여 정보의 표시를 제어 하는 **속성** 기간은 구현에서 다른 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 템플릿 정책 제한 솔루션 또는 프로젝트 수준에서 개체 속성을 사용할 수 있지만 구성 요소 수준에서 개체 속성을 처리 합니다. 즉  
  
- 메서드를 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 에 표시 될 내용을 결정 하는 **속성** 특정 개체에 대 한 창  
  
- 솔루션 및 프로젝트 수준에서 템플릿 정책을 사용 하 여에서 표시 되는 항목을 확인 합니다 **속성** 이전에 지정 된 개체에 대 한 창  
  
  특정 속성을 선택적으로 제한 하도록 템플릿 정책을 사용 하 여 **속성** 했을 때 지정 된 형식의 프로젝트 항목 창에서 선택한 **솔루션 탐색기** 의 모든 구성원에 게 유용할 수 있습니다 개발 팀 프로젝트에서 작업 합니다. 예를 들어, 템플릿 정책을 사용 하 고 있는 모든 연결 문자열 정보를 데이터베이스에서 개발자를 위한 설정를 읽기 전용으로 연결 문자열을 설정 합니다. 이러한 방법으로 데이터 액세스에 대 한 올바른 경로 사용 하는 각 개발자가 하는 간단한 방법을 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [속성 확장](../../extensibility/internals/extending-properties.md)
