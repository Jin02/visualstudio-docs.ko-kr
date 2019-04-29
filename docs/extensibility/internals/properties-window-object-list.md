---
title: 속성 창 개요 목록 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: eccc7cfc432918a80723251a7b9a87ec4e13450d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909101"
---
# <a name="properties-window-object-list"></a>속성 창 개요 목록
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

개체 목록에는 **속성** 창 하나 이상의 선택한 창 내에서 사용할 수 있는 기타 개체 선택을 변경할 수 있는 드롭다운 목록입니다. 에 대 한 호출 트리거이 목록 내에서 다른 개체를 선택 하면 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> 알리는 환경의 new-object가 선택 되어 있는지를 합니다. 표시 되는 정보는 **속성** 창이 새로 선택한 개체에 연결 된 속성을 표시 하려면 다음 변경 됩니다.  
  
## <a name="the-object-list"></a>개체 목록  
 두 필드의 개체 목록으로 구성 됩니다: 개체 유형과 개체 이름을 (굵게 표시 됨).  
  
 개체 자체에서 굵게 표시 된 개체 형식의 왼쪽에 표시 되는 개체 이름 검색은 사용 하 여는 `Name` 제공한 속성은 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 인터페이스. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>에서 유일한 방법은 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>를 반환 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> 해당 인터페이스의 coclass에 대 한 합니다. 합니다 **속성** 창을 사용 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 드롭다운 목록의 개체 이름으로 표시 되는 coclass의 이름을 가져옵니다.  
  
 개체에 없는 경우는 `Name` 속성 이름을 개체 목록의 이름 영역에 표시 되지 않습니다. 개체 목록에 표시 이름을 지정 하려는 경우 개체에는 Name 속성을 추가할 수 있습니다.  
  
 COM 개체를 구현 하지 않는 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>서 **속성** 창 왼쪽 목록의 개체 이름 대신 인터페이스 이름을 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)
