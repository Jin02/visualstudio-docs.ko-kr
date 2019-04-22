---
title: Tableadapter 만들기 및 구성 | Microsoft Docs
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
- table adapters, creating
- creating TableAdapters
- data [Visual Studio], creating data components
- data [Visual Studio], TableAdapters
- data [Visual Studio], creating table adapters
ms.assetid: 08630d69-0d6c-4e8f-b42d-2922f45f8415
caps.latest.revision: 33
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d6b6428681815f20951b090075e859959a4e3180
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59660863"
---
# <a name="create-and-configure-tableadapters"></a>TableAdapter 만들기 및 구성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tableadapter 응용 프로그램과 데이터베이스 간에 통신을 제공합니다. 데이터베이스, 쿼리 실행된 또는 저장된 프로시저에 연결 하 고 새 데이터를 반환 하거나 테이블 또는 기존 채우기 <xref:System.Data.DataTable> 반환된 된 데이터를 사용 하 여 합니다. 또한 Tableadapter 다시 데이터베이스에 응용 프로그램에서 업데이트 된 데이터를 보낼 수 있습니다.  
  
 다음 작업 중 하나를 수행 하는 경우에 Tableadapter는 만들어집니다.  
  
- 실행 된 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f) 중 하나를 선택 하 고는 **데이터베이스** 또는 **웹 서비스** 데이터 원본 유형입니다.  
  
- 데이터베이스 개체를 끌어 [서버 탐색기](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d) 에 **데이터 집합 디자이너**합니다.  
  
  새 TableAdapter를 만들를 도구 상자에서 TableAdapter의 빈 영역을 끌어 데이터 원본으로 구성 합니다 **데이터 집합 디자이너** 화면.  
  
  Tableadapter 소개를 참조 하세요 [Tableadapter를 사용 하 여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)합니다.  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="use-the-tableadapter-configuration-wizard"></a>TableAdapter 구성 마법사를 사용 합니다.  
 실행 합니다 **TableAdapter 구성 마법사** 만들거나 Tableadapter 및 관련된 Datatable을 편집 합니다. 마우스 오른쪽 단추로 클릭 하 여 기존 TableAdapter를 구성할 수 있습니다 합니다 **데이터 집합 디자이너**합니다.  
  
 ![테이블 어댑터 구성 마법사 raddata](../data-tools/media/raddata-table-adapter-configuration-wizard.png "raddata 테이블 어댑터 구성 마법사")  
  
 도구 상자에서 새 TableAdapter를 끌면 때 합니다 **데이터 집합 디자이너** 에 포커스를 마법사의 메시지에 TableAdapter에 연결 해야 하는 데이터 원본을 지정할 수 있습니다 하 고 새로운 종류의 명령을 통신할 사용 해야 합니다 데이터베이스, SQL 문 또는 저장된 프로시저입니다. 이미 데이터 원본에 연결 되어 있는 TableAdapter를 구성 하는 경우이 표시 되지 않습니다.  
  
-   사용 하 여는 **업데이트를 데이터베이스로 직접 보내는 메서드 만들기** 옵션은 설정에 해당 하는 `GenerateDBDirectMethods` 속성을 true로 합니다. 원래 SQL 문에서 충분한 정보를 제공하지 않거나 쿼리가 업데이트할 수 없는 쿼리인 경우에는 이 옵션을 사용할 수 없습니다. 이에 해당할 수 있습니다, 예를 들어 **조인** 쿼리 및 단일 (스칼라) 값을 반환 하는 쿼리.  
  
-   데이터베이스에 대 한 올바른 권한이 있는 경우 기본 데이터베이스에 새 저장된 프로시저를 만드는 옵션이 있습니다. 이러한 권한이 없으면이 옵션이 없습니다.  
  
-   에 대 한 기존 저장된 프로시저를 실행할 수도 있습니다는 **선택**를 **삽입**를 **업데이트**, 및 **삭제** 명령에는 TableAdapter입니다. 에 할당 되는 저장된 프로시저는 **업데이트** 명령인 예를 들어, 실행 되는 경우는 `TableAdapter.Update()` 메서드가 호출 됩니다.  
  
     선택한 저장 프로시저에서 데이터 테이블의 해당 열로 매개 변수를 매핑합니다. 예를 들어 명명 된 매개 변수를 허용 하는 저장된 프로시저 `@CompanyName` 에 전달 하는 합니다 `CompanyName` 테이블의 열 집합을 **원본 열** 의 `@CompanyName` 매개 변수를 `CompanyName`.  
  
    > [!NOTE]
    >  SELECT 명령에 할당 되는 저장된 프로시저는 마법사의 다음 단계에서 이름을 지정 하는 TableAdapter의 메서드를 호출 하 여 실행 됩니다. 기본 방법은 `Fill`이므로 SELECT 프로시저를 실행 하려면 일반적으로 사용 되는 코드는 `TableAdapter.Fill(tableName)`합니다. 기본 이름을 변경 하면 `Fill`를 대체할 `Fill` 이름의 할당 하 고이 "TableAdapter" TableAdapter의 실제 이름으로 바꿉니다 (예를 들어 `CustomersTableAdapter`).  
  
-   합니다 **고급 옵션** 마법사를 사용 하도록 설정에 정의 된 SELECT 문을 기반으로 하는 INSERT, UPDATE 및 DELETE 문을 생성 하는 **SQL 문 생성** 페이지입니다. 낙관적 동시성을 사용 하 고 문이 실행 될 after INSERT 및 UPDATE 데이터 테이블을 새로 고칠 수 있는지 여부를 지정 합니다.  
  
