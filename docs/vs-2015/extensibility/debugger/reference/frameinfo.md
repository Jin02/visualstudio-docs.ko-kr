---
title: FRAMEINFO | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 00590f4ce9822eee9253196aba15019eb86de1b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549613"
---
# <a name="frameinfo"></a>FRAMEINFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [FRAMEINFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/frameinfo)합니다.  
  
스택 프레임을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef struct tagFRAMEINFO {   
   FRAMEINFO_FLAGS    m_dwValidFields;  
   BSTR               m_bstrFuncName;  
   BSTR               m_bstrReturnType;  
   BSTR               m_bstrArgs;  
   BSTR               m_bstrLanguage;  
   BSTR               m_bstrModule;  
   UINT64             m_addrMin;  
   UINT64             m_addrMax;  
   IDebugStackFrame2* m_pFrame;  
   IDebugModule2*     m_pModule;  
   BOOL               m_fHasDebugInfo;  
   BOOL               m_fStaleCode;  
   BOOL               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
```csharp  
public struct FRAMEINFO {   
   public uint              m_dwValidFields;  
   public string            m_bstrFuncName;  
   public string            m_bstrReturnType;  
   public string            m_bstrArgs;  
   public string            m_bstrLanguage;  
   public string            m_bstrModule;  
   public ulong             m_addrMin;  
   public ulong             m_addrMax;  
   public IDebugStackFrame2 m_pFrame;  
   public IDebugModule2     m_pModule;  
   public int               m_fHasDebugInfo;  
   public int               m_fStaleCode;  
   public int               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
## <a name="members"></a>멤버  
 m_dwValidFields  
 플래그의 조합을 합니다 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 어떤 필드가 채워지는 지정 하는 열거형입니다.  
  
 m_bstrFuncName  
 스택 프레임과 연결 된 함수 이름입니다.  
  
 m_bstrReturnType  
 스택 프레임을 연관 된 형식을 반환 합니다.  
  
 m_bstrArgs  
 스택 프레임과 연결 된 함수에 인수입니다.  
  
 m_bstrLanguage  
 함수를 구현 하는 언어입니다.  
  
 m_bstrModule  
 스택 프레임과 연결 된 모듈 이름입니다.  
  
 m_addrMin  
 최소 실제 스택 주소입니다.  
  
 m_addrMAX  
 최대 물리적 스택 주소입니다.  
  
 m_pFrame  
 합니다 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 이 스택 프레임을 나타내는 개체입니다.  
  
 m_pFrame  
 합니다 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 이 스택 프레임을 포함 하는 모듈을 나타내는 개체입니다.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 디버그 정보를 지정 된 프레임에 있는 경우.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 스택 프레임은 더 이상 유효 하지는 코드와 연결 하는 경우.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 스택 프레임 (SDM) 세션 디버그 관리자에서 주석을 처리 하는 경우.  
  
## <a name="remarks"></a>설명  
 이 구조에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) 메서드를 채울 수 있습니다. 이 구조에 포함 된 목록에도 포함 되는 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 차례로 호출에서 반환 되는 인터페이스를 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
