---
title: 클라우드 구독에 대한 관리자 설정 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: lank
ms.date: 07/17/2019
ms.topic: conceptual
description: 클라우드 구독에 대한 관리자 설정
ms.openlocfilehash: 62a350e6061444e3c75878dfd89739011c4641d5
ms.sourcegitcommit: 57866dd72fd0e15ce61128df70729b427a2d02eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315213"
---
# <a name="set-up-administrators-for-visual-studio-cloud-subscriptions"></a>Visual Studio 클라우드 구독에 대한 관리자 설정

Visual Studio 클라우드 구독은 관리자에 의해 관리 됩니다. 이러한 개인들은 구독을 할당하고 할당을 편집하고 구독을 추가 또는 삭제하고 다른 구독 관리 작업을 수행할 수 있습니다.

## <a name="the-azure-subscription-owner-is-the-first-administrator"></a>Azure 구독 소유자가 첫 번째 관리자

Visual Studio 클라우드 구독을 구매하는 경우 구매하는 데 사용된 Azure 구독의 소유자로서 해당 구독에 대한 관리자로 자동 설정됩니다.

[Visual Studio Marketplace](https://marketplace.visualstudio.com/subscriptions)를 통해 클라우드 솔루션 공급자에게 문의하여 클라우드 구독을 구매할 수 있습니다. Visual Studio Marketplace를 통해 구매하는 경우 구매 경험 끝에 사용자를 관리할 기회가 제공됩니다. 해당 옵션을 선택하면 Visual Studio 구독 관리 포털([https://manage.visualstudio.com](https://manage.visualstudio.com))로 이동합니다.

구독을 구입했다면 언제든 [관리 포털](https://manage.visualstudio.com)을 방문할 수 있습니다. 포털에 로그인하고 왼쪽 상단 모서리에서 적절한 Azure 구독을 선택합니다.

클라우드 구독을 구매하는 데 사용된 Azure 구독의 소유자로서 추가 관리자를 할당할 수 있습니다.

## <a name="add-administrators"></a>관리자 추가

관리자를 추가하려면

1. [portal.azure.com](https://portal.azure.com)에서 Azure Portal에 연결합니다.
2. Visual Studio 클라우드 구독을 구매하는 데 사용된 계정으로 로그인합니다.
3. 왼쪽 탐색 창에서 아래로 스크롤하여 **비용 관리 + 청구**로 이동합니다.
4. **내 구독** 목록에서 구매하는 데 사용한 Azure 구독을 선택합니다.
5. 왼쪽 탐색 창에서 목록의 상단 부근에 있는 **액세스 제어**를 클릭합니다.
6. 창의 상단에 있는 **추가** 탭을 클릭합니다.
7. **역할 할당 추가**를 클릭합니다.
8. 오른쪽에 있는 플라이아웃 창에서 창 상단의 **역할** 드롭다운 목록을 클릭하고 아래로 스크롤하여 **사용자 액세스 관리자**를 선택합니다.
9. 사용자 목록에서 아래로 스크롤해 관리자로 만들려는 사용자를 선택합니다. 
10. **저장**을 클릭합니다.
11. **역할 할당** 탭을 클릭하여 선택된 사용자가 사용자 액세스 관리자로 표시되는지 확인합니다.

새 관리자는 이제 [관리 포털](https://manage.visualstudio.com)에 로그인하여 페이지의 왼쪽 상단 모서리에 있는 목록에서 클라우드 구독을 구매하는 데 사용된 동일한 Azure 구독을 선택하고 이러한 구독을 관리할 수 있습니다.

> [!NOTE]
> 관리자로 설정하지 않은 클라우드 구독을 편집할 수 있는 액세스 권한이 사용자에게 있는 경우에는 사용자는 기본 Azure 구독에서 구독을 관리할 수 있는 역할을 가질 수 있습니다. 해당 역할에는 소유자, 기여자, 서비스 관리자 또는 공동 관리자가 포함됩니다. 자세한 내용은 [청구 관리자 추가](/azure/devops/organizations/billing/add-backup-billing-managers?view=vsts)를 참조하세요.

Visual Studio 클라우드 구독에 대한 자세한 내용은 구독 구입에서 [개요](vscloud-overview.md)를 참조합니다. Visual Studio 클라우드 구독을 구매하려면 [https://marketplace.visualstudio.com/subscriptions](https://marketplace.visualstudio.com/subscription)에서 Visual Studio Marketplace를 방문하세요.
