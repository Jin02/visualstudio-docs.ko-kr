---
title: C-C++ 어설션 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [MFC], assertions
- results, checking
- result checking
- Call Stack window, assertion failures
- debugging [C++], assertions
- VERIFY macro
- assertions, side effects
- assertions
- ASSERT macro
- errors [C++], catching with assertions
- testing, error conditions with assertion statements
- _DEBUG macro
- Assertion Failed dialog box
- failures, finding locations
ms.assetid: 2d7b0121-71aa-414b-bbb6-ede1093d0bfc
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 759376a6682287cbe41d4d1dc13666c5a540f8e9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050559"
---
# <a name="cc-assertions"></a>C/C++ 어설션
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

어설션 문은 프로그램의 지점에서 true가 될 예상 하는 조건을 지정 합니다. 어설션이 실패 하 여 프로그램의 실행이 중단 되며 해당 조건이 true가 아닐 경우와 [어설션 오류 대화 상자](../debugger/assertion-failed-dialog-box.md) 나타납니다.  

 Visual C++ 에서는 다음 구문을 기반으로 하는 어설션 문을 지원 합니다.  

- MFC 프로그램에 대 한 MFC 어설션입니다.  

- [ATLASSERT](http://msdn.microsoft.com/library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) ATL.를 사용 하는 프로그램에 대 한  

- C 런타임 라이브러리를 사용 하는 프로그램에 대 한 CRT 어설션입니다.  

- ANSI [함수를 어설션](http://msdn.microsoft.com/library/a9ca031a-648b-47a6-bdf1-65fc7399dd40) 다른 c /C++ 프로그램입니다.  

  논리 오류를 catch는 작업의 결과 확인 하 고 처리 해야 하는 오류 조건을 테스트에 어설션을 사용할 수 있습니다.  

## <a name="BKMK_In_this_topic"></a> 항목 내용  
 [어설션 작동 방식](#BKMK_How_assertions_work)  

 [디버그 및 릴리스 빌드에 어설션 사용](#BKMK_Assertions_in_Debug_and_Release_builds)  

 [어설션을 사용 하 여의 파생 작업](#BKMK_Side_effects_of_using_assertions)  

 [CRT 어설션](#BKMK_CRT_assertions)  

 [MFC 어설션](#BKMK_MFC_assertions)  

- [MFC ASSERT_VALID 및 CObject::AssertValid](#BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid)  

- [AssertValid의 제한 사항](#BKMK_Limitations_of_AssertValid)  

  [어설션을 사용 하 여](#BKMK_Using_assertions)  

- [논리 오류 검색](#BKMK_Catching_logic_errors)  

- [결과 확인](#BKMK_Checking_results_)  

- [처리 되지 않은 찾기 오류](#BKMK_Testing_error_conditions_)  

## <a name="BKMK_How_assertions_work"></a> 어설션 작동 방식  
 디버거에서 중지 되 MFC 나 C 런타임 라이브러리 어설션으로 인해, 다음 원본이 사용 가능한 경우 디버거 탐색 어설션이 발생 한 원본 파일에서 합니다. 어설션 메시지 둘 다에 표시 됩니다는 [출력 창](../ide/reference/output-window.md) 하며 **어설션이 실패 한** 대화 상자. 어설션 메시지를 복사할 수 있습니다 합니다 **출력** 나중에 참조할 수 있도록 저장 하려는 경우 텍스트 창에는 창입니다. 합니다 **출력** 창에는 다른 오류 메시지가 포함 될 수 있습니다. 어설션 실패의 원인에 단서를 제공 하기 때문에 이러한 메시지를 주의 깊게 검토 합니다.  

 어설션을 사용 하 여 개발 하는 동안 오류를 검색 합니다. 일반적으로 각 가정에 대 한 하나의 어설션을 사용 하 여 합니다. 예를 들어, 인수로 NULL 인지를 가정 하는 경우 어설션을 가정을 테스트 하려면 사용 합니다.  

 [항목 내용](#BKMK_In_this_topic)  

## <a name="BKMK_Assertions_in_Debug_and_Release_builds"></a> 디버그 및 릴리스 빌드에 어설션 사용  
 어설션 문을 컴파일할 경우에 `_DEBUG` 정의 됩니다. 그렇지 않으면 컴파일러는 어설션을 null 문으로 처리 합니다. 따라서 어설션 문이 적용 오버 헤드 없이 또는 성능 최종 릴리스 프로그램에서 비용 및 사용 하 여 방지할 수 있도록 `#ifdef` 지시문입니다.  

## <a name="BKMK_Side_effects_of_using_assertions"></a> 어설션을 사용 하 여의 파생 작업  
 코드에 어설션을 추가할 경우 어설션이 파생 작업이 없는 있는지 확인 합니다. 예를 들어, 다음 어설션을 수정 하 여 `nM` 값:  

```  
ASSERT(nM++ > 0); // Don't do this!  

```  

 때문에 합니다 `ASSERT` 프로그램의 릴리스 버전에서 식은 계산 되지 않습니다 `nM` 디버그 및 릴리스 버전에서 다른 값이 적용 됩니다. MFC에서이 문제를 방지 하려면 사용 합니다 [확인](http://msdn.microsoft.com/library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) 매크로 대신 `ASSERT`합니다.  `VERIFY` 모든 버전 에서도 식을 계산 하 하지만 릴리스 버전의 결과 검사 하지 않습니다.  

 특히 주의 어설션이 문에서 함수 호출을 사용 하는 방법에 대 한 함수를 가질 수 있으므로 예기치 않은 파생 작업이 있습니다.  

```  
ASSERT ( myFnctn(0)==1 ) // unsafe if myFnctn has side effects  
VERIFY ( myFnctn(0)==1 ) // safe  
```  

 `VERIFY` 호출 `myFnctn` 디버그 및 릴리스 버전에서는 따라서 것이를 사용할 수 있습니다. 그러나 사용 하 여 `VERIFY` 릴리스 버전에서 불필요 한 함수 호출의 오버 헤드를 적용 합니다.  

 [항목 내용](#BKMK_In_this_topic)  

## <a name="BKMK_CRT_assertions"></a> CRT 어설션  
 CRTDBG 합니다. H 헤더 파일에 정의 된 [_ASSERT 및 _ASSERTE 매크로](http://msdn.microsoft.com/library/e98fd2a6-7f5e-4aa8-8fe8-e93490deba36) 어설션 검사에 대 한 합니다.  

|   매크로    |                                             결과                                              |
|------------|-------------------------------------------------------------------------------------------------|
| `_ASSERT`  | 지정 된 식이 FALSE로 평가 되는 경우의 파일 이름과 줄 번호는 `_ASSERT`합니다. |
| `_ASSERTE` |      동일 `_ASSERT`, plus 어설션된 식의 문자열 표현입니다.       |

 `_ASSERTE` FALSE를 판명 하는 어설션된 식을 보고 하기 때문에 더 강력 합니다. 소스 코드를 참조 하지 않고 문제를 식별할 수 있습니다. 그러나 응용 프로그램의 디버그 버전 문자열 상수를 사용 하 여 어설션 각 식에 대 한 사용 될 `_ASSERTE`합니다. 많이 사용 하면 `_ASSERTE` 매크로 상당한 양의 메모리를 차지 이러한 문자열 식입니다. 문제를 입증 하는 경우 사용 하 여 `_ASSERT` 메모리에 저장 합니다.  

 때 `_DEBUG` 정의 `_ASSERTE` 매크로 다음과 같이 정의 됩니다.  

```  
#define _ASSERTE(expr) \  
   do { \  
      if (!(expr) && (1 == _CrtDbgReport( \  
         _CRT_ASSERT, __FILE__, __LINE__, #expr))) \  
         _CrtDbgBreak(); \  
   } while (0)  
```  

 어설션된 식이 FALSE로 [_CrtDbgReport](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc) (기본적으로 메시지 대화 상자를 사용) 어설션 실패를 보고 하기 위해 호출 됩니다. 선택 하면 **다시 시도** 메시지 대화 상자에서 `_CrtDbgReport` 1을 반환 하 고 `_CrtDbgBreak` 디버거에서 호출 `DebugBreak`.  

### <a name="checking-for-heap-corruption"></a>힙 손상 확인  
 다음 예제에서는 [_CrtCheckMemory](http://msdn.microsoft.com/library/457cc72e-60fd-4177-ab5c-6ae26a420765) 힙 손상 되었는지 확인 하려면:  

```  
_ASSERTE(_CrtCheckMemory());  
```  

### <a name="checking-pointer-validity"></a>포인터 유효성 확인  
 다음 예제에서는 [_CrtIsValidPointer](http://msdn.microsoft.com/library/91c35590-ea5e-450f-a15d-ad8d62ade1fa) 된 지정 된 메모리 범위가 읽기 또는 쓰기에 대해 올바른지 확인 합니다.  

```  
_ASSERTE(_CrtIsValidPointer( address, size, TRUE );  
```  

 다음 예제에서는 [_CrtIsValidHeapPointer](http://msdn.microsoft.com/library/caf597ce-1b05-4764-9f37-0197a982bec5) 포인터가 가리키는 로컬 힙에서 메모리를 확인 하려면 (힙을 만들고 C 런타임 라이브러리의이 인스턴스에서 관리-DLL 라이브러리의 자체 인스턴스를 사용할 수 및 따라서 자체 힙의 경우 응용 프로그램 힙 외부)입니다. 이 어설션이 null 이나 아니라 정적 변수와 스택 변수를 다른 로컬이 아닌 메모리에 대 한 포인터도 범위를 벗어나는 주소입니다.  

```  
_ASSERTE(_CrtIsValidPointer( myData );  
```  

### <a name="checking-a-memory-block"></a>메모리 블록을 확인합니다.  
 다음 예제에서는 [_CrtIsMemoryBlock](http://msdn.microsoft.com/library/f7cbbc60-3690-4da0-a07b-68fd7f250273) 로컬 힙에서 메모리 블록을 들어 이며 유효한 블록 형식이 확인 합니다.  

```  
_ASSERTE(_CrtIsMemoryBlock (myData, size, &requestNumber, &filename, &linenumber));  
```  

 [항목 내용](#BKMK_In_this_topic)  

## <a name="BKMK_MFC_assertions"></a> MFC 어설션  
 MFC를 정의 합니다 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 어설션 검사에 대 한 매크로입니다. 또한 정의 `MFC ASSERT_VALID` 및 `CObject::AssertValid` 의 내부 상태를 확인 하기 위한 메서드를 `CObject`-파생 개체입니다.  

 경우 MFC의 인수 `ASSERT` 매크로 계산 결과가 0 또는 false 이면 매크로 프로그램 실행을 중지 하 고 사용자에 게 알립니다; 실행이 계속이 고, 그렇지 합니다.  

 어설션이 실패할 경우 메시지 대화 상자에서 어설션의 줄 번호를 소스 파일의 이름을 표시 합니다. 대화 상자에서 다시 시도 선택 하면 상자에 대 한 호출 [AfxDebugBreak](http://msdn.microsoft.com/library/c4cd79b9-9327-4db5-a9d6-c4004a92aa30) 중단 하 고 디버거 실행이 넘어갑니다. 이 시점에서 호출 스택을 검사 하 고 어설션이 실패 원인을 확인 하려면 다른 디버거 기능을 사용할 수 있습니다. 설정한 경우 [Just in time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md), 디버거가 이미 실행, 대화 상자에서 디버거를 시작할 수 있습니다.  

 다음 예제에서는 사용 하는 방법을 보여 줍니다 `ASSERT` 함수의 반환 값을 확인 하려면:  

```  
int x = SomeFunc(y);  
ASSERT(x >= 0);   //  Assertion fails if x is negative  
```  

 사용 하 여 assert 합니다 [IsKindOf](http://msdn.microsoft.com/library/7c87c748-b7e0-4c6d-9694-6035e62fdfd6) 형식 검사 함수 인수를 제공 하는 함수:  

```  
ASSERT( pObject1->IsKindOf( RUNTIME_CLASS( CPerson ) ) );  
```  

 `ASSERT` 매크로 릴리스 버전에 없는 코드를 생성 합니다. 릴리스 버전에서 식을 계산 하는 경우 사용 합니다 [확인](http://msdn.microsoft.com/library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) 매크로 ASSERT 대신 합니다.  

### <a name="BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid"></a> MFC ASSERT_VALID 및 CObject::AssertValid  
 합니다 [CObject::AssertValid](http://msdn.microsoft.com/library/534a0744-4ab6-423d-b492-b4058b3d5157) 메서드는 개체의 내부 상태에 대 한 런타임 검사를 제공 합니다. 재정의 필요 하지 않지만 `AssertValid` 에서 클래스를 파생 시키는 경우 `CObject`, 할 수 있습니다 클래스 보다 안정적이 수행 하 여 합니다. `AssertValid` 모든 유효한 값이 들어 있는지 확인 하는 개체의 멤버 변수에서 어설션을 수행 해야 합니다. 예를 들어 포인터 멤버 변수가 NULL이 아닌지 확인 해야 합니다.  

 다음 예제에서는 선언 하는 방법을 보여 줍니다는 `AssertValid` 함수:  

```  
class CPerson : public CObject  
{  
protected:  
    CString m_strName;  
    float   m_salary;  
public:  
#ifdef _DEBUG  
    // Override  
    virtual void AssertValid() const;  
#endif  
    // ...  
};  

```  

 재정의 하는 경우 `AssertValid`, 호출의 기본 클래스 버전 `AssertValid` 고유한 검사를 수행 하기 전에 합니다. 그런 다음 다음과 같이 파생 클래스에 고유한 멤버를 확인 하려면 ASSERT 매크로 사용 합니다.  

```  
#ifdef _DEBUG  
void CPerson::AssertValid() const  
{  
    // Call inherited AssertValid first.  
    CObject::AssertValid();  

    // Check CPerson members...  
    // Must have a name.  
    ASSERT( !m_strName.IsEmpty());  
    // Must have an income.  
    ASSERT( m_salary > 0 );  
}  
#endif  

```  

 개체를 저장할 멤버 변수가 있는 경우 사용할 수 있습니다 합니다 `ASSERT_VALID` 의 내부 유효성을 테스트할 매크로 (해당 클래스에서 재정의할 경우 `AssertValid`).  

 예를 들어 클래스 `CMyData`는 저장소를 [CObList](http://msdn.microsoft.com/library/80699c93-33d8-4f8b-b8cf-7b58aeab64ca) 멤버 변수 중 하나입니다. 합니다 `CObList` 변수인 `m_DataList`, 컬렉션을 저장 `CPerson` 개체입니다. 약식된 선언은 `CMyData` 다음과 유사 합니다.  

```  
class CMyData : public CObject  
{  
    // Constructor and other members ...  
    protected:  
        CObList* m_pDataList;  
    // Other declarations ...  
    public:  
#ifdef _DEBUG  
        // Override:  
        virtual void AssertValid( ) const;  
#endif  
    // And so on ...  
};  

```  

 합니다 `AssertValid` 의 재정의 `CMyData` 다음과 유사 합니다.  

```  
#ifdef _DEBUG  
void CMyData::AssertValid( ) const  
{  
    // Call inherited AssertValid.  
    CObject::AssertValid( );  
    // Check validity of CMyData members.  
    ASSERT_VALID( m_pDataList );  
    // ...  
}  
#endif  

```  

 `CMyData` 사용 된 `AssertValid` 해당 데이터 멤버에 저장 된 개체의 유효성을 테스트 하는 메커니즘입니다. 재정의할 `AssertValid` 의 `CMyData` 호출을 `ASSERT_VALID` 자체 m_pDataList 멤버 변수에 대 한 매크로입니다.  

 유효성 테스트 해도이 수준 때문에 클래스 `CObList` 재정의 `AssertValid`합니다. 이 재정의 목록의 내부 상태에 대 한 테스트 추가 유효성 검사를 수행 합니다. 에 유효성을 테스트 하는 따라서를 `CMyData` 개체의 저장 된 내부 상태에 대 한 추가 유효성 테스트를 통과 시키는 `CObList` 목록 개체.  

 몇 가지 더 많은 작업을 사용 하 여에 대 한 유효성 검사 테스트를 추가할 수 있습니다는 `CPerson` 개체 목록에도 저장 합니다. 클래스를 파생 시킬 수 있습니다 `CPersonList` 에서 `CObList` 시키고 `AssertValid`합니다. 재정의 호출 `CObject::AssertValid` 다음 목록에서 반복 하 고 호출 `AssertValid` 각 `CPerson` 개체 목록에 저장 합니다. 합니다 `CPerson` 이미이 항목의 시작 부분에 표시 된 클래스 재정의 `AssertValid`합니다.  

 디버깅을 빌드할 때 강력한 메커니즘입니다. 나중에 릴리스 빌드 메커니즘은 자동으로 해제 됩니다.  

### <a name="BKMK_Limitations_of_AssertValid"></a> AssertValid의 제한 사항  
 트리거된 어설션이 나타냅니다 개체가 잘못 된 실행이 중지 됩니다. 그러나 어설션의 부족 나타내지만 발견 된 문제가 개체 작동이 보장 되지 않습니다.  

 [항목 내용](#BKMK_In_this_topic)  

## <a name="BKMK_Using_assertions"></a> 어설션을 사용 하 여  

### <a name="BKMK_Catching_logic_errors"></a> 논리 오류 검색  
 프로그램의 논리에 따라 true 여야 하는 조건에서 어설션을 설정할 수 있습니다. 어설션이 논리 오류가 발생 하는 효과가 있습니다.  

 예를 들어, 컨테이너 및 변수에서 가스 분자를 시뮬레이션 하는 경우 `numMols` 분자의 총 수를 나타냅니다. 이 숫자는 0, MFC 어설션 문을 다음과 같이 포함할 수 있으므로 보다 작을 수 없습니다.  

```  
ASSERT(numMols >= 0);  

```  

 또는 다음과 같은 CRT 어설션을 포함할 수 있습니다.  

```  
_ASSERT(numMols >= 0);  
```  

 이러한 문은 프로그램 올바르게 작동 하는 경우 아무 작업도 수행 합니다. 그러나 논리 오류를 발생 하는 경우 `numMols` 0 보다 작을 수, 어설션은 프로그램의 실행을 중단을 표시 합니다 [어설션 실패 대화 상자](../debugger/assertion-failed-dialog-box.md)합니다.  

 [항목 내용](#BKMK_In_this_topic)  

### <a name="BKMK_Checking_results_"></a> 결과 확인  
 어설션은 테스트 결과 빠른 시각적 검사를 알 수 없는 작업에 유용 합니다.  

 예를 들어, 다음 코드에서는 변수를 업데이트 하는 것이 좋습니다 `iMols` 가리키는 연결 된 목록의 내용에 따라 `mols`:  

```  
/* This code assumes that type has overloaded the != operator  
 with const char *   
It also assumes that H2O is somewhere in that linked list.   
Otherwise we'll get an access violation... */  
while (mols->type != "H2O")  
{  
 iMols += mols->num;  
 mols = mols->next;  
}  
ASSERT(iMols<=numMols); // MFC version  
_ASSERT(iMols<=numMols); // CRT version  
```  

 분자의 수에 계산 `iMols` 분자, 총 작거나 여야 `numMols`합니다. 루프의 시각적 검사가 반드시 되도록 경우 있으므로 해당 조건에 대 한 테스트를 루프 후 어설션 문을 사용 하는 것을 표시 하지 않습니다.  

 [항목 내용](#BKMK_In_this_topic)  

### <a name="BKMK_Testing_error_conditions_"></a> 처리 되지 않은 찾기 오류  
 지점에서 오류 조건을 코드에서 테스트할 수 있는 오류 처리 해야 어설션을 사용할 수 있습니다. 다음 예제에서는 그래픽 루틴이 오류 코드 또는 성공에 0을 반환합니다.  

```  
myErr = myGraphRoutine(a, b);  

/* Code to handle errors and  
   reset myErr if successful */  

ASSERT(!myErr); -- MFC version  
_ASSERT(!myErr); -- CRT version  
```  

 오류 처리 코드가 제대로 작동 하는 경우 오류를 처리 해야 하 고 `myErr` 어설션이 도달 하기 전에 0으로 다시 설정 합니다. 하는 경우 `myErr` 에 다른 값을 어설션 실패, 프로그램 중단 하며 [어설션 실패 대화 상자](../debugger/assertion-failed-dialog-box.md) 나타납니다.  

 그러나 어설션 문이 오류 처리 코드에 대 한 대체는 합니다. 다음 예제에서는 최종 릴리스 코드에서 문제가 발생할 수 있는 어설션 문을 보여 줍니다.  

```  
myErr = myGraphRoutine(a, b);  

/* No Code to handle errors */  

ASSERT(!myErr); // Don't do this!  
_ASSERT(!myErr); // Don't do this, either!  
```  

 이 코드는 오류 조건을 처리 하는 어설션 문을 사용 합니다. 모든 오류 코드가 반환 되는 결과적으로, `myGraphRoutine` 최종 릴리스 코드에서 처리 되지 것입니다.  

 [항목 내용](#BKMK_In_this_topic)  

## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [관리 코드에 어설션 사용](../debugger/assertions-in-managed-code.md)
