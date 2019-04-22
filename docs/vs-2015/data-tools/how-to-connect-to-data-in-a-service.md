---
title: '방법: 데이터 서비스에 연결 | Microsoft Docs'
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
- data [Visual Studio], connecting to Web services
- data sources, creating from Web services
- data [Visual Studio], reading from Web services
- reading data, from Web services
- Web services, reading data
- Web services, as data sources
- Web services, connecting
ms.assetid: a6b54353-05fe-4e5c-8631-90231fc95504
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a13d0c8ff1383e27f9401f6549c422a8fef96e99
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59650046"
---
# <a name="how-to-connect-to-data-in-a-service"></a>방법: 서비스의 데이터에 연결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

응용 프로그램을 실행 하 여 서비스에서 반환 되는 데이터 연결 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f) 를 선택 하 고 **서비스** 에 **데이터소스형식선택**페이지.  
  
 마법사를 완료 하면 서비스 참조를 프로젝트에 추가 되 고에서 즉시 사용할 수는 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)합니다.  
  
> [!NOTE]
>  **데이터 원본** 창에 표시되는 항목은 서비스에서 반환하는 정보에 따라 달라집니다. **데이터 원본 구성 마법사**에서 바인딩 가능한 개체를 만들기에 충분한 정보를 제공하지 않는 서비스도 있습니다. 예를 들어 서비스가 형식화 되지 않은 데이터 집합을 반환 하는 경우 다음에 아무런 항목도 표시 합니다 **데이터 소스 창** 마법사가 완료 될 때입니다. 형식화 되지 않은 데이터 집합 스키마를 제공 하지 마법사가 데이터 소스를 만드는 데 충분 한 정보를 갖고 있지 않아 때문입니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-connect-your-application-to-a-service"></a>응용 프로그램 서비스에 연결 하려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
2.  선택 **서비스** 에 **데이터 소스 형식 선택** 페이지를 선택한 다음 클릭 **다음**합니다.  
  
3.  를 사용 하거나 클릭 하려는 서비스의 주소를 입력 **Discover** 현재 솔루션에서 서비스를 찾아 클릭 **이동**합니다.  
  
4.  필요에 따라 새 **Namespace** 기본값 대신 형식화 될 수 있습니다.  
  
    > [!NOTE]
    >  클릭 **고급** 열려는 합니다 [서비스 참조 구성 대화 상자](../data-tools/configure-service-reference-dialog-box.md)합니다.  
  
5.  클릭 **확인** 프로젝트에 서비스 참조를 추가 합니다.  
  
6.  **마침**을 클릭합니다.  
  
     데이터 원본이 **데이터 원본** 창에 추가됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
#### <a name="to-add-functionality-to-your-application"></a>응용 프로그램에 기능을 추가하려면  
  
-   항목을 선택 합니다 **데이터 원본** 창 바인딩된 컨트롤을 만드는 폼으로 끌어 옵니다. 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)   
 [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
