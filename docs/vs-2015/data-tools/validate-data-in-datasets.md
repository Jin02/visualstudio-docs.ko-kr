---
title: 데이터 집합의 데이터 유효성 검사 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
f1_keywords:
- DataTable.ColumnChanging
- System.Data.DataTable.ColumnChanging
- System.Data.DataTable.RowChanging
- DataTable.RowChanging
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data validation, datasets
- data validation
- validating data, datasets
- updating datasets, validating data
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
caps.latest.revision: 27
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8d42553fbee6de6a89e16716a191db8a3d9fb883
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72621062"
---
# <a name="validate-data-in-datasets"></a>데이터 세트의 데이터 유효성 검사
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터 유효성 검사는 데이터 개체에 입력 된 값이 데이터 집합의 스키마 내에서 제약 조건을 준수 하는지 확인 하는 프로세스입니다. 또한 유효성 검사 프로세스는 이러한 값이 응용 프로그램에 대해 설정 된 규칙을 따라 수행 되는지 확인 합니다. 기본 데이터베이스에 업데이트를 보내기 전에 데이터의 유효성을 검사 하는 것이 좋습니다. 이렇게 하면 응용 프로그램과 데이터베이스 간의 잠재적 왕복 수 뿐만 아니라 오류가 줄어듭니다.

 데이터 집합 자체에 유효성 검사를 작성 하 여 데이터 집합에 기록 되 고 있는 데이터가 유효한 지 확인할 수 있습니다. 데이터 집합은 업데이트가 수행 되는 방식에 관계 없이 (폼의 컨트롤에서 직접 또는 구성 요소 내에서) 또는 다른 방식으로 데이터를 확인할 수 있습니다. 데이터 집합은 데이터베이스 백 엔드와 달리 응용 프로그램의 일부 이기 때문에 응용 프로그램별 유효성 검사를 빌드하는 논리적 장소입니다.

 응용 프로그램에 유효성 검사를 추가 하는 가장 좋은 장소는 데이터 집합의 partial 클래스 파일에 있습니다. @No__t_0 또는 [!INCLUDE[csprcs](../includes/csprcs-md.md)]에서 **데이터 세트 디자이너** 을 열고 유효성 검사를 만들 열 또는 테이블을 두 번 클릭 합니다. 이 작업은 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기를 자동으로 만듭니다. 자세한 내용은 [방법: 열을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5) 하거나 다음으로 [How 합니다. 행을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc) 합니다. 전체 예제는 [Walkthrough를 참조 하세요. 데이터 집합 ](https://msdn.microsoft.com/library/09351fab-d670-45e3-b53a-a944eff717e7)에 유효성 검사를 추가 합니다.

## <a name="validate-data"></a>데이터 유효성 검사
 데이터 집합 내에서 유효성 검사는 다음과 같은 방법으로 수행할 수 있습니다.

- 변경 하는 동안 개별 데이터 열의 값을 검사할 수 있는 응용 프로그램별 유효성 검사를 만듭니다.  자세한 내용은 [방법: 열을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5) 합니다.

- 전체 데이터 행을 변경 하는 동안 데이터를 확인할 수 있는 고유한 응용 프로그램별 유효성 검사를 만듭니다. 자세한 내용은 [방법: 행을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc) 합니다.

- 데이터 집합의 실제 스키마 정의의 일부로 키, unique 제약 조건 등을 만듭니다. 스키마 정의에 유효성 검사를 통합 하는 방법에 대 한 자세한 내용은 [고유 값을 포함 하도록 DataColumn 제한](https://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)을 참조 하세요.

- @No__t_1, <xref:System.Data.DataColumn.AllowDBNull%2A> 및 <xref:System.Data.DataColumn.Unique%2A>과 같은 <xref:System.Data.DataColumn> 개체의 속성을 설정 합니다.

  레코드에서 변경이 발생 하는 경우 <xref:System.Data.DataTable> 개체에 의해 발생 하는 몇 가지 이벤트는 다음과 같습니다.

- @No__t_0 및 <xref:System.Data.DataTable.ColumnChanged> 이벤트는 개별 열을 변경할 때마다 발생 합니다. @No__t_0 이벤트는 특정 열의 변경 내용에 대 한 유효성을 검사 하려는 경우에 유용 합니다. 제안 된 변경에 대 한 정보는 이벤트와 함께 인수로 전달 됩니다. 자세한 내용은 [방법: 열을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5) 합니다.

- @No__t_0 및 <xref:System.Data.DataTable.RowChanged> 이벤트는 행을 변경한 후에 발생 합니다. @No__t_0 이벤트는 더 일반적입니다. 이는 행에서 변경 내용이 발생 하지만 변경 된 열을 알 수 없음을 나타냅니다. 자세한 내용은 [방법: 행을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc) 합니다.

  기본적으로 열을 변경할 때마다 4 개의 이벤트가 발생 합니다. 첫 번째는 변경 중인 특정 열에 대 한 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.ColumnChanged> 이벤트입니다. 다음은 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트입니다. 행이 여러 번 변경 되 면 각 변경에 대해 이벤트가 발생 합니다.

> [!NOTE]
> 데이터 행의 <xref:System.Data.DataRow.BeginEdit%2A> 메서드는 개별 열이 변경 된 후 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트를 해제 합니다. 이 경우 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트가 한 번만 발생 하면 <xref:System.Data.DataRow.EndEdit%2A> 메서드가 호출 될 때까지 이벤트가 발생 하지 않습니다. 자세한 내용은 [데이터 집합을 채우는 동안 제약 조건](../data-tools/turn-off-constraints-while-filling-a-dataset.md)해제를 참조 하세요.

 선택 하는 이벤트는 유효성 검사를 수행할 세부적인 방법에 따라 달라 집니다. 열이 변경 될 때 즉시 오류를 catch 하는 것이 중요 한 경우 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 사용 하 여 유효성 검사를 빌드합니다. 그렇지 않으면 <xref:System.Data.DataTable.RowChanging> 이벤트를 사용 하 여 한 번에 여러 오류를 catch 할 수 있습니다. 또한 데이터를 구조화 하 여 한 열의 값이 다른 열의 내용을 기준으로 유효성을 검사 하도록 하려면 <xref:System.Data.DataTable.RowChanging> 이벤트 중에 유효성 검사를 수행 합니다.

 레코드가 업데이트 되 면 변경 내용이 발생 하 고 변경 내용이 적용 된 후에 응답할 수 있는 이벤트가 <xref:System.Data.DataTable> 개체에 발생 합니다.

 응용 프로그램에서 형식화 된 데이터 집합을 사용 하는 경우 강력한 형식의 이벤트 처리기를 만들 수 있습니다. @No__t_0, `dataTableNameRowChanged`, `dataTableNameRowDeleting` 및 `dataTableNameRowDeleted`에 대 한 처리기를 만들 수 있는 형식화 된 이벤트를 4 개 추가 합니다. 이러한 형식화 된 이벤트 처리기는 코드를 더 쉽게 작성 하 고 읽을 수 있도록 테이블의 열 이름이 포함 된 인수를 전달 합니다.

## <a name="data-update-events"></a>데이터 업데이트 이벤트

|이벤트|설명|
|-----------|-----------------|
|<xref:System.Data.DataTable.ColumnChanging>|열의 값이 변경 되 고 있습니다. 이 이벤트는 제안 된 새 값과 함께 행과 열을 사용자에 게 전달 합니다.|
|<xref:System.Data.DataTable.ColumnChanged>|열의 값이 변경 되었습니다. 이벤트는 제안 된 값과 함께 행과 열을 사용자에 게 전달 합니다.|
|<xref:System.Data.DataTable.RowChanging>|@No__t_0 개체에 대 한 변경 내용은 데이터 집합으로 다시 커밋됩니다. @No__t_0 메서드를 호출 하지 않은 경우 <xref:System.Data.DataTable.ColumnChanging> 이벤트가 발생 한 직후에 열을 변경할 때마다 <xref:System.Data.DataTable.RowChanging> 이벤트가 발생 합니다. 변경을 수행 하기 전에 <xref:System.Data.DataRow.BeginEdit%2A>를 호출한 경우 <xref:System.Data.DataRow.EndEdit%2A> 메서드를 호출 하는 경우에만 <xref:System.Data.DataTable.RowChanging> 이벤트가 발생 합니다.<br /><br /> 이벤트는 수행 중인 작업 유형 (변경, 삽입 등)을 나타내는 값과 함께 사용자에 게 행을 전달 합니다.|
|<xref:System.Data.DataTable.RowChanged>|행이 변경 되었습니다. 이벤트는 수행 중인 작업 유형 (변경, 삽입 등)을 나타내는 값과 함께 사용자에 게 행을 전달 합니다.|
|<xref:System.Data.DataTable.RowDeleting>|행을 삭제 하 고 있습니다. 이벤트는 수행 중인 작업 유형 (delete)을 나타내는 값과 함께 행을 사용자에 게 전달 합니다.|
|<xref:System.Data.DataTable.RowDeleted>|행이 삭제 되었습니다. 이벤트는 수행 중인 작업 유형 (delete)을 나타내는 값과 함께 행을 사용자에 게 전달 합니다.|

 @No__t_0, <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowDeleting> 이벤트는 업데이트 프로세스 중에 발생 합니다. 이러한 이벤트를 사용 하 여 데이터의 유효성을 검사 하거나 다른 유형의 처리를 수행할 수 있습니다. 이러한 이벤트 중에 업데이트가 진행 되 고 있으므로 예외를 throw 하 여 업데이트를 취소할 수 있습니다. 이렇게 하면 업데이트를 완료할 수 없습니다.

 @No__t_0, <xref:System.Data.DataTable.RowChanged> 및 <xref:System.Data.DataTable.RowDeleted> 이벤트는 업데이트가 성공적으로 완료 될 때 발생 하는 알림 이벤트입니다. 이러한 이벤트는 성공적인 업데이트를 기반으로 하 여 추가 작업을 수행 하려는 경우에 유용 합니다.

## <a name="validate-data-during-column-changes"></a>열 변경 중 데이터 유효성 검사

> [!NOTE]
> **데이터 세트 디자이너** 유효성 검사 논리를 데이터 집합에 추가할 수 있는 partial 클래스를 만듭니다. 디자이너에서 생성 된 데이터 집합은 partial 클래스의 코드를 삭제 하거나 변경 하지 않습니다.

 @No__t_0 이벤트에 응답 하 여 데이터 열의 값이 변경 되 면 데이터의 유효성을 검사할 수 있습니다. 이 이벤트는 발생 하면 현재 열에 대해 제안 되는 값을 포함 하는 이벤트 인수 (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>)를 전달 합니다. @No__t_0의 내용에 따라 다음을 수행할 수 있습니다.

- 아무 작업도 수행 하지 않고 제안 된 값을 적용 합니다.

- 열 변경 이벤트 처리기 내에서 열 오류 (<xref:System.Data.DataRow.SetColumnError%2A>)를 설정 하 여 제안 된 값을 거부 합니다.

- 필요에 따라 <xref:System.Windows.Forms.ErrorProvider> 컨트롤을 사용 하 여 사용자에 게 오류 메시지를 표시 합니다. 자세한 내용은 [ErrorProvider 구성 요소](https://msdn.microsoft.com/library/c0f2e231-c5c9-413d-a507-75af2db499b6)를 참조 하세요.

  @No__t_0 이벤트 중에 유효성 검사를 수행할 수도 있습니다. 자세한 내용은 [방법: 행을 변경 하는 동안 데이터의 유효성을 검사 ](https://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc) 합니다.

## <a name="validate-data-during-row-changes"></a>행을 변경 하는 동안 데이터 유효성 검사
 유효성을 검사 하려는 각 열에 응용 프로그램의 요구 사항을 충족 하는 데이터가 포함 되어 있는지 확인 하는 코드를 작성할 수 있습니다. 이렇게 하려면 제안 된 값이 허용 되지 않는 경우 오류가 포함 되어 있음을 나타내도록 열을 설정 합니다. 다음 예에서는 `Quantity` 열이 0 이하인 경우 열 오류를 설정 합니다. 행 변경 이벤트 처리기는 다음 예제와 유사 합니다.

#### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>행이 변경 될 때 데이터의 유효성을 검사 하려면 (Visual Basic)

1. **데이터 세트 디자이너**에서 데이터 세트를 엽니다. 자세한 내용은 [방법: 데이터 세트 디자이너 ](https://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)에서 데이터 집합을 엽니다.

2. 유효성을 검사할 테이블의 제목 표시줄을 두 번 클릭 합니다. 이 작업을 수행 하면 데이터 집합의 partial 클래스 파일에 <xref:System.Data.DataTable>의 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기가 자동으로 만들어집니다.

    > [!TIP]
    > 테이블 이름 왼쪽을 두 번 클릭 하 여 행 변경 이벤트 처리기를 만듭니다. 테이블 이름을 두 번 클릭 하면 편집할 수 있습니다.

     [!code-vb[VbRaddataValidating#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataValidating/VB/NorthwindDataSet.vb#3)]

#### <a name="to-validate-data-when-a-row-changes-c"></a>행이 변경 될 때 데이터의 유효성C#을 검사 하려면 ()

1. **데이터 세트 디자이너**에서 데이터 세트를 엽니다. 자세한 내용은 [방법: 데이터 세트 디자이너 ](https://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)에서 데이터 집합을 엽니다.

2. 유효성을 검사할 테이블의 제목 표시줄을 두 번 클릭 합니다. 이 작업은 <xref:System.Data.DataTable>에 대 한 부분 클래스 파일을 만듭니다.

    > [!NOTE]
    > **데이터 세트 디자이너** 는 <xref:System.Data.DataTable.RowChanging> 이벤트에 대 한 이벤트 처리기를 자동으로 만들지 않습니다. @No__t_0 이벤트를 처리 하는 메서드를 만들고 코드를 실행 하 여 테이블의 초기화 메서드에서 이벤트를 연결 해야 합니다.

3. Partial 클래스에 다음 코드를 복사 합니다.

    ```
    public override void EndInit()
    {
        base.EndInit();
        Order_DetailsRowChanging += TestRowChangeEvent;
    }

    public void TestRowChangeEvent(object sender, Order_DetailsRowChangeEvent e)
    {
        if ((short)e.Row.Quantity <= 0)
        {
            e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
        }
        else
        {
            e.Row.SetColumnError("Quantity", "");
        }
    }
    ```

## <a name="to-retrieve-changed-rows"></a>변경 된 행을 검색 하려면
 데이터 테이블의 각 행에는 <xref:System.Data.DataRowState> 열거형의 값을 사용 하 여 해당 행의 현재 상태를 추적 하는 <xref:System.Data.DataRow.RowState%2A> 속성이 있습니다. @No__t_1 또는 <xref:System.Data.DataTable>의 `GetChanges` 메서드를 호출 하 여 데이터 집합 또는 데이터 테이블에서 변경 된 행을 반환할 수 있습니다. 데이터 집합의 <xref:System.Data.DataSet.HasChanges%2A> 메서드를 호출 하 여 `GetChanges`를 호출 하기 전에 변경 내용이 존재 하는지 확인할 수 있습니다. <xref:System.Data.DataSet.HasChanges%2A>에 대한 자세한 내용은 [방법: @No__t_0 변경 된 행을 확인 합니다.

> [!NOTE]
> @No__t_0 메서드를 호출 하 여 데이터 집합 또는 데이터 테이블에 대 한 변경 내용을 커밋한 후 `GetChanges` 메서드는 데이터를 반환 하지 않습니다. 응용 프로그램에서 변경 된 행을 처리 해야 하는 경우 `AcceptChanges` 메서드를 호출 하기 전에 변경 내용을 처리 해야 합니다.

 데이터 집합 또는 데이터 테이블의 <xref:System.Data.DataSet.GetChanges%2A> 메서드를 호출 하면 변경 된 레코드만 포함 된 새 데이터 집합 또는 데이터 테이블이 반환 됩니다. 특정 레코드 (예: 새 레코드 또는 수정 된 레코드만)를 가져오려는 경우 <xref:System.Data.DataRowState> 열거형의 값을 `GetChanges` 메서드에 매개 변수로 전달할 수 있습니다.

 @No__t_0 열거를 사용 하 여 행을 처리 하기 전에 행에 있던 원래 값과 같은 다른 버전의 행에 액세스할 수 있습니다.

#### <a name="to-get-all-changed-records-from-a-dataset"></a>데이터 집합에서 변경 된 모든 레코드를 가져오려면

- 데이터 집합의 <xref:System.Data.DataSet.GetChanges%2A> 메서드를 호출 합니다.

     다음 예에서는 `changedRecords` 라는 새 데이터 집합을 만들고 `dataSet1` 라는 다른 데이터 집합의 모든 변경 된 레코드로 채웁니다.

     [!code-csharp[VbRaddataEditing#14](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#14)]
     [!code-vb[VbRaddataEditing#14](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#14)]

#### <a name="to-get-all-changed-records-from-a-data-table"></a>데이터 테이블에서 변경 된 모든 레코드를 가져오려면

- DataTable의 <xref:System.Data.DataTable.GetChanges%2A> 메서드를 호출 합니다.

     다음 예에서는 `changedRecordsTable` 라는 새 데이터 테이블을 만들고 `dataTable1` 라는 다른 데이터 테이블의 모든 변경 된 레코드로 채웁니다.

     [!code-csharp[VbRaddataEditing#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#15)]
     [!code-vb[VbRaddataEditing#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#15)]

#### <a name="to-get-all-records-that-have-a-specific-row-state"></a>특정 행 상태를 포함 하는 모든 레코드를 가져오려면

- 데이터 집합 또는 데이터 테이블의 `GetChanges` 메서드를 호출 하 고 <xref:System.Data.DataRowState> 열거형 값을 인수로 전달 합니다.

     다음 예제에서는 `addedRecords` 라는 새 데이터 집합을 만들고 `dataSet1` 데이터 집합에 추가 된 레코드를 사용 하 여이를 채우는 방법을 보여 줍니다.

     [!code-csharp[VbRaddataEditing#16](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#16)]
     [!code-vb[VbRaddataEditing#16](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#16)]

- 다음 예에서는 `Customers` 테이블에 최근에 추가 된 모든 레코드를 반환 하는 방법을 보여 줍니다.

     [!code-csharp[VbRaddataEditing#17](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#17)]
     [!code-vb[VbRaddataEditing#17](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#17)]

## <a name="access-the-original-version-of-a-datarow"></a>DataRow의 원래 버전에 액세스
 데이터 행이 변경 되 면 데이터 집합은 행의 원래 (<xref:System.Data.DataRowVersion>) 버전과 새 (<xref:System.Data.DataRowVersion>) 버전을 모두 유지 합니다. 예를 들어 `AcceptChanges` 메서드를 호출 하기 전에 응용 프로그램은 <xref:System.Data.DataRowVersion> 열거형에 정의 된 것과 같은 다른 버전의 레코드에 액세스 하 고 그에 따라 변경 내용을 처리할 수 있습니다.

> [!NOTE]
> 서로 다른 버전의 행은 편집 된 후 `AcceptChanges` 메서드가 호출 되기 전에만 존재 합니다. @No__t_0 메서드를 호출한 후에는 현재 버전과 원래 버전이 동일 합니다.

 열 인덱스 (또는 열 이름)와 함께 <xref:System.Data.DataRowVersion> 값을 전달 하면 해당 열의 특정 행 버전에서 값이 반환 됩니다. 변경 된 열은 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.ColumnChanged> 이벤트 중에 식별 됩니다. 유효성 검사를 위해 다른 행 버전을 검사 하는 것이 좋습니다. 그러나 일시적으로 제약 조건을 일시 중단 한 경우 이러한 이벤트는 발생 하지 않으며 변경 된 열을 프로그래밍 방식으로 식별 해야 합니다. @No__t_0 컬렉션을 반복 하 고 다른 <xref:System.Data.DataRowVersion> 값을 비교 하 여이 작업을 수행할 수 있습니다.

#### <a name="to-get-the-original-version-of-a-record"></a>레코드의 원래 버전을 가져오려면

- 반환할 행의 <xref:System.Data.DataRowVersion>를 전달 하 여 열의 값에 액세스 합니다.

     다음 예에서는 <xref:System.Data.DataRowVersion> 값을 사용 하 여 <xref:System.Data.DataRow>에서 `CompanyName` 필드의 원래 값을 가져오는 방법을 보여 줍니다.

     [!code-csharp[VbRaddataEditing#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#21)]
     [!code-vb[VbRaddataEditing#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#21)]

## <a name="access-the-current-version-of-a-datarow"></a>DataRow의 현재 버전에 액세스 합니다.

#### <a name="to-get-the-current-version-of-a-record"></a>레코드의 현재 버전을 가져오려면

- 열의 값에 액세스 한 다음 반환할 행의 버전을 나타내는 매개 변수를 인덱스에 추가 합니다.

     다음 예에서는 <xref:System.Data.DataRowVersion> 값을 사용 하 여 <xref:System.Data.DataRow>에서 `CompanyName` 필드의 현재 값을 가져오는 방법을 보여 줍니다.

     [!code-csharp[VbRaddataEditing#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#22)]
     [!code-vb[VbRaddataEditing#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#22)]

## <a name="see-also"></a>참고 항목

- [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성을 검사 ](https://msdn.microsoft.com/library/d10aef35-701e-4a3c-a684-2a2ed1aeaca6)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용 하 여 폼 유효성 검사에 대 한 오류 아이콘을 표시 ](https://msdn.microsoft.com/library/3b681a32-9db4-497b-a34b-34980eabee46)