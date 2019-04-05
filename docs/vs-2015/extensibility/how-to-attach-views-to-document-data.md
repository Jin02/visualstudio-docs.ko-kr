---
title: '방법: 문서 데이터에 보기 연결 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - attach views to document data
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 671a243f65c68660c98c3730ca90568882a824d6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58970966"
---
# <a name="how-to-attach-views-to-document-data"></a>방법: 문서 데이터에 보기 연결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

새 문서 보기에 있는 경우에 기존 문서 데이터 개체에 연결할 수 있습니다.  
  
### <a name="to-determine-if-you-can-attach-a-view-to-an-existing-document-data-object"></a>기존 문서 데이터 개체에 뷰를 연결할 수 경우를 확인 하려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>를 구현해야 합니다.  
  
2.  구현의 `IVsEditorFactory::CreateEditorInstance`, 호출 `QueryInterface` IDE를 호출 하는 경우 기존 문서 데이터 개체에 `CreateEditorInstance` 구현.  
  
     호출 `QueryInterface` 에 설명 된 기존 문서 데이터 개체를 검토할 수 있습니다는 `punkDocDataExisting` 매개 변수입니다.  
  
     그러나 다른 설명이 없는 4 단계에 설명 된 대로 정확 하 게 인터페이스를 쿼리는 문서를 열 편집기를 따라 달라 집니다.  
  
3.  기존 문서 데이터 개체에 대해 적절 한 인터페이스를 찾을 수 없는, 문서 데이터 개체 편집기와 호환 되는지 나타내는 편집기에 오류 코드를 반환 합니다.  
  
     IDE의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, 메시지 상자에 알리고 있습니다 해당 문서의 다른 편집기에 열려 있는 닫을 것인지 묻는 합니다.  
  
4.  이 문서를 닫으면 Visual Studio를 한 번에 대 한 편집기 팩터리의 호출 합니다. 이 호출에는 `DocDataExisting` 매개 변수는 null입니다. 편집기 팩터리 구현을 사용자 고유의 편집기에서 문서 데이터 개체를 열 수 있습니다.  
  
    > [!NOTE]
    >  기존 문서 데이터 개체를 작업할 수 있는지 여부를 결정할 사용할 수도 있습니다 인터페이스 구현에 대 한 개인 지식이 실제에 대 한 포인터를 캐스팅 하 여 [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] 개인 구현의 클래스입니다. 예를 들어 모든 표준 편집기 구현할 `IVsPersistFileFormat`에서 상속 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>합니다. 따라서 호출할 수 있습니다 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, 기존 문서 데이터 개체의 클래스 ID와 일치에 구현 클래스 ID를 문서 데이터 개체를 사용 하 여 작업할 수 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Visual Studio의 사용자 구현을 호출 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 전달 다시에 대 한 포인터를 기존 문서 데이터 개체에는 `punkDocDataExisting` 있으면 매개 변수입니다. 반환 하는 문서 데이터 개체를 검사 `punkDocDataExisting` 문서 데이터 개체를이 항목의 절차의 4 단계에서 참고에 설명 된 대로 편집기에 대 한 적절 한 경우를 확인 합니다. 적절 한 경우에 설명 된 대로 편집기 팩터리의 데이터에 대 한 두 번째 보기를 제공 해야 [Supporting Multiple Document Views](../extensibility/supporting-multiple-document-views.md)합니다. 그렇지 않은 경우 다음 적절 한 오류 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [여러 문서 보기 지원](../extensibility/supporting-multiple-document-views.md)   
 [사용자 지정 편집기의 문서 데이터 및 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)
