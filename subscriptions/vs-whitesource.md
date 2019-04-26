---
title: WhiteSource Bolt 혜택 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 12/19/2018
ms.topic: conceptual
description: Visual Studio 구독에 포함된 WhiteSource Bolt 구독을 활성화하는 방법을 알아봅니다.
searchscope: VS Subscription
ms.openlocfilehash: ab373a21924aaac1a2a5660ed3032c69f04260e1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62811000"
---
# <a name="whitesource-bolt-in-visual-studio-subscriptions"></a>Visual Studio 구독의 WhiteSource Bolt

오픈 소스 취약성을 찾아 해결하고, 빌드에 포함된 모든 오픈 소스 구성 요소에 대한 포괄적인 인벤토리 및 라이선스 보고서를 생성합니다. 일부 Visual Studio 구독에는 6개월의 체험 액세스가 제공됩니다.

## <a name="activation-steps"></a>활성화 단계

1. WhiteSource Bolt 혜택을 활성화하려면 [https://my.visualstudio.com/benefits](https://my.visualstudio.com/benefits?wt.mc_id=o~msft~docs)에 로그인하세요.

2. 도구 섹션에서 WhiteSource Bolt 타일을 찾고 혜택 타일 아래쪽에 있는 **코드 얻기** 링크를 클릭합니다.
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 혜택 타일](_img/vs-whitesource/vs-whitesource-tile.png)

3. 활성화 코드가 표시된 알림을 받게 됩니다.  **클립보드에 코드를 복사**한 다음 **활성화**를 클릭합니다.
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 혜택 코드](_img/vs-whitesource/vs-whitesource-code.png)

4. WhiteSource 웹 페이지에서 **활성화** 단추를 클릭하거나 페이지의 **계정 활성화** 섹션까지 아래로 스크롤합니다.
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 혜택 활성화](_img/vs-whitesource/vs-whitesource-activate-page-cropped.png)

5. 페이지의 **계정 활성화** 섹션에서 4개 단계를 안내받습니다.

   - Microsoft Visual Studio 마켓플레이스에서 WhiteSource Bolt 확장을 [설치](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt)합니다. 확장을 설치할 수 있는 권한이 없는 경우 [Azure DevOps Services용 무료 확장 설치](/azure/devops/marketplace/install-vsts-extension?view=vsts)를 참조하세요.

Azure DevOps Services를 사용하는 경우 녹색 **설치** 단추를 클릭하거나 Team Foundation Server인 경우 **다운로드** 단추를 클릭합니다.  이 예에서는 Azure DevOps Services가 사용됩니다.
> [!div class="mx-imgBorder"]
> ![WhiteSource 혜택 확장 설치](_img/vs-whitesource/vs-whitesource-download-install.png)

- 다음으로, 사용할 Azure DevOps 조직을 선택하고 **확인**을 클릭합니다.  (아직 Azure DevOps Services를 설정하지 않은 경우 [혜택](https://my.visualstudio.com/benefits) 페이지에서 Azure DevOps Services 혜택을 활성화합니다.)

> [!div class="mx-imgBorder"]
> ![WhiteSource 혜택 계정 확인](_img/vs-whitesource/vs-whitesource-confirm-account.png)

- 확장이 설치되어 사용할 준비가 되었는지 확인하는 메시지가 표시됩니다.  **시작**을 클릭하여 WhiteSource Bolt 페이지로 돌아가고 계속합니다.
> [!div class="mx-imgBorder"]
> ![WhiteSource 혜택 설치 완료](_img/vs-whitesource/vs-whitesource-install-complete.png)

5. Azure DevOps 프로젝트 대시보드를 열고 **Azure Pipelines** 메뉴를 클릭한 후 **WhiteSource Bolt**를 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 혜택 확장 추가](_img/vs-whitesource/vs-whitesource-installed-cropped.png)

6. WhiteSource Bolt 혜택 타일에서 활성화 코드를 붙여넣고 **활성화**를 클릭합니다. 각 활성화 코드는 하나의 프로젝트만 활성화하는 데 사용할 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 혜택 활성화 코드](_img/vs-whitesource/vs-whitesource-activate-code-cropped.png)

