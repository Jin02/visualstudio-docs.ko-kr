---
title: 데이터 소스 창에서 끌어올 때 만들 컨트롤을 설정 합니다. | Microsoft Docs
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
- Data Sources Window, select controls
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- data [Visual Studio], Data Sources window
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
caps.latest.revision: 34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 222ecfa56b179379c2d007e8635e7b40d6b1b660
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655378"
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>데이터 소스 창에서 끌어올 때 만들 컨트롤 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**데이터 소스** 창에서 WPF 디자이너나 Windows Forms designer로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다. **데이터 소스** 창의 각 항목에는 디자이너로 끌어올 때 생성 되는 기본 컨트롤이 있습니다. 그러나 다른 컨트롤을 만들도록 선택할 수 있습니다.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>데이터 테이블 또는 개체에 대해 만들 컨트롤 설정
 데이터 **소스** 창에서 데이터 테이블이 나 개체를 나타내는 항목을 끌기 전에 모든 데이터를 하나의 컨트롤로 표시 하거나 개별 컨트롤에 각 열 또는 속성을 표시 하도록 선택할 수 있습니다.

 이 컨텍스트에서 용어 *개체* 는 사용자 지정 비즈니스 개체, 엔터티 (엔터티 데이터 모델) 또는 서비스에서 반환 된 개체를 참조 합니다.

#### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>데이터 테이블이 나 개체에 대해 만들 컨트롤을 설정 하려면

1. WPF 디자이너나 Windows Forms 디자이너가 열려 있는지 확인 합니다.

2. **데이터 소스** 창에서 설정 하려는 데이터 테이블이 나 개체를 나타내는 항목을 선택 합니다.

3. 항목에 대 한 드롭다운 메뉴를 클릭 하 고 메뉴에서 다음 항목 중 하나를 클릭 합니다.

   - 각 데이터 필드를 별도의 컨트롤에 표시 하려면 **세부 정보**를 클릭 합니다. 데이터 항목을 디자이너로 끌어 오면이 작업은 각 컨트롤에 대 한 레이블과 함께 부모 데이터 테이블이 나 개체의 각 열 또는 속성에 대해 서로 다른 데이터 바인딩된 컨트롤을 만듭니다.

   - 모든 데이터를 단일 컨트롤로 표시 하려면 목록에서 WPF 응용 프로그램의 **DataGrid** 또는 **목록** , Windows Forms 응용 프로그램에서 **DataGridView** 와 같은 다른 컨트롤을 선택 합니다.

     사용 가능한 컨트롤 목록은 열려 있는 디자이너, 프로젝트의 대상 .NET Framework 버전 및 **도구 상자**에 데이터 바인딩을 지 원하는 사용자 지정 컨트롤을 추가 했는지 여부에 따라 달라 집니다. 만들려는 컨트롤이 사용 가능한 컨트롤 목록에 있으면 목록에 컨트롤을 추가할 수 있습니다. 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조 하세요.

     데이터 **소스** 창에서 데이터 테이블 또는 개체의 컨트롤 목록에 추가할 수 있는 사용자 지정 Windows Forms 컨트롤을 만드는 방법에 대 한 자세한 내용은 [복합 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)를 참조 하세요.

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>데이터 열 또는 속성에 대해 만들 컨트롤 설정
 열 또는 개체의 속성을 나타내는 항목을 **데이터 소스** 창에서 디자이너로 끌기 전에 컨트롤을 만들 수 있도록 설정할 수 있습니다.

#### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>열 또는 속성에 대해 만들 컨트롤을 설정 하려면

1. WPF 디자이너나 Windows Forms 디자이너가 열려 있는지 확인 합니다.

2. **데이터 원본** 창에서 원하는 테이블 또는 개체를 확장 하 여 해당 열 또는 속성을 표시 합니다.

3. 만들 컨트롤을 설정 하려는 각 열 또는 속성을 선택 합니다.

4. 열 또는 속성에 대 한 드롭다운 메뉴를 클릭 한 다음 항목을 디자이너로 끌 때 만들려는 컨트롤을 선택 합니다.

     사용 가능한 컨트롤 목록은 열려 있는 디자이너, 프로젝트의 대상 .NET Framework 버전 및 **도구 상자**에 추가한 데이터 바인딩을 지 원하는 사용자 지정 컨트롤에 따라 다릅니다. 만들려는 컨트롤이 사용 가능한 컨트롤 목록에 있으면 목록에 컨트롤을 추가할 수 있습니다. 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조 하세요.

     데이터 **소스** 창에서 데이터 열 또는 속성에 대 한 컨트롤 목록에 추가할 수 있는 사용자 지정 컨트롤을 만드는 방법을 알아보려면 [단순 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)를 참조 하세요.

     열 또는 속성에 대 한 컨트롤을 만들지 않으려면 드롭다운 메뉴에서 **없음** 을 선택 합니다. 이 방법은 부모 테이블이 나 개체를 디자이너에 끌어 놓을 수 있지만 특정 열 또는 속성을 포함 하지 않으려는 경우에 유용 합니다.

## <a name="see-also"></a>관련 항목:
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)
