---
title: 클라우드 구독에 대한 관리자 설정 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/28/2018
ms.topic: conceptual
description: 클라우드 구독에 대한 관리자 설정
searchscope: VS Subscription
ms.openlocfilehash: 34479c21ec3cb0672b8d2354595c971b062bba56
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945824"
---
# <a name="set-up-administrators-for-visual-studio-cloud-subscriptions"></a>Visual Studio 클라우드 구독에 대한 관리자 설정

Visual Studio 클라우드 구독은 관리자에 의해 관리 됩니다. 이러한 개인들은 구독을 할당하고 할당을 편집하고 구독을 추가 또는 삭제하고 다른 구독 관리 작업을 수행할 수 있습니다.

## <a name="the-azure-subscription-owner-is-the-first-administrator"></a>Azure 구독 소유자가 첫 번째 관리자

Visual Studio 클라우드 구독을 구매하는 경우 구매하는 데 사용된 Azure 구독의 소유자로서 해당 구독에 대한 관리자로 자동 설정됩니다.

[Visual Studio Marketplace](https://marketplace.visualstudio.com/subscriptions)를 통해 클라우드 솔루션 공급자에게 문의하여 클라우드 구독을 구매할 수 있습니다. Visual Studio Marketplace를 통해 구매하는 경우 구매 경험 끝에 사용자를 관리할 기회가 제공됩니다. 해당 옵션을 선택하면 Visual Studio 구독 관리 포털 - [https://manage.visualstudio.com](https://manage.visualstudio.com)로 이동합니다.

구독을 구입했으면 언제든 [관리 포털](https://manage.visualstudio.com)을 방문할 수 있습니다. 포털에 로그인하고 왼쪽 상단 모서리에서 적절한 Azure 구독을 선택합니다.

클라우드 구독을 구매하는 데 사용된 Azure 구독의 소유자로서 추가 관리자를 할당할 수 있습니다.

## <a name="add-administrators"></a>관리자 추가

관리자를 추가하려면

1. [portal.azure.com](https://portal.azure.com)에서 Azure Portal에 연결합니다.
2. Visual Studio 클라우드 구독을 구매하는 데 사용된 계정으로 로그인합니다.
3. 왼쪽 탐색 창에서 아래로 스크롤하여 **비용 관리 + 청구**로 이동합니다.
4. **내 구독** 목록에서 구매하는 데 사용한 Azure 구독을 선택합니다.
5. 왼쪽 탐색 창에서 목록의 상단 부근에 있는 **액세스 제어**를 클릭합니다.
6. 창의 상단에 있는 **추가** 탭을 클릭합니다.
7. 오른쪽의 플라이 아웃 창에서 관리자로 만들려는 구독자의 이름을 클릭합니다.
8. 창의 상단에서 **역할** 드롭다운 목록을 클릭하고 아래로 스크롤하여 **사용자 액세스 관리자**를 선택합니다.
9. **저장**을 클릭합니다.

사용자가 지정한 구독자는 페이지의 가운데에 표시되며 구독자의 역할은 "사용자 액세스 관리자"로 표시됩니다.

새 관리자는 지금 [관리 포털](https://manage.visualstudio.com)에 로그인하여 페이지의 왼쪽 상단 모서리에 있는 목록에서 클라우드 구독을 구매하는 데 사용된 동일한 Azure 구독을 선택하고 이러한 구독을 관리하기 시작합니다.

> [!NOTE]
> 관리자로 설정하지 않은 클라우드 구독을 편집할 수 있는 액세스 권한이 사용자에게 있는 경우에는 사용자는 기본 Azure 구독에서 구독을 관리할 수 있는 역할을 가질 수 있습니다. 해당 역할에는 소유자, 기여자, 서비스 관리자 또는 공동 관리자가 포함됩니다. 자세한 내용은 [청구 관리자 추가](/azure/devops/organizations/billing/add-backup-billing-managers?view=vsts)를 참조하세요.

Visual Studio 클라우드 구독에 대한 자세한 내용은 클라우드 구독 구입에서 [개요](vscloud-overview.md)를 참조합니다. Visual Studio 클라우드 구독을 구매하려면 [https://marketplace.visualstudio.com/subscriptions](https://marketplace.visualstudio.com/subscription)에서 Visual Studio Marketplace를 방문하세요.