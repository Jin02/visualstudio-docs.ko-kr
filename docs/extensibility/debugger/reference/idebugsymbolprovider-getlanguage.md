---
title: IDebugSymbolProvider::GetLanguage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetLanguage
helpviewer_keywords:
- IDebugSymbolProvider::GetLanguage method
ms.assetid: e4142183-3d8b-418f-907f-4ee4c753d8ce
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 071dac72e39a3cce5b0b17dc9e401b9072efda6a
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224062"
---
# <a name="idebugsymbolprovidergetlanguage"></a>IDebugSymbolProvider::GetLanguage
이 메서드는 디버그 주소에서 코드를 컴파일하는 데 사용 된 언어를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetLanguage( 
   IDebugAddress* pAddress,
   GUID*          pguidLanguage,
   GUID*          pguidLanguageVendor
);
```

```csharp
int GetLanguage(
   IDebugAddress pAddress,
   out Guid      pguidLanguage,
   out Guid      pguidLanguageVendor
);
```

## <a name="parameters"></a>매개 변수
 `pAddress`\

 [in] Address 개체 표시는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.

 `pguidLanguage`\

 [out] 반환 된 `GUID` 언어를 지정 하는 합니다.

 `pguidLanguageVendor`\

 [out] 반환 된 `GUID` 언어 공급 업체를 지정 하는 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 디버그 엔진 올바른 식 계산기를 선택 하는 데 필요한 정보를 가져오려면이 메서드를 호출 합니다.

## <a name="see-also"></a>참고자료
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)