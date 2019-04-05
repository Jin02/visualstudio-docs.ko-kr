---
title: 디자이너에 추가 하려는 개체가 디자이너에서 현재 사용 중인 것 보다 다른 데이터 연결을 사용 하 여 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e9922cb879c9adbf0a6e334aa0c9ebc6cf60585d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985962"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer-is-currently-using"></a>디자이너에 추가하려는 개체가 현재 디자이너가 사용 중인 것과 다른 데이터 연결을 사용합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
디자이너에 추가하려는 개체가 디자이너에서 현재 사용 중인 데이터 연결이 아닌 다른 데이터 연결을 사용합니다. 디자이너에서 사용 중인 연결을 바꾸시겠습니까?  
  
 항목을 추가 하는 경우는 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]), 모든 항목이 하나의 공유 데이터 연결을 사용 합니다. 디자인 화면에는 화면의 모든 개체에 대해 하나의 연결을 사용하는 <xref:System.Data.Linq.DataContext>가 표시됩니다. 디자이너에서 현재 사용하는 데이터 연결과 다른 데이터 연결을 사용하는 디자이너에 개체를 추가하면 이 메시지가 나타납니다. 이 오류를 해결하려면 기존 연결 유지를 선택하세요. 이 항목을 선택하면 선택한 개체가 추가되지 않습니다. 또는 개체 추가를 선택하고 <xref:System.Data.Linq.DataContext> 연결을 새 연결로 다시 설정할 수 있습니다.  
  
> [!NOTE]
>  클릭 하면 **Yes**의 모든 엔터티 클래스가 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 새 연결에 매핑됩니다.  
  
### <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>기존 연결을 선택한 개체에서 사용하는 연결로 대체하려면  
  
-   **예**를 클릭합니다.  
  
     선택한 개체가 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에 추가되고 DataContext.Connection이 새 연결로 설정됩니다.  
  
### <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>기존 연결을 계속 사용하고 선택한 개체 추가를 취소하려면  
  
-   **아니요**를 클릭합니다.  
  
     작업이 취소됩니다.  DataContext.Connection이 기존 연결로 설정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   