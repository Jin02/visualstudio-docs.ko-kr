---
title: 'CA1062: public 메서드의 인수에 대한 유효성을 검사하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
- Validate arguments of public methods
helpviewer_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 274b01a67974db08d9ec016a18ec115bcfac2452
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907973"
---
# <a name="ca1062-validate-arguments-of-public-methods"></a>CA1062: public 메서드의 인수에 대한 유효성을 검사하세요.

|||
|-|-|
|TypeName|ValidateArgumentsOfPublicMethods|
|CheckId|CA1062|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

외부에 표시 되는 메서드는 해당 참조 인수 중 하나를 해당 인수 인지 여부를 확인 하지 않고 역참조 `null` (`Nothing` Visual Basic에서).

## <a name="rule-description"></a>규칙 설명

외부에서 볼 수 있는 메서드에 전달 되는 모든 참조 인수를 검사 해야 `null`합니다. 해당 하는 경우 throw 한 <xref:System.ArgumentNullException> 인수의 경우 `null`합니다.

메서드를 호출할 수 알 수 없는 어셈블리에서 public 또는 protected로 선언 된 메서드의 모든 매개 변수 유효성을 검사 해야 합니다. 내부 메서드를 확인 하 고 적용 해야 메서드 알려진된 어셈블리에 의해서만 호출 수를 디자인 된 경우는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 메서드를 포함 하는 어셈블리에 특성입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면에 대 한 각 참조 인수를 유효성을 검사 `null`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

역참조 매개 변수는 함수에서 다른 메서드 호출에서 검증 된 경우이 규칙에서 경고를 무시할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 메서드 및 규칙을 충족 하는 메서드를 보여 줍니다.

 ```csharp
 using System;

namespace DesignLibrary
{
    public class Test
    {
        // This method violates the rule.
        public void DoNotValidate(string input)
        {
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }

        // This method satisfies the rule.
        public void Validate(string input)
        {
            if (input == null)
            {
                throw new ArgumentNullException("input");
            }
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }
    }
}
```

```vb
Imports System

Namespace DesignLibrary

    Public Class Test

        ' This method violates the rule.
        Sub DoNotValidate(ByVal input As String)

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

        ' This method satisfies the rule.
        Sub Validate(ByVal input As String)

            If input Is Nothing Then
                Throw New ArgumentNullException("input")
            End If

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

    End Class

End Namespace
```

## <a name="example"></a>예제

개체를 참조 하는 필드 또는 속성을 채우는 복사 생성자는 CA1062 규칙을 위반할 수 있습니다. 복사 생성자에 전달 되는 복사 된 개체가 될 수 있으므로 위반이 발생 `null` (`Nothing` Visual Basic에서). 위반을 해결 하려면 정적 (Visual Basic에서는 Shared) 메서드를 사용 하 여 복사한 개체 null 인지 확인 합니다.

다음에서 `Person` 클래스 예제는 `other` 에 전달 되는 개체를 `Person` 복사 생성자 않을 `null`.

```csharp
public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor CA1062 fires because other is dereferenced
    // without being checked for null
    public Person(Person other)
        : this(other.Name, other.Age)
    {
    }
}
```

## <a name="example"></a>예제

다음 수정 된 `Person` 예제에서는 합니다 `other` 에서 null에 대 한 복사 생성자에 전달 되는 개체를 먼저 검사는 `PassThroughNonNull` 메서드.

```csharp
public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor
    public Person(Person other)
        : this(PassThroughNonNull(other).Name,
          PassThroughNonNull(other).Age)
    {
    }

    // Null check method
    private static Person PassThroughNonNull(Person person)
    {
        if (person == null)
            throw new ArgumentNullException("person");
        return person;
    }
}
```