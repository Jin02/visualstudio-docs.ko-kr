---
title: '연습: N 계층 데이터 응용 프로그램 만들기 | Microsoft Docs'
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
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
caps.latest.revision: 51
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f3185a6b7ebe4f5f37428e04f1b4215431921c51
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981487"
---
# <a name="walkthrough-creating-an-n-tier-data-application"></a>연습: N 계층 데이터 애플리케이션 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
N-계층 * 데이터 응용 프로그램은 여러 논리 계층으로 분리 되어 데이터에 액세스 하는 응용 프로그램 또는 *계층*합니다. 응용 프로그램 구성 요소를 개별 계층으로 분리하면 응용 프로그램의 확장성과 유지 관리 가능성이 높아집니다. 이는 전체 솔루션을 다시 설계하지 않고도 단일 계층에 적용할 수 있는 새로운 기술을 보다 쉽게 도입할 수 있기 때문입니다. N 계층 아키텍처에는 표시 계층, 중간 계층 및 데이터 계층이 포함됩니다. 중간 계층에는 대개 데이터 액세스 계층, 비즈니스 논리 계층 및 인증, 유효성 검사 등의 공유 구성 요소가 포함됩니다. 데이터 계층에는 관계형 데이터베이스가 포함됩니다. 표시 계층에 액세스하는 최종 사용자로부터 격리된 상태를 유지하기 위해 N 계층 응용 프로그램에서는 보통 중요한 정보가 중간 계층의 데이터 액세스 계층에 저장됩니다. 자세한 내용은 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)합니다.  
  
 N 계층 응용 프로그램의 여러 계층을 분리하는 방법 중 하나는 응용 프로그램에 포함할 각 계층에 대해 개별 프로젝트를 만드는 것입니다. 형식화된 데이터 집합에는 생성된 데이터 집합 및 `DataSet Project` 코드를 포함해야 하는 프로젝트를 결정하는 `TableAdapter` 속성이 포함됩니다.  
  
 이 연습에서는 **데이터 세트 디자이너**를 사용하여 데이터 세트 및 `TableAdapter` 코드를 개별 클래스 라이브러리 프로젝트로 분리하는 방법을 보여줍니다. 만들려는 데이터 집합 및 TableAdapter 코드를 분리 한 후에 [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) 데이터 액세스 계층을 호출 하는 서비스입니다. 마지막으로 Windows Forms 응용 프로그램을 표시 계층으로 만듭니다. 이 계층은 데이터 서비스에서 데이터에 액세스합니다.  
  
 이 연습에서는 다음 단계를 수행합니다.  
  
- 여러 프로젝트가 포함된 새 N 계층 솔루션을 만듭니다.  
  
- N 계층 솔루션에 클래스 라이브러리 프로젝트 두 개를 추가합니다.  
  
- **데이터 원본 구성 마법사**를 사용하여 형식화된 데이터 세트를 만듭니다.  
  
- 생성 된 구분 [Tableadapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364) 및 데이터 집합 코드를 별도 프로젝트로 합니다.  
  
- 데이터 액세스 계층으로 호출할 WCF(Windows Communication Foundation) 서비스를 만듭니다.  
  
- 데이터 액세스 계층에서 데이터를 검색하기 위한 함수를 서비스에서 만듭니다.  
  
- 표시 계층으로 사용할 Windows Forms 응용 프로그램을 만듭니다.  
  
- 데이터 소스에 바인딩되는 Windows Forms 컨트롤을 만듭니다.  
  
