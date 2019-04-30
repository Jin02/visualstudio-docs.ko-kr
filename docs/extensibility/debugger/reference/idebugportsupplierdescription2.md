---
title: IDebugPortSupplierDescription2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d5f210d3f0f8f2a9d28abee3d1956a3b4d09038a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62918124"
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
사용 하도록 설정 합니다 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI 내에서 텍스트를 표시 하는 **전송 정보** 의 섹션을 **프로세스에 연결** 대화 상자.

## <a name="syntax"></a>구문

```
IDebugPortSupplierDescription2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 이 인터페이스는 포트 공급자가 구현 됩니다.

## <a name="methods"></a>메서드
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortSupplierDescription2`합니다.

|메서드|설명|
|------------|-----------------|
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|포트 공급자에 대 한 설명 및 설명 메타 데이터를 검색합니다.|

## <a name="requirements"></a>요구 사항
 헤더: Msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll