---
title: '방법: ASP.NET 예외 디버그 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 3289fd82f8a3b99bf49ee796e49a285ffb93793c
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72536015"
---
# <a name="how-to-debug-aspnet-exceptions"></a>방법: ASP.NET 예외 디버깅
예외 디버깅은 강력한 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 애플리케이션을 개발하는 데 중요한 요소입니다. 예외를 디버깅 하는 방법에 대 한 일반적인 정보는 [디버거에서 예외를 관리](../debugger/managing-exceptions-with-the-debugger.md)하는 것입니다.

 처리되지 않은 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외를 디버깅하려면 디버거에서 실행을 중지해야 합니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 런타임에는 최상위 예외 처리기가 있습니다. 따라서 디버거는 처리되지 않은 예외에서 기본적으로 중단되지 않습니다. 예외가 throw될 때 디버거에서 실행을 중단하도록 지정하려면 **예외** 대화 상자에서 특정 예외에 대해 **다음 예외가 발생할 경우 중단: Throw됨** 설정을 선택해야 합니다.

 내 코드만를 사용 하도록 설정한 경우 **다음 예외가 발생할 경우 중단: throw** 됨을 사용 하면 .net 메서드 또는 다른 시스템 코드에서 예외가 throw 되는 경우 디버거가 즉시 중단 되지 않습니다. 이러한 경우 디버거의 실행은 비시스템 코드를 적중해야 중단됩니다. 그러므로 예외가 발생할 때 시스템 코드를 단계별로 수행할 필요가 없습니다.

 내 코드만 옵션을 사용할 경우 더 유용한 다른 옵션(**다음 예외가 발생할 경우 중단: 사용자가 처리하지 않음**)도 사용할 수 있습니다. 예외에 대해 이 설정을 선택하면 디버거는 사용자 코드에서 예외를 catch하여 처리하지 않는 경우에 한해서만 사용자 코드에서 실행을 중단합니다. 이렇게 설정할 경우 최상위 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외 처리기가 사용자가 작성하지 않은 코드에 있기 때문에 해당 처리기의 결과가 무시됩니다.

### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>내 코드만 옵션을 사용하여 ASP.NET 예외 디버깅을 설정하려면

1. **디버그** 메뉴에서 **예외**를 클릭합니다.

     **예외** 대화 상자가 표시됩니다.

2. **Common Language Runtime Exceptions** 행에서 **Throw**되거나 **사용자가 처리하지 않음**을 선택합니다.

     **사용자가 처리하지 않음** 설정을 사용하려면 **내 코드만**을 사용하도록 설정해야 합니다.

### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>최상의 방법으로 ASP.NET 예외 처리를 수행하려면

- 예측 가능하며 처리 방법을 알고 있는 예외를 throw할 수 있는 코드의 바깥쪽에 `try ... catch` 블록을 배치합니다. 예를 들어 애플리케이션에서 XML Web services를 호출하거나 SQL Server를 직접 호출할 경우에는 다양한 예외가 발생할 수 있으므로 해당 코드는 **try ... catch** 블록에 있어야 합니다.

## <a name="see-also"></a>관련 항목:
- [ASP.NET 애플리케이션 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)