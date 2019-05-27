---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 793a3072160230744ab66a5805cd99c24e20cb7c
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200444"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
포트 공급자에서 사용자 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetUserName(
    BSTR *pbstrUserName
);
```

```csharp
int GetUserName (
    string pbstrUserName
);
```

## <a name="parameters"></a>매개 변수
`pbstrUserName`\
[out] 사용자 이름을 포함 하는 문자열입니다.

## <a name="return-value"></a>반환 값
 메서드가 성공 하는 경우 반환 `S_OK`합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 `GetUserName` 에 표시 되는 사용자 이름을 반환 합니다 **사용자 이름** 열의 합니다 **프로세스에 연결** 대화 상자. 보려는 합니다 **프로세스에 연결** 대화 상자에서 클릭 **프로세스에 연결** 에 **도구** 메뉴에서를 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE).

## <a name="see-also"></a>참고자료
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)