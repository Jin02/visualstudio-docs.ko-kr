---
title: IDebugPortPicker::DisplayPortPicker | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 00923556927f2fed7e5895df2db391a45463e57e
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212900"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
사용자가 포트를 선택할 수 있도록 지정 된 대화 상자가 표시 됩니다.

## <a name="syntax"></a>구문

```cpp
HRESULT DisplayPortPicker(
   HWND hwndParentDialog,
   BSTR* pbstrPortId
);
```

```csharp
public int DisplayPortPicker(
   int hwndParentDialog,
   out string pbstrPortId
);
```

## <a name="parameters"></a>매개 변수
`hwndParentDialog`\
[in] 부모 대화 상자에 대 한 핸들입니다.

`pbstrPortId`\
[out] 포트 식별자 문자열입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 값 `S_FALSE` (또는 반환 값이 `S_OK` 사용 하 여는 `BSTR` 로 설정 `NULL`) 사용자 클릭 했음을 나타냅니다 **취소**합니다.

## <a name="see-also"></a>참고자료
- [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)