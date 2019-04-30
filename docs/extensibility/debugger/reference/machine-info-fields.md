---
title: MACHINE_INFO_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MACHINE_INFO_FIELDS
helpviewer_keywords:
- MACHINE_INFO_FIELDS enumeration
ms.assetid: 2d61d206-7d40-4df1-8c88-1b3c9c78821e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61a22a1868a47fd4b54b19cf224f995897775b4f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865786"
---
# <a name="machineinfofields"></a>MACHINE_INFO_FIELDS
특정 컴퓨터에 대 한 검색할 정보의 종류를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_MACHINE_INFO_FIELDS { 
   MCIF_NAME  = 0x00000001,
   MCIF_FLAGS = 0x00000002,
   MCIF_ALL   = 0x00000003
};
typedef DWORD MACHINE_INFO_FIELDS;
```

```csharp
public enum enum_MACHINE_INFO_FIELDS { 
   MCIF_NAME  = 0x00000001,
   MCIF_FLAGS = 0x00000002,
   MCIF_ALL   = 0x00000003
};
```

## <a name="members"></a>멤버
 MCIF_NAME 초기화/사용 된 `bstrName` 구조의 필드입니다.

 MCIF_FLAGS 초기화/사용 된 `Flags` 구조의 필드입니다.

 MIF_ALL 초기화/사용 하 여 모든 구조의 필드입니다.

## <a name="remarks"></a>설명
 이러한 값에 전달 되는 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md) 멤버를 나타내도록 메서드는 [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) 구조는 초기화할 합니다.

 에서도 사용 합니다 `Fields` 소속을 `MACHINE_INFO` 에 유효 하 고 사용 되는 필드는 구조체.

 이러한 플래그는 비트과 결합 될 수 `OR`입니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)
- [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)