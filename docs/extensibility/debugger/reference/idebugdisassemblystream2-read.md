---
title: IDebugDisassemblyStream2::Read | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::Read
helpviewer_keywords:
- IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb204ccb98d0c7f5a6f5eeac9ccbc5ea07dfae16
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875813"
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
디스어셈블리 스트림 내의 현재 위치에서 시작 하는 지침을 읽습니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Read( 
   DWORD                     dwInstructions,
   DISASSEMBLY_STREAM_FIELDS dwFields,
   DWORD*                    pdwInstructionsRead,
   DisassemblyData*          prgDisassembly
);
```

```csharp
int Read( 
   uint                           dwInstructions,
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,
   out uint                       pdwInstructionsRead,
   DisassemblyData[]              prgDisassembly
);
```

#### <a name="parameters"></a>매개 변수
 `dwInstructions`

 [in] 디스어셈블 하기 위한 지침의 수입니다. 이 값은 또한의 최대 길이 `prgDisassembly` 배열입니다.

 `dwFields`

 [in] 플래그의 조합을 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) 의 필드를 나타내는 열거형 `prgDisassembly` 작성 됩니다.

 `pdwInstructionsRead`

 [out] 실제로 디스어셈블된 명령의 수를 반환 합니다.

 `prgDisassembly`

 [out] 배열을 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조 디스어셈블된 명령 당 하나의 구조 디스어셈블된 코드를 사용 하 여 입력 됩니다. 이 배열의 길이 따라 결정 됩니다는 `dwInstructions` 매개 변수입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 호출 하 여 현재 범위에서 사용할 수 있는 지침의 최대 수를 가져올 수 있습니다 합니다 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) 메서드.

 호출 하 여 현재 위치에서 다음 명령을 읽기 위치를 변경할 수 있습니다 합니다 [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) 메서드.

 `DSF_OPERANDS_SYMBOLS` 플래그를 추가할 수는 `DSF_OPERANDS` 플래그는 `dwFields` 지침 디스어셈블할 때는 기호 이름을 사용 해야 함을 나타내는 매개 변수를 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
- [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)
- [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)