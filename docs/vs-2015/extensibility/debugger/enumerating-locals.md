---
title: 로컬 항목 열거 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enumerating locals
- expression evaluation, enumerating locals
ms.assetid: 254a88e7-d3a7-447a-bd0c-8985e73d85cf
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4da225417724f1de39f25a1527bdf980f3d369cd
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60039201"
---
# <a name="enumerating-locals"></a>로컬 항목 열거
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 Visual Studio가 채울 준비가 합니다 **지역** 호출한 창 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 에 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 에서 반환 된 개체 [ GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) (참조 [GetMethodProperty 구현](../../extensibility/debugger/implementing-getmethodproperty.md)). `IDebugProperty2::EnumChildren` 반환 된 [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 개체입니다.  
  
 이 구현의 `IDebugProperty2::EnumChildren` 다음 작업을 수행 합니다.  
  
1. 메서드를 나타내는이 확인 합니다.  
  
2. 사용 하는 `guidFilter` 인수에 대해 호출할 메서드를 결정 합니다 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 개체. 경우 `guidFilter` 같음:  
  
    1. `guidFilterLocals`를 호출 [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 가져오려고는 [IEnumDebugFields](../../extensibility/debugger/reference/ienumdebugfields.md) 개체입니다.  
  
    2. `guidFilterArgs`를 호출 [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 가져오려고는 `IEnumDebugFields` 개체입니다.  
  
    3. `guidFilterLocalsPlusArgs`에서 결과를 결합 하는 열거형을 합성 `IDebugMethodField::EnumLocals` 및 `IDebugMethodField::EnumArguments`합니다. 이 합성 클래스로 표현 됩니다 `CEnumMethodField`합니다.  
  
3. 클래스를 인스턴스화합니다 (호출 `CEnumPropertyInfo` 이 예제의) 구현 하는 `IEnumDebugPropertyInfo2` 인터페이스를 포함 합니다 `IEnumDebugFields` 개체입니다.  
  
4. 반환 된 `IEnumDebugProperty2Info2` 에서 인터페이스를 `CEnumPropertyInfo` 개체입니다.  
  
## <a name="managed-code"></a>관리 코드  
 이 예제에서는 구현을 보여 줍니다. `IDebugProperty2::EnumChildren` 관리 코드에서.  
  
```csharp  
namespace EEMC  
{  
    public class CFieldProperty : IDebugProperty2  
    {  
        public HRESULT EnumChildren (  
                uint                    dwFields,  
                uint                    radix,  
            ref Guid                    guidFilter,   
                ulong                   attribFilter,   
                string                  nameFilter,   
                uint                    timeout,  
            out IEnumDebugPropertyInfo2 properties)   
        {  
            properties = null;  
            IEnumDebugFields fields = null;  
  
            // If this field is a method...  
            if (0 != ((uint) fieldKind & (uint) FIELD_KIND.FIELD_TYPE_METHOD))  
            {  
                IDebugMethodField methodField = (IDebugMethodField) field;  
  
                // Enumerate parameters.  
                if (guidFilter == FilterGuids.guidFilterArgs)  
                {  
                    methodField.EnumParameters(out fields);    
                }  
                // Enumerate local variables.  
                else if (guidFilter == FilterGuids.guidFilterLocals)  
                {  
                    methodField.EnumLocals(address, out fields);    
                }  
                // Enumerate all local variables, including invisible compiler temps.  
                else if (guidFilter == FilterGuids.guidFilterAllLocals)  
                {  
                    methodField.EnumAllLocals(address, out fields);    
                }  
                // Enumerate "this", if any, and all parameters and local variables.  
                else if (guidFilter == FilterGuids.guidFilterLocalsPlusArgs)  
                {  
                    IDebugClassField fieldThis   = null;  
                    IEnumDebugFields parameters = null;  
                    IEnumDebugFields locals     = null;  
  
                    methodField.GetThis(out fieldThis);  
                    methodField.EnumParameters(out parameters);  
                    methodField.EnumLocals(address, out locals);  
  
                    CEnumMethodField enumMethodField =   
                        new CEnumMethodField(fieldThis, parameters, locals);  
                    fields = (IEnumDebugFields) enumMethodField;  
                }  
                // Enumerate only "this".  
                else if (guidFilter == FilterGuids.guidFilterThis)  
                {  
                    IDebugClassField fieldThis   = null;  
                    methodField.GetThis(out fieldThis);  
  
                    CEnumMethodField enumMethodField =   
                        new CEnumMethodField(fieldThis, null, null);  
                    fields = (IEnumDebugFields) enumMethodField;  
                }  
                else throw new COMException();// E_FAIL  
            }  
            // Wrap a property enumerator around the field enumerator.  
            CEnumPropertyInfo propertiesInfo =   
                new CEnumPropertyInfo(provider, address, binder, radix, fields,   
                 (DEBUGPROP_INFO_FLAGS) dwFields);  
  
            properties = (IEnumDebugPropertyInfo2) propertiesInfo;  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>비관리 코드  
 이 예제에서는 구현을 보여 줍니다. `IDebugProperty2::EnumChildren` 비관리 코드에서.  
  
```cpp#  
STDMETHODIMP CFieldProperty::EnumChildren(   
        in DEBUGPROP_INFO_FLAGS        infoFlags,  
        in DWORD                       radix,  
        in REFGUID                     guidFilter,  
        in DBG_ATTRIB_FLAGS            attribFilter,  
        in LPCOLESTR                   pszNameFilter,  
        in DWORD                       timeout,  
        out IEnumDebugPropertyInfo2 ** ppchildren )  
{  
    if (ppchildren == NULL)  
        return E_INVALIDARG;  
    else  
        *ppchildren = 0;  
  
    //get enumeration  
    HRESULT hr;  
    IEnumDebugFields*     pfields    = NULL;  
  
    if (m_fieldKind & FIELD_TYPE_METHOD)  
    {  
        //-----------------------------------------------------  
        // A Method  
  
        IDebugMethodField*  pmethod    = NULL;  
  
        //enumerate the requested properties  
        hr = m_field->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod) );  
        if (FAILED(hr))  
            return hr;  
  
        if (guidFilter == guidFilterArgs)  
        {  
            hr = pmethod->EnumParameters( &pfields );    
        }  
        else if (guidFilter == guidFilterLocals)  
        {  
            hr = pmethod->EnumLocals( m_address, &pfields );  
        }  
        else if (guidFilter == guidFilterAllLocals)  
        {  
            hr = pmethod->EnumAllLocals( m_address, &pfields );  
        }  
        else if (guidFilter == guidFilterLocalsPlusArgs)  
        {  
            //we create a special enumerator for this  
            IDebugClassField* pfieldThis  = NULL;  
            IEnumDebugFields* pparameters = NULL;  
            IEnumDebugFields* plocals     = NULL;  
  
            pmethod->GetThis( &pfieldThis );  
            pmethod->EnumParameters( &pparameters );  
            pmethod->EnumLocals( m_address, &plocals );  
  
            CEnumMethodField* penumMethodField =  
                new CEnumMethodField( pfieldThis, pparameters, plocals );  
            if (pfieldThis != NULL)  
                pfieldThis->Release();  
            if (pparameters != NULL)  
                pparameters->Release();  
            if (plocals != NULL)  
                plocals->Release();  
            if (!penumMethodField)   
            {   
                hr = E_OUTOFMEMORY;  
            }  
            else  
            {  
                hr = penumMethodField->QueryInterface( IID_IEnumDebugFields,  
                        reinterpret_cast<void**>(&pfields) );  
                penumMethodField->Release();  
            }  
        }  
        else if (guidFilter == guidFilterThis )  
        {  
            IDebugClassField* pfieldThis  = NULL;  
  
            hr = pmethod->GetThis( &pfieldThis );  
            if (SUCCEEDED(hr))  
            {  
                CEnumMethodField* penumMethodField =  
                    new CEnumMethodField( pfieldThis, NULL, NULL );  
                pfieldThis->Release();  
                if (!penumMethodField)   
                {  
                    hr = E_OUTOFMEMORY;  
                }  
                else  
                {  
                    hr = penumMethodField->QueryInterface( IID_IEnumDebugFields,  
                        reinterpret_cast<void**>(&pfields) );  
                    penumMethodField->Release();  
                }  
            }  
        }  
        else  
        {  
            hr = E_FAIL;  
        }  
  
        pmethod->Release();  
        if (hr != S_OK)  
            return hr;  
    }  
  
    //create a property info enumeration around the field enumerator  
    CEnumPropertyInfo* pproperties =  
        new CEnumPropertyInfo( m_provider, m_address, m_binder,   
                               radix, pfields, infoFlags );  
    if (pfields != NULL)  
        pfields->Release();  
    if (pproperties == NULL)  
        return E_OUTOFMEMORY;  
  
    hr = pproperties->QueryInterface( IID_IEnumDebugPropertyInfo2,  
        reinterpret_cast<void**>(ppchildren) );  
    pproperties->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [지역 변수의 샘플 구현](../../extensibility/debugger/sample-implementation-of-locals.md)   
 [Getmethodproperty 구현](../../extensibility/debugger/implementing-getmethodproperty.md)   
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)
