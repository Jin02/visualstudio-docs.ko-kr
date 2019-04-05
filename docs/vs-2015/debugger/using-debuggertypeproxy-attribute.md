---
title: DebuggerTypeProxy 특성 사용 | Microsoft Docs
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
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca1b84990ed2747e530a1a83a17e17b99f36b116
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58982910"
---
# <a name="using-debuggertypeproxy-attribute"></a>DebuggerTypeProxy 특성 사용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DebuggerTypeProxyAttribute] (assetId:///T:System.Diagnostics.DebuggerTypeProxyAttribute?qualifyHint=False & autoUpgrade = True)에 프록시가 지정 또는 대리 항목 형식과 방법 형식 변경에 대 한 디버거 창에 표시 됩니다. 프록시가 있는 변수를 볼 때 원래 형식 대신 프록시가 **표시**에 나타납니다. 디버거 변수 창에는 프록시 형식의 공용 멤버만 표시됩니다. 개인 멤버는 표시되지 않습니다.  
  
 이 특성은 다음 항목에 적용될 수 있습니다.  
  
- 구조체  
  
- 클래스  
  
- 어셈블리  
  
  형식 프록시 클래스에는 프록시가 대체할 형식의 인수를 사용하는 생성자가 있어야 합니다. 디버거에서는 대상 형식의 변수를 표시해야 할 때마다 형식 프록시 클래스의 새 인스턴스를 만듭니다. 이 경우 성능에 영향을 미칠 수 있으므로 생성자에서는 반드시 필요한 작업만 수행해야 합니다.  
  
  성능 저하를 최소화하기 위해 식 계산기에서는 사용자가 디버거 창에서 + 기호를 클릭하거나 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 사용하여 형식을 확장한 경우가 아니면 형식의 표시 프록시에 대한 특성을 검사하지 않습니다. 따라서 표시 형식 자체에 특성을 배치하면 안 됩니다. 특성은 표시 형식의 본문에서만 사용할 수 있습니다.  
  
  형식 프록시는 특성의 대상인 클래스 내에 중첩된 private 클래스인 것이 좋습니다. 이렇게 하면 형식 프록시에서 내부 멤버에 쉽게 액세스할 수 있습니다.  
  
  <xref:System.Diagnostics.DebuggerTypeProxyAttribute>가 어셈블리 수준에서 사용되는 경우 `Target` 매개 변수는 프록시가 대체할 형식을 지정합니다.  
  
  와 함께이 특성을 사용 하는 방법의 예 <xref:System.Diagnostics.DebuggerDisplayAttribute> 및 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>를 참조 하십시오[DebuggerDisplay 특성을 사용 하 여](../debugger/using-the-debuggerdisplay-attribute.md)합니다.  
  
## <a name="using-generics-with-debuggertypeproxy"></a>DebuggerTypeProxy와 함께 제네릭 사용  
 제네릭에 대한 지원은 제한되어 있습니다. C#의 경우 `DebuggerTypeProxy`는 개방형 형식만 지원합니다. 생성되지 않은 형식이라고도 하는 개방형 형식은 해당 형식 매개 변수의 인수를 사용하여 인스턴스화되지 않은 제네릭 형식입니다. 생성된 형식이라고도 하는 닫힌 형식은 지원되지 않습니다.  
  
 개방형 형식에 대한 구문은 다음과 같습니다.  
  
 `Namespace.TypeName<,>`  
  
 `DebuggerTypeProxy`에서 제네릭 형식을 대상으로 사용하는 경우 이 구문을 사용해야 합니다. `DebuggerTypeProxy` 메커니즘은 형식 매개 변수를 자동으로 유추합니다.  
  
 C#의 개방형 형식과 닫힌 형식에 대 한 자세한 내용은 참조는 [C# 언어 사양](http://msdn.microsoft.com/library/e5d5a5cc-636b-4bff-b9c8-a8edc6207c22), 섹션 20.5.2 개방형 형식 및 닫힌 형식을 합니다.  
  
 Visual Basic에는 개방형 형식 구문이 없으므로 Visual Basic의 경우 이와 같은 작업을 수행할 수 없습니다. 대신 개방형 형식 이름의 문자열 표현을 사용해야 합니다.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>참고 항목  
 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)   
  [디버거 표시 특성을 사용하여 디버깅 향상](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)