## <a name="configure-a-tableadapters-fill-method"></a>TableAdapter의 Fill 메서드를 구성 합니다.  
 TableAdapter의 테이블의 스키마를 변경 하는 경우가 있습니다. 이 작업을 수행 하려면 TableAdapter의 기본 수정 `Fill` 메서드. 주 복제본을 사용 하 여 Tableadapter를 만들 `Fill` 연결된 된 데이터 테이블의 스키마를 정의 하는 메서드입니다. 주 `Fill` 메서드 쿼리 또는 TableAdapter를 처음 구성할 때 입력 한 저장된 프로시저를 기반으로 합니다. 이 데이터 집합 디자이너에서 데이터 테이블에서 첫 번째 (최상위) 메서드입니다.  
  
 ![여러 개의 쿼리가 있는 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
 TableAdapter에 수행한 모든 변경 내용을 주 `Fill` 메서드는 연결된 된 데이터 테이블의 스키마에 반영 됩니다. 예를 들어, 기본에서 쿼리에서 열 제거 `Fill` 메서드 또한 연결된 된 데이터 테이블에서 열을 제거 합니다. 또한 기본에서 열을 제거 `Fill` 메서드는 TableAdapter에 대 한 모든 추가 쿼리에서 열을 제거 합니다.  
  
 만들고 TableAdapter에 대 한 추가 쿼리를 편집 하려면 TableAdapter 쿼리 구성 마법사를 사용할 수 있습니다. 이러한 추가 쿼리는 스칼라 값을 반환 하지 않는 한 테이블 스키마를 준수 해야 합니다.  지정 된 이름이 추가 쿼리 (예를 들어 `CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`.)  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>새 쿼리를 사용 하 여 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
1.  **데이터 세트 디자이너**에서 데이터 세트를 엽니다.  
  
2.  끌어 새 쿼리를 만드는 경우는 **쿼리** 에서 개체를 **데이터 집합** 탭을 **도구 상자** 에 <xref:System.Data.DataTable>를 선택 또는 **추가 쿼리**TableAdapter의 바로 가기 메뉴에서. 끌 수도 있습니다는 **쿼리** 개체의 빈 영역에는 **데이터 집합 디자이너**, 없이 연결 된 TableAdapter를 만듭니다 <xref:System.Data.DataTable>합니다. 이러한 쿼리를 실행된 하는 UPDATE, INSERT 또는 단일 (스칼라) 값을 반환 하거나 DELETE 명령을 데이터베이스에 대해만 수 있습니다.  
  
3.  에 **데이터 연결 선택** 화면을 선택 하거나 쿼리를 사용 하는 연결을 만듭니다.  
  
    > [!NOTE]
    >  이 화면 디자이너를 사용 하려면 적절 한 연결을 확인할 수 없는 경우 또는 연결이 없는 경우에 표시 됩니다.  
  
4.  에 **명령 유형을 선택** 화면에서의 데이터베이스에서 데이터를 가져오는 다음 방법 중에서 선택 합니다.  
  
    -   **SQL 문을 사용 하 여** 데이터베이스에서 데이터를 선택 하는 SQL 문을 입력할 수 있습니다.  
  
    -   **새 저장된 프로시저를 만들** 사용 하도록 설정 하면 마법사가 만든 새 저장 프로시저 (데이터베이스)를 지정 된 SELECT 문을 기반으로 합니다.  
  
    -   **기존 저장된 프로시저를 사용 하 여** 쿼리를 실행 하는 경우 기존 저장된 프로시저를 실행할 수 있습니다.  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>기존 쿼리는 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
-   기존 TableAdapter 쿼리를 편집 하는 경우 쿼리를 마우스 오른쪽 단추로 클릭 하 고 선택한 **구성** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  TableAdapter를 재구성 TableAdapter의 주 쿼리를 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Data.DataTable> 스키마입니다. 그러나 선택한 쿼리를만 구성 TableAdapter에서 추가 쿼리를 마우스 오른쪽 단추로 클릭 합니다. 합니다 **TableAdapter 구성 마법사** TableAdapter 쿼리 구성 마법사만 선택한 쿼리를 다시 구성 하는 동안에 TableAdapter 정의 다시 구성 합니다.  
  
#### <a name="to-add-a-global--query-to-a-tableadapter"></a>TableAdapter에 전역 쿼리를 추가 하려면  
  
-   *전역 쿼리* 는 단일 (스칼라) 값 또는 값을 반환 하는 SQL 쿼리입니다. 일반적으로 전역 함수 삽입, 업데이트, 삭제와 같은 데이터베이스 작업을 수행 합니다. 테이블 또는 특정 순서로 모든 항목에 대 한 총 요금은 고객의 수가 같은 정보를 집계할 수도 있습니다.  
  
     드래그 하 여 전역 쿼리 추가 **쿼리** 에서 개체를 **데이터 집합** 탭의 **도구 상자** 의 빈 영역으로 끌어는 **데이터 집합 디자이너**.  
  
-   예를 들어 원하는 작업을 수행 하는 쿼리를 제공 `SELECT COUNT(*) AS CustomerCount FROM Customers`합니다.  
  
    > [!NOTE]
    >  끌어를 **쿼리** 직접 개체를 **데이터 집합 디자이너** 스칼라 (단일) 값만 반환 하는 메서드를 만듭니다. 쿼리 또는 저장된 프로시저를 선택 하면 보다 단일 값을 반환할 수 있습니다, 하는 동안 마법사에서 만들어지는 메서드만 단일 값을 반환 합니다. 예를 들어 쿼리는 반환된 된 데이터의 첫 번째 행의 첫 번째 열을 반환할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter를 사용하여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)