- 데이터 테이블을 채우는 코드를 작성합니다.  
  
  ![비디오 링크](../data-tools/media/playvideo.gif "PlayVideo") 이 항목의 비디오 버전을 참조 하세요. [Video How to: N 계층 데이터 응용 프로그램을 만드는](http://go.microsoft.com/fwlink/?LinkId=115188)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.
  
## <a name="creating-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>N 계층 솔루션 및 데이터 집합을 저장할 클래스 라이브러리(DataEntityTier) 만들기  
 이 연습의 첫 단계에서는 솔루션과 클래스 라이브러리 프로젝트 두 개를 만듭니다. 첫 번째 클래스 라이브러리에는 데이터 집합, 즉 응용 프로그램 데이터를 저장할 DataTables 및 생성되는 형식화된 DataSet 클래스가 포함됩니다. 이 프로젝트는 응용 프로그램의 데이터 엔터티 계층으로 사용되며 대개 중간 계층에 배치됩니다. 데이터 집합 디자이너 초기 데이터 집합을 만들고 자동으로 코드를 두 클래스 라이브러리로 분리 됩니다.  
  
> [!NOTE]
>  **확인**을 클릭하기 전에 프로젝트와 솔루션의 이름을 올바르게 지정해야 합니다. 그러면 이 연습을 보다 쉽게 완료할 수 있습니다.  
  
#### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>N 계층 솔루션 및 DataEntityTier 클래스 라이브러리를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
    > [!NOTE]
    >  합니다 **데이터 집합 디자이너** 에서 지원 됩니다 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 및 C# 프로젝트입니다. 이러한 언어 중 하나로 새 프로젝트를 만듭니다  
  
2.  에 **새 프로젝트** 대화 상자의 합니다 **프로젝트 형식** 창 클릭 **Windows**합니다.  
  
3.  클릭 합니다 **클래스 라이브러리** 템플릿.  
  
4.  프로젝트 이름을 **DataEntityTier**로 지정합니다.  
  
5.  솔루션의 이름을 **NTierWalkthrough**합니다.  
  
6.  **확인**을 클릭합니다.  
  
     DataEntityTier 프로젝트가 포함된 NTierWalkthrough 솔루션이 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## <a name="creating-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>TableAdapters를 포함할 클래스 라이브러리(DataAccessTier) 만들기  
 DataEntityTier 프로젝트를 만든 후 다음 단계에서는 다른 클래스 라이브러리 프로젝트를 만듭니다. 이 프로젝트는 생성 된 보유할 `TableAdapter`s 라고 합니다 *데이터 액세스 계층* 응용 프로그램의 합니다. 데이터 액세스 계층은 데이터베이스에 연결하는 데 필요한 정보를 포함하며 대개 중간 계층에 배치됩니다.  
  
#### <a name="to-create-the-new-class-library-for-the-tableadapters"></a>TableAdapters용 새 클래스 라이브러리를 만들려면  
  
1.  **파일** 메뉴에서 NTierWalkthrough 솔루션에 새 프로젝트를 추가 합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 합니다 **템플릿** 창 클릭 **클래스 라이브러리**합니다.  
  
3.  프로젝트 이름을 **DataAccessTier** 누릅니다 **확인**합니다.  
  
     DataAccessTier 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.  
  
## <a name="creating-the-dataset"></a>데이터 집합 만들기  
 다음 단계에서는 형식화된 데이터 집합을 만듭니다. 단일 프로젝트에서 DataTables 클래스를 비롯한 데이터 집합 클래스와 `TableAdapter` 클래스를 모두 사용하여 형식화된 데이터 집합을 만듭니다. 모든 클래스는 단일 파일로 생성됩니다. 데이터 집합과 `TableAdapter`를 각기 다른 프로젝트로 분리할 때는 데이터 집합 클래스가 다른 프로젝트로 이동되며 `TableAdapter` 클래스는 원래 프로젝트에 남습니다. 그러므로 최종적으로 `TableAdapter`를 포함할 프로젝트(DataAccessTier 프로젝트)에 데이터 집합을 만듭니다. 사용 하 여 데이터 집합을 만들려는 합니다 **데이터 소스 구성 마법사**합니다.  
  
> [!NOTE]
> 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.
  
#### <a name="to-create-the-dataset"></a>데이터 집합을 만들려면  
  
1.  DataAccessTier를 클릭 **솔루션 탐색기**합니다.  
  
2.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
3.  에 **데이터 원본** 창 클릭 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
4.  에 **데이터 소스 형식 선택** 페이지에서 클릭 **데이터베이스** 클릭 하 고 **다음**합니다.  
  
5.  **데이터 연결 선택** 페이지에서 다음 작업 중 하나를 수행합니다.  
  
     Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 클릭합니다.  
  
     또는  
  
     클릭 **새 연결** 열려는 합니다 **연결 추가** 대화 상자.  
  
6.  데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.  
  
    > [!NOTE]
    >  SQL Server에 연결하는 대신 로컬 데이터베이스 파일을 선택한 경우 프로젝트에 파일을 추가할지를 묻는 메시지가 표시될 수 있습니다. 클릭 **예** 데이터베이스 파일을 프로젝트에 추가 합니다.  
  
7.  클릭 **다음** 에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지입니다.  
  
8.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
9. 에 대 한 확인란을 클릭 합니다 **고객** 및 **주문** 테이블과 클릭 **마침**합니다.  
  
     NorthwindDataSet이 DataAccessTier 프로젝트에 추가되고 **데이터 원본** 창에 표시됩니다.  
  
## <a name="separating-the-tableadapters-from-the-dataset"></a>데이터 집합에서 TableAdapters 분리  
 데이터 집합을 만든 후에는 생성된 데이터 집합 클래스를 TableAdapters에서 분리합니다. 이렇게 하려면 **데이터 세트 프로젝트** 속성을 분리된 데이터 세트 클래스를 저장할 프로젝트의 이름으로 설정합니다.  
  
#### <a name="to-separate-the-tableadapters-from-the-dataset"></a>데이터 집합에서 TableAdapters를 분리하려면  
  
1. **솔루션 탐색기**에서 **NorthwindDataSet.xsd**를 두 번 클릭하여 **데이터 세트 디자이너**에서 데이터 세트를 엽니다.  
  
2. 디자이너의 빈 영역을 클릭합니다.  
  
3. **속성** 창에서 **데이터 세트 프로젝트** 노드를 찾습니다.  
  
4. 에 **데이터 집합 프로젝트** 목록에서 클릭 **DataEntityTier**합니다.  
  
5. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
   데이터 집합 및 TableAdapters가 두 클래스 라이브러리 프로젝트로 분리됩니다. 원래 전체 데이터 집합(DataAccessTier)이 포함되었던 프로젝트에 이제는 TableAdapters만이 포함됩니다. 에 지정 된 프로젝트를 **데이터 집합 프로젝트** 형식화 된 데이터 집합을 포함 하는 속성 (DataEntityTier): 집합인 NorthwindDataSet.Dataset.Designer.vb 또는 NorthwindDataSet.Dataset.Designer.cs입니다.  
  
> [!NOTE]
>  **데이터 세트 프로젝트** 속성을 설정하여 데이터 세트와 TableAdapters를 분리할 때는 프로젝트의 기존 부분 데이터 세트 클래스가 자동으로 이동되지 않습니다. 따라서 데이터 집합 프로젝트로 기존 데이터 집합 부분 클래스를 수동으로 이동해야 합니다.  
  
## <a name="creating-a-new-service-application"></a>새 서비스 응용 프로그램 만들기  
 이 연습에서는 WCF 서비스를 사용하여 데이터 액세스 계층에 액세스하는 방법을 설명하므로 새 WCF 서비스 응용 프로그램을 만듭니다.  
  
#### <a name="to-create-a-new-wcf-service-application"></a>새 WCF 서비스 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 NTierWalkthrough 솔루션에 새 프로젝트를 추가 합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 합니다 **프로젝트 형식** 창 클릭 **WCF**합니다. 에 **템플릿을** 창 클릭 **WCF 서비스 라이브러리**합니다.  
  
3.  프로젝트 이름을 **DataService** 누릅니다 **확인**합니다.  
  
     DataService 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.  
  
## <a name="creating-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>데이터 액세스 계층에서 Customers 및 Orders 데이터를 반환하는 메서드 만들기  
 데이터 액세스 계층의 두 메서드를 호출 해야 하는 데이터 서비스: GetCustomers 및 GetOrders 합니다. 이러한 메서드는 Northwind Customers 및 Orders 테이블을 반환합니다. DataAccessTier 프로젝트에서 GetCustomers 및 GetOrders 메서드를 만듭니다.  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>데이터 액세스 계층에서 Customers 테이블을 반환하는 메서드를 만들려면  
  
1.  **솔루션 탐색기**, 데이터 집합 디자이너에서 데이터 집합을 열려면 NorthwindDataset.xsd를 두 번 클릭 합니다.  
  
2.  CustomersTableAdapter를 마우스 오른쪽 단추로 클릭 하 고 클릭 **쿼리 추가** Tableadapter를 편집 합니다.  
  
3.  **명령 유형을 선택하세요.** 페이지에서 기본값인 **SQL 문 사용**을 그대로 유지하고 **다음**을 클릭합니다.  
  
4.  **쿼리 형식 선택** 페이지에서 기본값인 **행을 반환하는 SELECT**를 그대로 유지하고 **다음**을 클릭합니다.  
  
5.  **SQL SELECT 문을 지정하십시오.** 페이지에서 기본 쿼리를 그대로 유지하고 **다음**을 클릭합니다.  
  
6.  **생성할 메서드 선택** 페이지에서 **DataTable 반환** 섹션의 **메서드 이름**에 **GetCustomers**를 입력합니다.  
  
7.  **마침**을 클릭합니다.  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>데이터 액세스 계층에서 Orders 테이블을 반환하는 메서드를 만들려면  
  
1.  OrdersTableAdapter를 마우스 오른쪽 단추로 클릭 하 고 클릭 **쿼리 추가**합니다.  
  
2.  **명령 유형을 선택하세요.** 페이지에서 기본값인 **SQL 문 사용**을 그대로 유지하고 **다음**을 클릭합니다.  
  
3.  **쿼리 형식 선택** 페이지에서 기본값인 **행을 반환하는 SELECT**를 그대로 유지하고 **다음**을 클릭합니다.  
  
4.  **SQL SELECT 문을 지정하십시오.** 페이지에서 기본 쿼리를 그대로 유지하고 **다음**을 클릭합니다.  
  
5.  **생성할 메서드 선택** 페이지에서 **DataTable 반환** 섹션의 **메서드 이름**에 **GetOrders**를 입력합니다.  
  
6.  **마침**을 클릭합니다.  
  
7.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
## <a name="adding-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>데이터 엔터티 및 데이터 액세스 계층에 대한 참조를 데이터 서비스에 추가  
 데이터 서비스에는 데이터 집합 및 TableAdapters의 정보가 필요하므로 DataEntityTier 및 DataAccessTier 프로젝트에 대한 참조를 추가합니다.  
  
#### <a name="to-add-references-to-the-data-service"></a>데이터 서비스에 참조를 추가하려면  
  
1.  DataService를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 누릅니다 **참조 추가**합니다.  
  
2.  **참조 추가** 대화 상자에서 **프로젝트** 탭을 클릭합니다.  
  
3.  **DataAccessTier** 및 **DataEntityTier** 프로젝트를 모두 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
## <a name="adding-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>데이터 액세스 계층에서 GetCustomers 및 GetOrders 메서드를 호출하는 함수를 서비스에 추가  
 이제 데이터 액세스 계층에 데이터를 반환하는 메서드가 포함되었으므로 데이터 서비스에 데이터 액세스 계층의 메서드를 호출하는 메서드를 만듭니다.  
  
> [!NOTE]
>  C# 프로젝트의 경우 다음 코드가 컴파일하도록 할 `System.Data.DataSetExtensions` 어셈블리에 대한 참조를 추가해야 합니다.  
  
#### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>데이터 서비스에서 GetCustomers 및 GetOrders 함수를 만들려면  
  
1.  에 **DataService** 프로젝트에서 IService1.vb 또는 IService1.cs를 두 번 클릭 합니다.  
  
2.  **여기에 서비스 작업을 추가합니다.** 주석 아래에 다음 코드를 추가합니다.  
  
    ```vb  
    <OperationContract()> _  
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable  
  
    <OperationContract()> _  
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable  
    ```  
  
    ```csharp  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();  
  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();  
  
    ```  
  
3.  DataService 프로젝트에서 Service1.vb 또는 Service1.cs를 두 번 클릭합니다.  
  
4.  Service1 클래스에 다음 코드를 추가합니다.  
  
    ```vb  
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers  
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
        Return CustomersTableAdapter1.GetCustomers()  
    End Function  
  
    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders  
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
        Return OrdersTableAdapter1.GetOrders()  
    End Function  
    ```  
  
    ```csharp  
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
             CustomersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();  
        return CustomersTableAdapter1.GetCustomers();  
  
    }  
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
             OrdersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();  
        return OrdersTableAdapter1.GetOrders();  
  
    }  
    ```  
  
5.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
## <a name="creating-a-presentation-tier-to-display-data-from-the-data-service"></a>데이터 서비스의 데이터를 표시할 표시 계층 만들기  
 이제 데이터 액세스 계층으로 호출할 메서드가 포함된 데이터 서비스가 솔루션에 포함되어 있으므로 데이터 서비스로 호출하여 사용자에게 데이터를 표시할 또 다른 프로젝트를 만듭니다. 이 연습에서는 N 계층 응용 프로그램의 표시 계층인 Windows Forms 응용 프로그램을 만듭니다.  
  
#### <a name="to-create-the-presentation-tier-project"></a>표시 계층 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 NTierWalkthrough 솔루션에 새 프로젝트를 추가 합니다.  
  
2.  에 **새 프로젝트** 대화 상자의 합니다 **프로젝트 형식** 창 클릭 **Windows**합니다. **템플릿** 창에서 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  프로젝트 이름을 **PresentationTier**로 지정하고 **확인**을 클릭합니다.  
  
4.  PresentationTier 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.  
  
## <a name="setting-the-presentationtier-project-as-the-startup-project"></a>PresentationTier 프로젝트를 시작 프로젝트로 설정  
 표시 계층은 데이터를 표시하고 데이터와 상호 작용하는 데 사용되는 실제 클라이언트 응용 프로그램이므로 PresentationTier 프로젝트를 시작 프로젝트로 설정해야 합니다.  
  
#### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>새 표시 계층 프로젝트를 시작 프로젝트로 설정하려면  
  
-   **솔루션 탐색기**에서 **PresentationTier**를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 클릭합니다.  
  
## <a name="adding-references-to-the-presentation-tier"></a>표시 계층에 대한 참조 추가  
 클라이언트 응용 프로그램 PresentationTier가 서비스의 메서드에 액세스하려면 데이터 서비스에 대한 서비스 참조가 필요합니다. WCF 서비스를 통한 형식 공유를 사용하도록 설정하려면 데이터 집합에 대한 참조도 필요합니다. 데이터 서비스를 통해 형식 공유를 사용하도록 설정할 때까지는 부분 데이터 집합 클래스에 추가한 코드를 표시 계층에서 사용할 수 없습니다. 일반적으로는 유효성 검사 등의 코드를 데이터 테이블의 행 및 열 변경 이벤트에 추가하므로 클라이언트에서 이 코드에 액세스할 가능성이 높습니다.  
  
#### <a name="to-add-a-reference-to-the-presentation-tier"></a>표시 계층에 대한 참조를 추가하려면  
  
1.  **솔루션 탐색기**PresentationTier를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다.  
  
2.  에 **참조 추가** 대화 상자에서 클릭 합니다 **프로젝트** 탭 합니다.  
  
3.  선택 **DataEntityTier** 누릅니다 **확인**합니다.  
  
#### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>표시 계층에 대한 서비스 참조를 추가하려면  
  
1.  **솔루션 탐색기**PresentationTier를 마우스 오른쪽 단추로 클릭 하 고 클릭 **서비스 참조 추가**합니다.  
  
2.  **서비스 참조 추가** 대화 상자에서 **검색**을 클릭합니다.  
  
3.  선택 **Service1** 누릅니다 **확인**합니다.  
  
    > [!NOTE]
    >  현재 컴퓨터에 서비스가 여러 개이면 이 연습 앞부분에서 만든 서비스(GetCustomers 및 GetOrders 메서드가 포함된 서비스)를 선택합니다.  
  
## <a name="adding-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>데이터 서비스에서 반환하는 데이터를 표시할 DataGridView를 폼에 추가  
 데이터 서비스에 대한 서비스 참조를 추가하고 나면 **데이터 소스** 창에 서비스에 의해 반환되는 데이터가 자동으로 채워집니다.  
  
#### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>데이터 바인딩된 DataGridView 두 개를 폼에 추가하려면  
  
1.  **솔루션 탐색기**, PresentationTier 프로젝트를 선택 합니다.  
  
2.  **데이터 원본** 창에서 **NorthwindDataSet**를 확장하고 **Customers** 노드를 찾습니다.  
  
3.  **Customers** 노드를 Form1로 끌어 옵니다.  
  
4.  **데이터 원본** 창에서 **Customers** 노드를 확장하고 관련 **Orders** 노드(**Customers** 노드에 중첩된 **Orders** 노드)를 찾습니다.  
  
5.  관련 **Orders** 노드를 Form1로 끌어 옵니다.  
  
6.  폼의 빈 영역을 두 번 클릭하여 `Form1_Load` 이벤트 처리기를 만듭니다.  
  
7.  다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.  
  
    ```vb  
    Dim DataSvc As New ServiceReference1.Service1Client  
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)  
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)  
    ```  
  
    ```csharp  
    ServiceReference1.Service1Client DataSvc =   
        new ServiceReference1.Service1Client();  
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());  
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());  
  
    ```  
  
## <a name="increasing-the-maximum-message-size-allowed-by-the-service"></a>서비스에서 허용하는 최대 메시지 크기 늘리기  
 서비스는 Customers 및 Orders 테이블에서 데이터를 반환하므로 maxReceivedMessageSize의 기본값은 데이터를 저장하는 데 충분하지 않기 때문에 값을 늘려야 합니다. 이 연습에서는 값을 6553600으로 변경합니다. 클라이언트에서 값을 변경하면 서비스 참조가 자동으로 업데이트됩니다.  
  
> [!NOTE]
>  기본값이 작은 이유는 DoS(서비스 거부) 공격에 대한 노출을 제한하기 위해서입니다. 자세한 내용은 <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>을 참조하십시오.  
  
#### <a name="to-increase-the-maxreceivedmessagesize-value"></a>maxReceivedMessageSize 값을 늘리려면  
  
1.  **솔루션 탐색기**, PresentationTier 프로젝트의 app.config 파일을 두 번 클릭 합니다.  
  
2.  **maxReceivedMessage** 크기 특성을 찾아 값을 `6553600`으로 변경합니다.  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 애플리케이션을 실행합니다. 데이터가 데이터 서비스에서 검색되어 폼에 표시됩니다.  
  
#### <a name="to-test-the-application"></a>애플리케이션을 테스트하려면  
  
1.  F5 키를 누릅니다.  
  
2.  Customers 및 Orders 테이블의 데이터가 데이터 서비스에서 검색되어 폼에 표시됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 Windows 기반 응용 프로그램에서 관련 데이터를 저장한 후 몇 단계를 더 수행해야 할 수도 있습니다. 예를 들어 이 응용 프로그램을 다음과 같이 개선할 수 있습니다.  
  
-   데이터 집합에 유효성 검사 기능을 추가합니다. 내용은 [연습: N 계층 데이터 응용 프로그램에 유효성 검사 추가](http://msdn.microsoft.com/library/b35d072c-31f0-49ba-a225-69177592c265)합니다.  
  
-   데이터를 데이터베이스로 다시 업데이트하기 위한 추가 메서드를 서비스에 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [N 계층 응용 프로그램에서 데이터 집합 작업](../data-tools/work-with-datasets-in-n-tier-applications.md)   
 [계층적 업데이트](../data-tools/hierarchical-update.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)
