---
title: BPERESI_FIELDS | 마이크로 소프트 문서
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: af2f20e7d3abd79261dc18753a7eb940666fc186
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737759"
---
# <a name="bperesi_fields"></a>BPERESI_FIELDS
중단점의 실패한 해결에 대해 검색할 정보를 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
typedef DWORD BPERESI_FIELDS;
```

```csharp
public enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
```

## <a name="fields"></a>필드
`PERESI_BPRESLOCATION`\
`bpResLocation` [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조의 (중단점 확인 위치) 필드를 초기화/사용합니다.

`BPERESI_PROGRAM`\
`BP_ERROR_RESOLUTION_INFO` 구조의 `pProgram` 필드를 초기화/사용합니다.

`BPERESI_THREAD`\
`BP_ERROR_RESOLUTION_INFO` 구조의 `pThread` 필드를 초기화/사용합니다.

`BPERESI_MESSAGE`\
`BP_ERROR_RESOLUTION_INFO` 구조의 `bstrMessage` 필드를 초기화/사용합니다.

`BPERESI_TYPE`\
`BP_ERROR_RESOLUTION_INFO` 구조체의 `dwType` (중단점 유형) 필드를 초기화/사용합니다.

`BPERESI_ALLFIELDS`\
`BP_ERROR_RESOLUTION_INFO` 구조체의 모든 필드를 초기화/사용합니다.

## <a name="remarks"></a>설명
[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) 메서드에 매개 변수로 전달되어 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조의 필드를 초기화할 필드를 나타냅니다.

이러한 값은 `BP_ERROR_RESOLUTION_INFO` 구조의 어떤 필드가 사용되고 해당 구조가 반환될 때 유효한지 나타내는 데도 사용됩니다.

이러한 값은 약간 과 `OR`결합될 수 있습니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: 마이크로소프트.비주얼스튜디오.디버거.인터롭

어셈블리: 마이크로소프트.비주얼스튜디오.디버거.인터롭.dll

## <a name="see-also"></a>참조
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)
