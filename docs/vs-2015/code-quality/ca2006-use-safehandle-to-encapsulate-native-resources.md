---
title: 'CA2006: SafeHandle을 사용 하 여 네이티브 리소스 캡슐화 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 394fafb0c9185a5e11ba759a5b873236956cf25b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652205"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|범주|Microsoft.Reliability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
 관리 코드는 <xref:System.IntPtr>를 사용 하 여 네이티브 리소스에 액세스 합니다.

## <a name="rule-description"></a>규칙 설명
 관리 코드에서 `IntPtr`를 사용 하면 잠재적인 보안 및 안정성 문제를 나타낼 수 있습니다. @No__t_0의 모든 용도를 검토 하 여 <xref:System.Runtime.InteropServices.SafeHandle> 또는 유사한 기술을 사용 해야 하는지 여부를 확인 해야 합니다. @No__t_0는 관리 코드를 소유 하 고 있는 것으로 간주 되는 메모리, 파일 핸들 또는 소켓과 같은 일부 네이티브 리소스를 나타내는 경우 발생 합니다. 관리 코드에서 리소스를 소유 하는 경우에는 리소스 유출을 발생 하므로 해당 리소스와 연결 된 네이티브 리소스도 해제 해야 합니다.

 이러한 시나리오에서는 `IntPtr`에 대 한 다중 스레드 액세스가 허용 되 고 `IntPtr` 표시 되는 리소스를 해제 하는 방법이 제공 되는 경우 보안 또는 안정성 문제도 있습니다. 이러한 문제는 리소스 릴리스에 대 한 `IntPtr` 값을 재활용 하는 것과 관련이 있습니다. 반면 리소스의 동시 사용은 다른 스레드에서 수행 됩니다. 이로 인해 한 스레드가 잘못 된 리소스와 연결 된 데이터를 읽거나 쓸 수 있는 경합 상태가 발생할 수 있습니다. 예를 들어, 형식에서 OS 핸들을 `IntPtr` 저장 **하 고 사용자** 가 약간의 동기화를 사용 하지 않고 해당 핸들을 동시에 사용 하는 다른 메서드를 호출할 수 있도록 허용 하는 경우 코드에 핸들 재활용 문제가 있습니다.

 이 핸들 재활용 문제로 인해 데이터가 손상 되거나 보안상 취약 해질 수 있습니다. `SafeHandle` 및 해당 형제 클래스 <xref:System.Runtime.InteropServices.CriticalHandle> 이러한 스레딩 문제를 방지할 수 있도록 리소스에 대 한 기본 핸들을 캡슐화 하는 메커니즘을 제공 합니다. 또한 `SafeHandle` 및 해당 형제 클래스 `CriticalHandle`를 사용 하 여 네이티브 메서드 호출을 통해 네이티브 핸들의 복사본을 포함 하는 관리 되는 개체의 수명을 신중 하 게 제어할 수 있습니다. 이 경우 `GC.KeepAlive`에 대 한 호출을 제거 하는 경우가 많습니다. @No__t_0 및를 사용 하는 경우 발생 하는 성능 오버 헤드는 `CriticalHandle`를 덜 설계 하 여 자주 줄일 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 @No__t_0 사용을 `SafeHandle`으로 변환 하 여 네이티브 리소스에 대 한 액세스를 안전 하 게 관리 합니다. 예제는 <xref:System.Runtime.InteropServices.SafeHandle> 참조 항목을 참조 하세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 경고는 표시 하지 않아야 합니다.

## <a name="see-also"></a>관련 항목:
 <xref:System.IDisposable>
