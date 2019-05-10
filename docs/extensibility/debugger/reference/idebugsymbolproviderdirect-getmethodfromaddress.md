---
title: IDebugSymbolProviderDirect::GetMethodFromAddress | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetMethodFromAddress
- GetMethodFromAddress
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 76bec7cb621605933f8cc0b15ff6cb6e4dd6d70e
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224002"
---
# <a name="idebugsymbolproviderdirectgetmethodfromaddress"></a>IDebugSymbolProviderDirect::GetMethodFromAddress
지정 된 디버그 주소에서 메서드에 대 한 정보를 검색합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetMethodFromAddress(
   IDebugAddress* pAddress,
   GUID*          pGuid,
   DWORD*         pAppID,
   _mdToken*      pTokenClass,
   _mdToken*      pTokenMethod,
   DWORD*         pdwOffset,
   DWORD*         pdwVersion
);
```

```csharp
int GetMethodFromAddress(
   IDebugAddress pAddress,
   out Guid      pGuid,
   out uint      pAppID,
   out uint      pTokenClass,
   out uint      pTokenMethod,
   out uint      pdwOffset,
   out uint      pdwVersion
);
```

## <a name="parameters"></a>매개 변수
 `pAddress`\

 [in] 디버그 하 여 표시 되는 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.

 `pGuid`\

 [out] 모듈의 고유 식별자입니다.

 `pAppID`\

 [out] 응용 프로그램 도메인의 식별자입니다.

 `pTokenClass`\

 [out] 토큰 나타내는 포함 하는 클래스입니다.

 `pTokenMethod`\

 [out] 모듈을 나타내는 토큰 형식입니다.

 `pdwOffset`\

 [out] 시작 부분에서 바이트 오프셋을 `pAddress` 매개 변수입니다.

 `pdwVersion`\

 [out] 메서드의 버전 번호입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)