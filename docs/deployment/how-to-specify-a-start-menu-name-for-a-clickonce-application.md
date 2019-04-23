---
title: '방법: ClickOnce 응용 프로그램에 대 한 시작 메뉴 이름 지정 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4ef1675480182796e1fe8bbe29baa5ed6a9d5f63
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085118"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>방법: ClickOnce 애플리케이션의 시작 메뉴 이름 지정
경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 사용 하 여 온라인 및 오프 라인 설치를 항목에 추가 됩니다 합니다 **시작** 메뉴 및 **프로그램 추가 / 제거** 목록입니다. 기본적으로 표시 이름은 응용 프로그램 어셈블리의 이름과 동일 하지만 설정 하 여 표시 이름을 변경할 수 있습니다 **Product name** 에 **게시 옵션** 대화 상자.

 **제품 이름** 에 표시 됩니다는 *publish.htm* 페이지, 설치 된 오프 라인 응용 프로그램에서 항목의 이름이 됩니다 합니다 **시작** 메뉴에 표시 되는 이름 수도 있습니다 **프로그램 추가 / 제거**합니다.

 **게시자 이름** 에 표시 됩니다는 *publish.htm* 위에서 페이지 **Product name**, 하며 설치 된 오프 라인 응용 프로그램에 대 한 해당 응용 프로그램의 포함 된 폴더의 이름 아이콘에는 **시작** 메뉴.

 시작 메뉴 바로 가기 또는 앱 참조에서 만들어지는 *%appdata%\Microsoft\Windows\Start Menu\Programs\\< 게시자 이름이\>* 합니다. 바로 가기 또는 앱 참조를 제품 이름으로 동일한 이름이 있습니다.

 설정할 수 있습니다는 **제품 이름** 및 **게시자 이름** 속성에는 **게시 옵션** 에서 사용할 수 있는 대화 상자를 **게시** 페이지 **프로젝트 디자이너**합니다.

### <a name="to-specify-a-start-menu-name"></a>시작 메뉴 이름 지정

1. **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **게시** 탭을 클릭합니다.

3. 클릭 합니다 **옵션** 버튼을 클릭 합니다 **게시 옵션** 대화 상자.

4. 클릭 **설명을**합니다.

5. 에 **게시 옵션** 대화 상자에 표시할 이름을 입력 합니다 **Product name**합니다.

6. 게시자 이름을 입력할 수는 필요에 따라 **게시자 이름**합니다.

## <a name="see-also"></a>참고자료
- [ClickOnce 애플리케이션 게시](../deployment/publishing-clickonce-applications.md)
- [방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)