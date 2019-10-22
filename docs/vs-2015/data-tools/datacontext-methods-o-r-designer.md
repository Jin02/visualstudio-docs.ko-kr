---
title: DataContext 메서드 (O-R 디자이너) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9d7e0eee35e0f1e62247865bd539aab8d21349d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657399"
---
# <a name="datacontext-methods-or-designer"></a>DataContext 메서드(O/R 디자이너)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DataContext] (assetId://T: qualifyHint = False & autoUpgrade = True) 메서드 ( [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)컨텍스트)는에서 저장 프로시저 및 함수를 실행 하는 <xref:System.Data.Linq.DataContext> 클래스의 메서드입니다. 데이터.

 <xref:System.Data.Linq.DataContext> 클래스는 SQL Server 데이터베이스와 해당 데이터베이스에 매핑되는 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 엔터티 클래스 간의 연결 통로 역할을 하는 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 클래스입니다. @No__t_0 클래스에는 데이터베이스에 연결 하 고 데이터베이스의 데이터를 조작 하기 위한 연결 문자열 정보 및 메서드가 포함 되어 있습니다. 기본적으로 <xref:System.Data.Linq.DataContext> 클래스에는 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 클래스에서 데이터베이스로 업데이트 된 데이터를 보내는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드와 같이 사용자가 호출할 수 있는 여러 메서드가 포함 되어 있습니다. 또한 저장 프로시저 및 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드를 추가로 만들 수 있습니다. 즉 이러한 사용자 지정 메서드를 호출하면 <xref:System.Data.Linq.DataContext> 메서드가 매핑되는 데이터베이스의 저장 프로시저 또는 함수가 실행됩니다. 클래스를 확장하는 메서드를 추가하는 것처럼 <xref:System.Data.Linq.DataContext> 클래스에 새 메서드를 추가할 수 있습니다. 그러나 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 컨텍스트의 <xref:System.Data.Linq.DataContext> 메서드에 대 한 토론에서는 설명 되는 저장 프로시저 및 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드입니다.

## <a name="methods-pane"></a>메서드 창
 저장 프로시저 및 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 메서드 창에 표시됩니다. 메서드 창은 **엔터티** 창 옆에 있는 창입니다 (주 디자인 화면). 메서드 창에는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]를 사용 하 여 만든 모든 <xref:System.Data.Linq.DataContext> 메서드가 나열 됩니다. 기본적으로 메서드 창은 비어 있습니다. **서버 탐색기** /**데이터베이스 탐색기** 에서 저장 프로시저 또는 함수를 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]로 끌어 <xref:System.Data.Linq.DataContext> 메서드를 만들고 메서드 창을 채웁니다. 자세한 내용은 [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기 (O/R 디자이너)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)를 참조 하세요.

> [!NOTE]
> @No__t_0를 마우스 오른쪽 단추로 클릭 한 다음 메서드 창 **숨김** 또는 **메서드 창 표시**를 클릭 하거나 바로 가기 키 CTRL + 1을 사용 하 여 메서드 창을 열고 닫습니다.

## <a name="two-types-of-datacontext-methods"></a>DataContext 메서드의 두 가지 형식
 DataContext 메서드는 데이터베이스의 저장 프로시저와 함수에 매핑되는 메서드로 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 메서드 창에서 만들고 추가할 수 있습니다. <xref:System.Data.Linq.DataContext> 메서드에는 다음과 같이 결과 세트를 하나 이상 반환하는 형식과 반환하지 않는 형식이 있습니다.

- 결과 집합을 하나 이상 반환하는 <xref:System.Data.Linq.DataContext> 메서드

     애플리케이션이 저장 프로시저 및 함수를 데이터베이스에서 실행하고 결과를 반환하는 작업만 수행할 때 이 <xref:System.Data.Linq.DataContext> 메서드를 만듭니다. 자세한 내용은 [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기 (O/R 디자이너)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), ISingleResult \<T > 및 <xref:System.Data.Linq.IMultipleResults>를 참조 하세요.

- 특정 엔터티 클래스에 대한 Inserts, Updates, Deletes 등과 같이 결과 집합을 반환하지 않는 <xref:System.Data.Linq.DataContext> 메서드

     애플리케이션에서 엔터티 클래스와 데이터베이스 간에 수정된 데이터를 저장할 때 기본 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 동작을 사용하는 대신 저장 프로시저를 실행해야 하는 경우 이 <xref:System.Data.Linq.DataContext> 메서드를 만듭니다. 자세한 내용은 [방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)을 참조 하세요.

## <a name="return-types-of-datacontext-methods"></a>DataContext 메서드의 반환 형식
 **서버 탐색기** /**데이터베이스 탐색기** 에서 저장 프로시저 및 함수를 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]로 끌어 오면 생성 된 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 항목을 삭제 하는 위치에 따라 달라 집니다. 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 사용 하 여 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 항목을 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 빈 영역에 놓으면 (두 창) 자동으로 생성 된 형식을 반환 하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 만든 자동 생성 형식의 이름은 저장 프로시저 또는 함수가 반환한 필드에 매핑되는 저장 프로시저 또는 함수의 이름 및 속성과 일치합니다.

> [!NOTE]
> 메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 검사하거나 변경하려면 해당 메서드를 선택하고 **속성** 창에서 **반환 형식** 속성을 검사합니다. 자세한 내용은 [방법: DataContext 메서드의 반환 형식 변경 (O/R 디자이너)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)을 참조 하세요.

 데이터베이스에서 O/R 디자이너 화면으로 끌어 오는 개체는 데이터베이스의 개체 이름을 기초로 이름이 자동으로 지정됩니다. 같은 개체를 두 번 이상 끌어 오면 이름을 구별할 수 있도록 새 이름 끝에 숫자가 추가됩니다. 데이터베이스 개체 이름에 공백이 포함되어 있거나 Visual Basic 또는 C#에서 지원되지 않는 문자가 사용되었으면 해당 공백이나 잘못된 문자가 밑줄로 대체됩니다.

## <a name="see-also"></a>관련 항목:
 [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md) [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655) [저장 프로시저](https://msdn.microsoft.com/library/4d23dd7a-a85f-44ff-a717-af7d0950c0fc) [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기 (O/R 디자이너)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md) [방법: 업데이트, 삽입을 수행 하는 저장 프로시저 할당 및 삭제 (O/R 디자이너)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md) [연습: 엔터티 클래스의 삽입, 업데이트 및 삭제 동작 사용자 지정](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md) [연습: LINQ to SQL 클래스 만들기 (O-R 디자이너)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)
