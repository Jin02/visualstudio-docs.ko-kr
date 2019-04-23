---
title: TableAdapter DBDirect 메서드 데이터 저장 | Microsoft Docs
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
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7cba6f91dd6dc0bb826531a312dc6ca5c94b21a5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60114758"
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>TableAdapter DBDirect 메서드를 사용하여 데이터 저장
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 TableAdapter의 DBDirect 메서드를 사용 하 여 데이터베이스에 대해 직접 SQL 문을 실행 하는 것에 대 한 자세한 지침을 제공 합니다. TableAdapter의 DBDirect 메서드는 데이터베이스 업데이트에 대한 상세 제어 수준을 제공합니다. 개별을 호출 하 여 특정 SQL 문과 저장된 프로시저 실행에 사용할 수 있습니다 `Insert`, `Update`, 및 `Delete` 응용 프로그램에서 필요에 따라 메서드 (오버 로드 된 달리 `Update` 업데이트를 수행 하는 메서드 INSERT 및 DELETE 문을 모두 한 번의 호출).  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
- 새 **Windows 응용 프로그램**합니다.  
  
- 만들기 및 사용 하 여 데이터 집합을 구성 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다.  
  
- **데이터 원본** 창에서 항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택합니다. 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
- **데이터 원본** 창에서 폼으로 항목을 끌어 데이터 바인딩된 폼을 만듭니다.  
  
- 직접 데이터베이스에 액세스 하 고 삽입, 업데이트 및 삭제를 수행 하는 메서드 추가...  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
- Northwind 샘플 데이터베이스에 대한 액세스.
  
## <a name="create-a-windows-application"></a>Windows 응용 프로그램 만들기  
 첫 번째 단계를 만드는 것을 **Windows 응용 프로그램**합니다.  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴에서 새 **프로젝트**합니다.  
  
2. 프로젝트 이름을 **TableAdapterDbDirectMethodsWalkthrough**합니다.  
  
3. 선택 **Windows 응용 프로그램**를 선택한 후 **확인**합니다. 자세한 내용은 [클라이언트 응용 프로그램](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
     **TableAdapterDbDirectMethodsWalkthrough** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## <a name="create-a-data-source-from-your-database"></a>데이터베이스에서 데이터 원본 만들기  
 이 단계에서는 **데이터 원본 구성 마법사**를 사용하여 Northwind 샘플 데이터베이스의 `Region` 테이블을 기반으로 하는 데이터 원본을 만듭니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1. 에 **데이터** 메뉴에서 **데이터 소스 표시**합니다.  
  
2. **데이터 원본** 창에서 **새 데이터 원본 추가**를 선택하여 **데이터 원본 구성 마법사**를 시작합니다.  
  
3. 에 **데이터 소스 형식 선택** 화면에서 **데이터베이스**를 선택한 후 **다음**합니다.  
  
4. 에 **데이터 연결 선택** 화면에서 다음 중 하나를 수행 합니다.  
  
    - Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    - **새 연결**을 선택하여 **연결 추가/수정** 대화 상자를 시작합니다.  
  
5. 데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 하 여 선택한 옵션을 선택 **다음**합니다.  
  
6. 에 **응용 프로그램 구성 파일에 연결 문자열을 저장** 화면에서 **다음**합니다.  
  
7. 에 **데이터베이스 개체 선택** 화면에서 확장 된 **테이블** 노드.  
  
8. 선택 된 `Region` 테이블을 선택한 후 **완료**합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 `Region` 테이블이 **데이터 원본** 창에 나타납니다.  
  
## <a name="addcontrols-to-the-form-to-display-the-data"></a>데이터를 표시 하려면 폼에 Addcontrols  
 **데이터 원본** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Windows form의 컨트롤에 바인딩된 데이터를 만들려면  
  
- 주를 끌어 **지역** 에서 노드를 **데이터 원본** 창에서 폼입니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), RegionTableAdapter를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>개별 TableAdapter DbDirect 메서드를 호출하는 단추를 추가하려면  
  
1. <xref:System.Windows.Forms.Button> 컨트롤 3개를 **도구 상자**에서 **Form1**의 **RegionDataGridView** 아래로 끌어 옵니다.  
  
2. 각 단추에 대해 다음 **이름** 및 **텍스트** 속성을 설정합니다.  
  
    |이름|텍스트|  
    |----------|----------|  
    |`InsertButton`|**삽입**|  
    |`UpdateButton`|**업데이트**|  
    |`DeleteButton`|**삭제**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>데이터베이스에 새 레코드를 삽입하는 코드를 추가하려면  
  
1. 선택 **InsertButton** click 이벤트에 대 한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2. `InsertButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-csharp[VbRaddataSaving#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#1)]
     [!code-vb[VbRaddataSaving#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#1)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>데이터베이스에서 레코드를 업데이트하는 코드를 추가하려면  
  
1. **UpdateButton**을 두 번 클릭하여 클릭 이벤트에 대한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2. `UpdateButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-csharp[VbRaddataSaving#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#2)]
     [!code-vb[VbRaddataSaving#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#2)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>데이터베이스에서 레코드를 삭제 하는 코드를 추가 하려면  
  
1. 선택 **DeleteButton** click 이벤트에 대 한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2. `DeleteButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-csharp[VbRaddataSaving#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#3)]
     [!code-vb[VbRaddataSaving#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#3)]  
  
## <a name="run-the-application"></a>애플리케이션 실행  
  
#### <a name="to-run-the-application"></a>애플리케이션을 실행하려면  
  
- 선택 **F5** 응용 프로그램을 실행 합니다.  
  
- 선택 된 **삽입** 단추 및 새 레코드를 모눈에 표시 되는지 확인 합니다.  
  
- 선택 된 **업데이트** 단추를 하 고 표에 레코드가 업데이트 되었는지 확인 합니다.  
  
- 선택 된 **삭제** 단추를 클릭 한 레코드의 표에서 삭제 되는지 확인 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 일부의 단계가 있습니다 데이터 바인딩된 폼을 만든 후 수행 하는 것이 좋습니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
- 폼에 검색 기능을 추가합니다. 자세한 내용은 [방법: 매개 변수가 있는 쿼리는 Windows Forms 응용 프로그램 추가](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)합니다.  
  
- **데이터 원본** 창에서 **마법사로 데이터 세트 구성**을 선택하여 추가 테이블을 데이터 세트에 추가합니다. 관련 노드를 폼으로 끌어 관련 데이터를 표시하는 컨트롤을 추가할 수 있습니다. 
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)
