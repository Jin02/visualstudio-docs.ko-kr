---
title: '방법: 주 interop 어셈블리를 통해 대상 Office 응용 프로그램'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 074b01e78fd398a43548febf81ba03b61a8646b4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079638"
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>방법: 주 interop 어셈블리를 통해 대상 Office 응용 프로그램
  새 Office 프로젝트를 만들 때 Visual Studio는 프로젝트를 빌드하는 데 필요한 Microsoft Office PIA(주 interop 어셈블리)에 대한 참조를 자동으로 추가합니다. 다음과 같은 시나리오에서는 다른 PIA에 대한 참조를 추가해야 합니다.

- 프로젝트에서 다른 Microsoft Office 응용 프로그램의 기능을 사용하려고 합니다. 예를 들어 Microsoft Office Word용 프로젝트에서 Microsoft Office Excel의 기능을 사용할 수 있습니다.

- Microsoft Office Access와 같이 Visual Studio에 전용 프로젝트가 없는 Microsoft Office 응용 프로그램을 자동화하려고 합니다.

  [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>주 interop 어셈블리에 대한 참조를 추가하려면

1. 프로젝트 이름을 선택 하 고 Office 프로젝트를 엽니다 **솔루션 탐색기**합니다.

2. **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.

3. 에 **프레임 워크** 탭에서 원하는 PIA를 선택 합니다 합니다 **구성 요소 이름** 목록입니다. 사용 가능한 Microsoft Office 주 interop 어셈블리에 대 한 자세한 내용은 참조 하세요. [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)합니다.

     경우 프로젝트 대상을 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상 합니다 **Interop 형식 포함** 어셈블리 참조 속성 **True** 기본적으로 합니다. 이 설정을 사용하면 최종 사용자 컴퓨터에서 솔루션에 PIA가 필요하지 않습니다. 자세한 내용은 [디자인 Office 솔루션을 만들고](../vsto/designing-and-creating-office-solutions.md)합니다.

    > [!NOTE]
    >  Office 프로젝트에서 언제 든 지 추가할 Office Pia에 대 한 참조를 사용 하 여는 **.NET** 탭을 **참조 추가** 대화 상자 대신 **COM** 탭. 자세한 내용은 [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)합니다.

4. **확인**을 클릭합니다.

     에 어셈블리 이름을 표시 합니다 **참조** 의 폴더 **솔루션 탐색기**합니다.

## <a name="see-also"></a>참고자료
- [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)
- [Office 솔루션에서 코드를 작성 합니다.](../vsto/writing-code-in-office-solutions.md)
- [Office 솔루션 개발](../vsto/developing-office-solutions.md)
- [방법: Office 주 interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md)
