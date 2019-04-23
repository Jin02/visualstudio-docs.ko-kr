---
title: 데이터베이스의 그림에 컨트롤 바인딩
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 4e41cb7bf747a1c083dc1728d7ea26f47ad8fa48
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60106997"
---
# <a name="bind-controls-to-pictures-from-a-database"></a>데이터베이스의 그림에 컨트롤 바인딩

사용할 수는 **데이터 원본** 창 응용 프로그램에서 컨트롤을 데이터베이스에 이미지를 바인딩할 수 있습니다. 예를 들어 이미지를 바인딩할 수 있습니다는 <xref:System.Windows.Controls.Image> WPF 응용 프로그램에서 또는 컨트롤을 <xref:System.Windows.Forms.PictureBox> Windows Forms 응용 프로그램에서 제어 합니다.

데이터베이스의 그림은 일반적으로 바이트 배열로 저장 됩니다. 항목의 **데이터 원본** 바이트 배열이 있으면 입력 제어 저장 되는 창으로 설정 **None** 기본적으로 바이트 배열을 간단한 실행 파일에는 바이트 배열에서 아무 것도 포함 될 수 있으므로 대규모 응용 프로그램입니다. 바이트 배열 항목에 대 한 데이터 바인딩된 컨트롤을 만드는 합니다 **데이터 원본** 이미지를 나타내는 창을 만드는 컨트롤을 선택 해야 합니다.

다음 절차에 있다고 가정 합니다 **데이터 원본** 창 이미지에 바인딩되는 항목으로 채워집니다.

## <a name="to-bind-a-picture-in-a-database-to-a-control"></a>데이터베이스의 그림 컨트롤에 바인딩할

1. 디자인 화면에 컨트롤을 추가 하려면 WPF 디자이너 또는 Windows Forms 디자이너에서 열려 있는지 확인 합니다.

2. 에 **데이터 원본** 창에서 원하는 테이블을 확장 하거나 해당 열 또는 속성을 표시할 개체입니다.

   > [!TIP]
   > 경우는 **데이터 원본** 창이 열려 있지 않으면, 선택 하 여 엽니다 **뷰** > **기타 Windows** > **데이터 원본을**.

3. 열 이나 이미지 데이터를 포함 하는 속성을 선택 하 고 해당 드롭다운 목록 컨트롤 목록에서 다음 컨트롤 중 하나를 선택 합니다.

    - WPF designer가 열려 있으면 선택 **이미지**합니다.

    - Windows Forms 디자이너를 연 경우 선택할 **PictureBox**합니다.

    - 또는 데이터 바인딩을 지원 하 고 이미지를 표시할 수 있는 다른 컨트롤을 선택할 수 있습니다. 사용 하려는 컨트롤의 사용 가능한 컨트롤 목록에 없는 경우 목록에 추가 하 고 선택 수 있습니다. 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)