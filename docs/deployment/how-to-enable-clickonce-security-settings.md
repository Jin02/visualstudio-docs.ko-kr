---
title: ClickOnce 보안 설정을 사용 하도록 설정 하는 방법 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d673edac957e9625f7d948fbe766ee08b23b6b52
ms.sourcegitcommit: 3f491903e0c10db9a3f3fc0940f7b587fcbf9530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85382434"
---
# <a name="how-to-enable-clickonce-security-settings"></a>방법: ClickOnce 보안 설정 사용
ClickOnce 응용 프로그램에 대 한 코드 액세스 보안은 응용 프로그램을 게시 하기 위해 사용 하도록 설정 되어야 합니다. 이 작업은 게시 마법사를 사용 하 여 응용 프로그램을 게시할 때 자동으로 수행 됩니다.

 응용 프로그램을 빌드하거나 디버그할 때 코드 액세스 보안을 사용 하도록 설정 하면 성능에 영향을 줄 수 있습니다. 이러한 경우에는 보안 설정을 일시적으로 사용 하지 않도록 설정할 수 있습니다.

 **프로젝트 디자이너**의 **보안** 페이지에서 ClickOnce 보안 설정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

### <a name="to-enable-clickonce-security-settings"></a>ClickOnce 보안 설정을 사용 하도록 설정 하려면

1. **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **보안** 탭을 클릭합니다.

3. **ClickOnce 보안 설정 사용** 확인란을 선택합니다.

     이제 보안 페이지에서 응용 프로그램에 대 한 보안 설정을 사용자 지정할 수 있습니다.

    > [!NOTE]
    > 이 확인란은 **게시** 마법사를 사용 하 여 응용 프로그램을 게시할 때마다 자동으로 선택 됩니다.

### <a name="to-disable-clickonce-security-settings"></a>ClickOnce 보안 설정을 사용 하지 않도록 설정 하려면

1. **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **보안** 탭을 클릭합니다.

3. **ClickOnce 보안 설정 사용** 확인란의 선택을 취소 합니다.

     응용 프로그램은 완전 신뢰 보안 설정으로 실행 됩니다. **보안** 페이지의 모든 설정은 무시 됩니다.

    > [!NOTE]
    > 게시 마법사를 사용 하 여 응용 프로그램을 게시할 때마다이 확인란이 선택 됩니다. 게시를 성공적으로 완료 한 후에 다시 지워야 합니다.

## <a name="see-also"></a>추가 정보
- [ClickOnce 애플리케이션 보안](../deployment/securing-clickonce-applications.md)
- [ClickOnce 애플리케이션의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)
