---
title: IDebugProperty3::GetCustomViewerCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::GetCustomViewerCount
helpviewer_keywords:
- IDebugProperty3::GetCustomViewerCount
ms.assetid: dc5bb3e4-dc85-46e4-98fa-c6be8583b985
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4e6d6ddbc87a2219711a93b54a699df3c5511ab2
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200199"
---
# <a name="idebugproperty3getcustomviewercount"></a>IDebugProperty3::GetCustomViewerCount
이 속성에 사용할 수 있는 사용자 지정 뷰어에 수를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCustomViewerCount(
    ULONG* pcelt
);
```

```csharp
int GetCustomViewerCount(
    out uint pcelt
);
```

## <a name="parameters"></a>매개 변수
`pcelt`\
[out] 이 속성에 사용할 수 있는 사용자 지정 뷰어 수입니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
형식 시각화 도우미를 지원 하기 위해이 메서드는 호출을 전달 합니다 [GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) 메서드. 식 계산기는이 속성의이 형식에 대 한 사용자 지정 뷰어도 지원 합니다 하는 경우이 메서드는 사용자 지정 뷰어 수가 반환된 된 값에 추가 합니다.

형식 시각화 도우미 및 사용자 지정 뷰어 간의 차이점에 대 한 자세한 내용은 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)합니다.

## <a name="example"></a>예제
다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **CProperty** 노출 하는 개체를 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 인터페이스입니다.

```cpp
STDMETHODIMP CProperty::GetCustomViewerCount(ULONG* pcelt)
{
    if (pcelt == NULL)
    {
        return E_POINTER;
    }

    if (GetVisualizerService())
    {
        return m_pIEEVisualizerService->GetCustomViewerCount(pcelt);
    }
    else
    {
        return E_NOTIMPL;
    }
}
```

## <a name="see-also"></a>참고자료
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)
- [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
