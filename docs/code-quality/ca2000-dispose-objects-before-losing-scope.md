---
title: 'CA2000: 범위를 벗어나기 전에 개체를 삭제하세요.'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7a498a01741b86c16a52f790489dc8ce62aad06c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233235"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: 범위를 벗어나기 전에 개체를 삭제하세요.

|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|범주|Microsoft.Reliability|
|주요 변경 내용|최신이 아님|

## <a name="cause"></a>원인

<xref:System.IDisposable> 형식의 로컬 개체가 만들어지지만 개체에 대 한 모든 참조가 범위를 벗어난 후에는 개체가 삭제 되지 않습니다.

## <a name="rule-description"></a>규칙 설명

개체에 대 한 모든 참조가 범위를 벗어나는 삭제 가능한 개체를 명시적으로 삭제 하지 않으면 가비지 수집기가 개체의 종료자를 실행할 때 개체는 결정 되지 않은 시간에 삭제 됩니다. 개체의 종료 자가 실행 되지 않도록 하는 예외 이벤트가 발생할 수 있으므로 개체를 명시적으로 삭제 해야 합니다.

### <a name="special-cases"></a>특수 한 경우

CA2000 규칙은 개체가 삭제 되지 않은 경우에도 다음 형식의 로컬 개체에 대해 발생 하지 않습니다.

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

이러한 형식 중 하나의 개체를 생성자에 전달 하 고 필드에 할당 하면 새로 생성 된 형식에 대 한 *삭제 소유권 전송이* 표시 됩니다. 즉, 새로 생성 된 형식이 이제 개체의 삭제를 담당 합니다. 코드가 이러한 형식 중 하나의 개체를 생성자에 전달 하는 경우에는 개체에 대 한 모든 참조가 범위를 CA2000 규칙을 위반 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 개체에 <xref:System.IDisposable.Dispose%2A> 대 한 모든 참조가 범위를 벗어나는 개체에 대해를 호출 합니다.

[`Using`](/dotnet/visual-basic/language-reference/statements/using-statement) [ `using` 문을](/dotnet/csharp/language-reference/keywords/using-statement) 사용 하 여 (Visual Basic)를 구현 <xref:System.IDisposable>하는 개체를 래핑할 수 있습니다. 이러한 방식으로 래핑된 개체는 `using` 블록 끝에서 자동으로 삭제 됩니다. 그러나 다음과 같은 경우에는 `using` 문을 사용 하 여 처리 하거나 처리할 수 없습니다.

- 삭제 가능한 개체를 반환 하려면 개체를 `try/finally` `using` 블록 외부의 블록에 생성 해야 합니다.

- `using` 문의 생성자에서 삭제 가능한 개체의 멤버를 초기화 하지 마십시오.

- 한 예외 처리기로 보호 되는 생성자가 [ `using` 문의 획득 부분](/dotnet/csharp/language-reference/language-specification/statements#the-using-statement)에 중첩 된 경우 외부 생성자에서 오류가 발생 하면 중첩 된 생성자에서 만든 개체가 닫히지 않습니다. 다음 예제에서 <xref:System.IO.StreamReader> 생성자 <xref:System.IO.FileStream> 에 오류가 발생 하면 개체가 닫히지 않습니다. CA2000는이 경우 규칙 위반을 플래그 합니다.

   ```csharp
   using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
   { ... }
   ```

- 동적 개체는 그림자 개체를 사용 하 여 개체의 <xref:System.IDisposable> 삭제 패턴을 구현 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

다음 경우를 제외 하 고이 규칙에서 경고를 표시 하지 마십시오.

- 개체에서를 호출 `Dispose`하는 메서드 (예:)를 호출 했습니다.<xref:System.IO.Stream.Close%2A>
- 경고를 발생 시킨 메서드는 개체를 <xref:System.IDisposable> 래핑하는 개체를 반환 합니다.
- 할당 하는 메서드에는 삭제 소유권이 없습니다. 즉, 개체를 삭제 하는 책임이 메서드에서 생성 되 고 호출자에 게 반환 되는 다른 개체나 래퍼에 전송 됩니다.

## <a name="related-rules"></a>관련 규칙

- [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)
- [CA2202: 개체를 여러 번 삭제 하지 마십시오.](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>예제

삭제 가능한 개체를 반환 하는 메서드를 구현 하는 경우 catch 블록 없이 try/finally 블록을 사용 하 여 개체가 삭제 되었는지 확인 합니다. Try/finally 블록을 사용 하 여 오류 지점에서 예외가 발생할 수 있도록 하 고 개체가 삭제 되었는지 확인 합니다.

OpenPort1 메서드에서 ISerializable 개체 SerialPort 또는 SomeMethod에 대 한 호출을 열기 위한 호출이 실패할 수 있습니다. 이 구현에서 CA2000 경고가 발생 합니다.

OpenPort2 메서드에서는 두 개의 SerialPort 개체가 선언 되 고 null로 설정 됩니다.

- `tempPort`-메서드 작업이 성공 했는지 테스트 하는 데 사용 됩니다.

- `port`는 메서드의 반환 값에 사용 됩니다.

는 `tempPort` 블록`try` 에서 생성 되 고 열리며 다른 모든 필수 작업은 동일한 `try` 블록에서 수행 됩니다. `try` 블록의 끝에는 열린 포트가 반환 되 고 `tempPort` 개체가로 `null`설정 된 `port` 개체에 할당 됩니다.

블록 `finally` 은의 `tempPort`값을 확인 합니다. Null이 아닌 경우에는 메서드의 작업이 실패 하 고 `tempPort` 리소스가 해제 되도록 닫혔습니다. 반환 된 포트 개체에는 메서드의 작업이 성공한 경우 열린 SerialPort 개체가 포함 되 고, 작업이 실패 한 경우에는 null이 됩니다.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function

Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If

   End Try

   Return port

End Function
```

## <a name="example"></a>예제

기본적으로 Visual Basic 컴파일러는 오버플로를 확인 하는 모든 산술 연산자를 포함 합니다. 따라서 Visual Basic 산술 연산은을 throw <xref:System.OverflowException>할 수 있습니다. CA2000와 같은 규칙에서 예기치 않은 위반이 발생할 수 있습니다. 예를 들어, 다음 CreateReader1 함수는 Visual Basic 컴파일러가 StreamReader를 삭제 하지 않도록 하는 예외를 throw 할 수 있는 추가에 대 한 오버플로 검사 명령을 내보내기 때문에 CA2000 위반을 발생 시킵니다.

이 문제를 해결 하려면 프로젝트의 Visual Basic 컴파일러에의 한 오버플로 검사 내보내기를 사용 하지 않도록 설정 하거나 다음 CreateReader2 함수와 같이 코드를 수정할 수 있습니다.

오버플로 검사 내보내기를 사용 하지 않도록 설정 하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. **컴파일**을 클릭 하 고 **고급 컴파일 옵션**을 클릭 한 다음 **정수 오버플로 검사 제거**를 선택 합니다.

[!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>참고 항목

- <xref:System.IDisposable>
- [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)