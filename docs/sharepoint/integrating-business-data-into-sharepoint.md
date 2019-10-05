---
title: SharePoint에 비즈니스 데이터 통합 | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], business data
- BDC [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], business data
- Business Data Connectivity service [SharePoint development in Visual Studio], aggregating data
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], data
- BDC [SharePoint development in Visual Studio], data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fbbdba27b5ccc52e64575aad018af4ca20cf2e14
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63008801"
---
# <a name="integrate-business-data-into-sharepoint"></a>SharePoint 비즈니스 데이터 통합
  SharePoint에 비즈니스 데이터를 통합할 수 있습니다. 비즈니스 데이터와 같은 백 엔드 서버 응용 프로그램에서 가져올 수 있습니다 [!INCLUDE[TLA#tla_sqlsvr](../sharepoint/includes/tlasharptla-sqlsvr-md.md)], Siebel 및 SAP 또는 웹 서비스입니다. 사용자 수 보기, 추가, 업데이트 또는 외부 목록 또는 SharePoint에 비즈니스 데이터 웹 파트를 사용 하 여 비즈니스 데이터를 삭제 합니다.  이 데이터를 오프 라인 Microsoft Outlook과 같은 Microsoft Office 응용 프로그램에서 액세스할 수도 있습니다. 자세한 내용은 [여기서 수 외부 데이터를 표시할](http://go.microsoft.com/fwlink/?LinkId=169295)합니다.

 데이터를 SharePoint에 통합 하려면 데이터 연결 (BDC (비즈니스) 서비스에 대 한 모델을 만듭니다. BDC 서비스는 비즈니스 응용 프로그램의 데이터에 대 한 정보를 저장 하는 SharePoint에서 응용 프로그램. 자세한 내용은 [비즈니스 데이터 연결 (BDC) 서비스](http://go.microsoft.com/fwlink/?LinkID=169276)합니다.

## <a name="models-in-visual-studio"></a>Visual Studio에서 모델
 Visual Studio에서 모델을 사용 하 여 검색 하 고 백 엔드 데이터 원본에서 데이터를 업데이트 하는 사용자 지정 코드를 작성할 수 있습니다. 여러 데이터 원본에서 데이터를 집계 수도 있습니다. 데이터를 포함 하는 고객의 목록을 표시할 수는 예를 들어, 한 [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)] 데이터베이스 및 웹 서비스입니다.

 이미 SharePoint에 배포 된 모델을 가져올 수도 있습니다. 모델을 가져온 후에 사용자 지정 코드를 추가 하거나 방금 Visual Studio를 사용 하 여 패키지를 SharePoint 서버 팜에 여러 모델을 배포할 수 있습니다. 자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.

## <a name="design-a-model-in-visual-studio"></a>Visual Studio에서 모델 디자인
 디자이너 및 몇 가지 도구 창을 사용 하 여 모델을 디자인할 수 있습니다. 모델을 디자인할 때 Visual Studio 모델 XML을 생성 합니다. 자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.

 모델은 엔터티 및 메서드를 포함 합니다.

### <a name="entities"></a>엔터티
 엔터티 필드의 컬렉션을 설명 합니다. 예를 들어, 엔터티는 데이터베이스의 테이블을 나타낼 수 있습니다. 엔터티는 SharePoint에서 외부 콘텐츠 형식으로 표시 됩니다. 외부 콘텐츠 형식에 대 한 자세한 내용은 참조 하세요. [외부 콘텐츠 형식 이란?](http://go.microsoft.com/fwlink/?LinkId=169293)

### <a name="methods"></a>메서드
 메서드를 사용 하면 엔터티의 필드에 작업을 수행 하려면 외부 콘텐츠 형식의 소비자가 있습니다. Updater 메서드 수 주소를 변경 하려면 사용자를 사용 하도록 설정 하 고 고객의 생년월일 하는 예를 들어, 여기서 `Address` 하 고 `BirthDate` 필드는는 `Customer` 엔터티.

 Visual Studio 모델의 각 엔터티에 대 한 서비스 코드 파일을 생성합니다. 모델 메서드를 추가 하면 Visual Studio 서비스 코드 파일에서 해당 메서드를 생성 합니다. 적절 한 작업을 수행 하려면 각 메서드에 코드를 추가 합니다. 예를 들어 모델에 Creator 메서드를 추가 하는 경우 Visual Studio 서비스 코드 파일에서 Creator 메서드를 생성 합니다. 이 메서드는 BDC 서비스에서 사용자가 클릭 하 여 **새 항목** 모델을 기반으로 하는 목록에서 단추입니다. 따라서 데이터 원본에 새 데이터를 추가 하는 작성자 메서드에 코드를 추가 합니다. 자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)|어떻게 새 모델을 만들거나 가져오는 SharePoint에서 내보내기 하는 모델을 보여 줍니다.|
|[비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)|Visual Studio 디자인 도구를 사용 하 여 모델의 요소를 디자인 하는 방법에 설명 합니다.|
|[SharePoint Designer를 사용 하 여 vs 하는 경우. BCS를 사용 하 여 visual Studio를 만들 때 솔루션](http://go.microsoft.com/fwlink/?LinkID=183448)|Visual Studio를 사용 하거나 SharePoint Designer를 사용 하 여 BDC에 대 한 모델을 만들 것인지를 결정 하도록 도와줍니다.|