7. 이제 활성화가 완료되었으며, 남아 있는 구독 기간은 180일입니다.

8. WhiteSource Bolt 확장을 빌드 단계 중 하나로 추가해야 합니다.  [WhiteSource Bolt 페이지](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate)에서 사용 방법을 보여 주는 비디오가 제공됩니다.

9. 빌드를 실행하면 다음과 같은 포괄적인 보고서와 대시보드가 자동으로 생성됩니다.
    - 보안 취약성 대시보드
    - 보안 취약성 보고서
    - 오래된 라이브러리 보고서
    - 라이선스 위험 및 규정 준수 대시보드
    - 인벤토리 보고서

## <a name="eligibility"></a>자격

| 구독 수준                                                 |     채널                                            | 이점                                                          | 갱신 가능?    |
|--------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|---------------|
| Visual Studio Enterprise(Standard)   | VL, Azure, 일반 정품, 선택한 NFR<sup>1</sup> | 6개월       |  예          |
| Visual Studio Professional(표준) | VL, Azure, 일반 정품                                       | 사용할 수 없음                                                           |해당 없음         |
| Visual Studio Test Professional(표준)                         | VL, 일반 정품                                              | 사용할 수 없음                                             |  해당 없음         |
| MSDN 플랫폼(표준)                                          | VL, 일반 정품                                              | 사용할 수 없음                                              | 해당 없음         |
| Visual Studio Dev Essentials | 해당 없음  | 사용할 수 없음 |해당 없음 |
| Visual Studio Enterprise, Visual Studio Professional(월간 클라우드) | Azure                                       | 사용할 수 없음                                                           |해당 없음|

<sup>1</sup> *포함:  Microsoft 파트너 네트워크(Enterprise).  제외: 기타 NFR(전매금지), VSIP(Visual Studio Industry Partner), FTE, MCT Software & Services Developer, BizSpark, Imagine, MVP(Most Valuable Professional), RD(Regional Director), MCT Software & Services, Microsoft 파트너 네트워크(Professional)*

> [!NOTE]
> Microsoft는 더 이상 Visual Studio Professional 연간 구독 및 클라우드 구독에 Visual Studio Enterprise 연간 구독을 제공하지 않습니다. 기존 고객 환경 및 해당 구독의 갱신, 증가, 감소 또는 취소 기능은 변경되지 않습니다. 새 고객은 [https://visualstudio.microsoft.com/vs/pricing/](https://visualstudio.microsoft.com/vs/pricing/)으로 이동하여 Visual Studio를 구입하기 위한 다양한 옵션을 살펴보세요.

어떤 구독을 사용하고 있는지 확실하지 않나요?  자신의 이메일 주소에 할당된 모든 구독을 보려면 [https://my.visualstudio.com/subscriptions](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs)에 연결합니다. 일부 구독이 표시되지 않으면 하나 이상이 다른 전자 메일 주소에 할당되어 있을 수 있습니다.  해당 구독을 보려면 해당 전자 메일 주소로 로그인해야 합니다.

## <a name="support-resources"></a>지원 리소스

- WhiteSource Bolt와 관련하여 도움이 필요하세요?  [https://www.whitesourcesoftware.com/vse_whitesource_bolt/](https://www.whitesourcesoftware.com/vse_whitesource_bolt/)에서 WhiteSource Bolt 담당자와 실시간 채팅이 가능합니다.
- Visual Studio 구독에 대한 판매, 구독, 계정 및 요금 청구에 대한 지원을 받으려면 Visual Studio [구독 지원](https://visualstudio.microsoft.com/subscriptions/support/)에 문의하세요.
- Visual Studio IDE, Azure DevOps Services 또는 기타 Visual Studio 제품이나 서비스와 관련하여 궁금한 점이 있나요?  [Visual Studio 지원](https://visualstudio.microsoft.com/support/)을 참조하세요.