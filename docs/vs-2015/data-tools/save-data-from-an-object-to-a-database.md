---
title: 개체의 데이터를 데이터베이스에 저장 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], saving
- data access [Visual Studio], objects
- saving data
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6c1470c831177e74e7670d696b44fc2b0119a9a9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72607450"
---
# <a name="save-data-from-an-object-to-a-database"></a>개체에서 데이터베이스로 데이터 저장
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

개체의 값을 TableAdapter의 DBDirect 메서드 중 하나로 전달 하 여 개체의 데이터를 데이터베이스에 저장할 수 있습니다 (예: `TableAdapter.Insert`).

 개체 컬렉션의 데이터를 저장 하려면 개체의 컬렉션을 반복 하 고 (예: for next loop) TableAdapter의 DBDirect 메서드 중 하나를 사용 하 여 각 개체의 값을 데이터베이스로 보냅니다.

 기본적으로 DBDirect 메서드는 데이터베이스에 대해 직접 실행할 수 있는 TableAdapter에 생성 됩니다. 이러한 메서드는 직접 호출할 수 있으며 데이터베이스에 업데이트를 전송 하기 위해 변경 내용을 조정 하기 위해 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable> 개체가 필요 하지 않습니다.

> [!NOTE]
> TableAdapter를 구성 하는 경우 기본 쿼리는 DBDirect 메서드를 만들 수 있는 충분 한 정보를 제공 해야 합니다. 예를 들어 기본 키 열이 정의 되지 않은 테이블의 데이터를 쿼리하도록 TableAdapter가 구성 된 경우 DBDirect 메서드를 생성 하지 않습니다.

|TableAdapter DBDirect 메서드|설명|
|----------------------------------|-----------------|
|`TableAdapter.Insert`|데이터베이스에 새 레코드를 추가 하 고 개별 열 값을 메서드 매개 변수로 전달할 수 있도록 합니다.|
|`TableAdapter.Update`|데이터베이스의 기존 레코드를 업데이트 합니다. @No__t_0 메서드는 원래 열 값과 새 열 값을 메서드 매개 변수로 사용 합니다. 원래 값을 사용 하 여 원래 레코드를 찾은 다음 새 값을 사용 하 여 해당 레코드를 업데이트 합니다.<br /><br /> @No__t_0 메서드는 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow> 또는 <xref:System.Data.DataRow>s 배열을 메서드 매개 변수로 사용 하 여 데이터 집합의 변경 내용을 데이터베이스에 다시 조정 하는 데도 사용 됩니다.|
|`TableAdapter.Delete`|메서드 매개 변수로 전달 된 원래 열 값을 기준으로 데이터베이스에서 기존 레코드를 삭제 합니다.|

### <a name="to-save-new-records-from-an-object-to-a-database"></a>개체의 새 레코드를 데이터베이스에 저장 하려면

- @No__t_0 메서드에 값을 전달 하 여 레코드를 만듭니다.

     다음 예에서는 `currentCustomer` 개체의 값을 `TableAdapter.Insert` 메서드에 전달 하 여 `Customers` 테이블에 새 고객 레코드를 만듭니다.

     [!code-csharp[VbRaddataSaving#23](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#23)]
     [!code-vb[VbRaddataSaving#23](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#23)]

### <a name="to-update-existing-records-from-an-object-to-a-database"></a>개체의 기존 레코드를 데이터베이스로 업데이트 하려면

- @No__t_0 메서드를 호출 하 여 레코드를 업데이트 하 고 레코드를 업데이트 하기 위해 새 값을 전달 하 여 레코드를 수정 하 고 원래 값을 전달 하 여 레코드를 찾습니다.

    > [!NOTE]
    > 개체는 `Update` 메서드에 전달 하기 위해 원래 값을 유지 해야 합니다. 이 예제에서는 `orig` 접두사가 포함 된 속성을 사용 하 여 원래 값을 저장 합니다.

     다음 예에서는 `Customer` 개체의 새 값과 원래 값을 `TableAdapter.Update` 메서드로 전달 하 여 `Customers` 테이블의 기존 레코드를 업데이트 합니다.

     [!code-csharp[VbRaddataSaving#24](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#24)]
     [!code-vb[VbRaddataSaving#24](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#24)]

### <a name="to-delete-existing-records-from-a-database"></a>데이터베이스에서 기존 레코드를 삭제 하려면

- @No__t_0 메서드를 호출 하 고 원래 값을 전달 하 여 레코드를 찾는 방법으로 레코드를 삭제 합니다.

    > [!NOTE]
    > 개체는 `Delete` 메서드에 전달 하기 위해 원래 값을 유지 해야 합니다. 이 예제에서는 `orig` 접두사가 포함 된 속성을 사용 하 여 원래 값을 저장 합니다.

     다음 예에서는 `Customer` 개체의 원래 값을 `TableAdapter.Delete` 메서드로 전달 하 여 `Customers` 테이블에서 레코드를 삭제 합니다.

     [!code-csharp[VbRaddataSaving#25](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#25)]
     [!code-vb[VbRaddataSaving#25](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#25)]

## <a name="net-framework-security"></a>.NET Framework 보안
 데이터베이스의 테이블에서 선택한 삽입, 업데이트 또는 삭제를 수행할 수 있는 권한이 있어야 합니다.

## <a name="see-also"></a>관련 항목:
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)
