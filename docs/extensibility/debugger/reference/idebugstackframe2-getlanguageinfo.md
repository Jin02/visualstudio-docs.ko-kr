---
title: IDebugStackFrame2::GetLanguageInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d0f5c17fc0dd12cf8ecb184b667880462548877
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60093282"
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
이 스택 프레임과 연결 된 언어를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetLanguageInfo ( 
   BSTR* pbstrLanguage,
   GUID* pguidLanguage
);
```

```csharp
int GetLanguageInfo ( 
   ref string pbstrLanguage,
   ref Guid   pguidLanguage
);
```

#### <a name="parameters"></a>매개 변수
 `pbstrLanguage`

 [out] 이 스택 프레임과 연결 된 메서드를 구현 하는 언어의 이름을 반환 합니다.

 `pguidLanguage`

 [out] 반환 된 `GUID` 언어입니다. 에 대 한는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 언어, 예를 들어, 다음 돌아오게 됩니다.

- `guidVBScriptLang`

- `guidJScriptLang`

- `guidCPPLang`

- `guidVBLang`

- `guidSQLLang`

- `guidScriptLang`

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)