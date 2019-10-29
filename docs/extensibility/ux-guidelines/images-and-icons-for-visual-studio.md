---
title: Visual Studio의 이미지 및 아이콘 | Microsoft Docs
ms.date: 04/26/2017
ms.topic: conceptual
ms.assetid: f410325e-9cf2-4f39-b6d7-b672121c2691
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e449fb30bd95319a46d1db50da63778f6800a70
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "72983865"
---
# <a name="images-and-icons-for-visual-studio"></a>Visual Studio의 이미지 및 아이콘
## <a name="BKMK_ImageUseInVisualStudio"></a>Visual Studio에서 이미지 사용
 아트 워크를 만들기 전에 [Visual Studio 이미지 라이브러리](https://www.microsoft.com/download/details.aspx?id=35825)에서 1000 개 이상의 이미지를 사용 하는 것이 좋습니다.

### <a name="types-of-images"></a>이미지 형식

- **아이콘**. 명령, 계층, 템플릿 등에 표시 되는 작은 이미지 Visual Studio에 사용 되는 기본 아이콘 크기는 16x16 PNG입니다. 이미지 서비스에 의해 생성 된 아이콘은 HDPI 지원에 대 한 XAML 형식을 자동으로 생성 합니다.

    > [!NOTE]
    > 메뉴 시스템에서 이미지를 사용 하는 동안에는 모든 명령에 대 한 아이콘을 만들면 안 됩니다. 명령에서 아이콘을 가져와야 하는지 여부를 확인 하려면 [Visual Studio에 대 한 메뉴 및 명령을](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md) 참조 하세요.

- **작게.** 새 프로젝트 대화 상자와 같은 대화 상자에서 미리 보기 영역에 사용 되는 이미지입니다.

- **대화 상자 이미지입니다.** 설명 그래픽 또는 메시지 표시기로 대화 상자 또는 마법사에 표시 되는 이미지입니다. 어려운 개념을 설명 하거나 사용자의 주의를 얻기 위해 필요한 경우에만 (경고, 경고)를 사용 합니다.

- **애니메이션 이미지.** 진행률 표시기, 상태 표시줄 및 작업 대화 상자에서 사용 됩니다.

- **커서로.** 마우스를 사용 하 여 작업이 허용 되는지 여부를 나타내는 데 사용 됩니다 .이 경우 개체를 삭제할 수 있습니다.

## <a name="BKMK_IconDesign"></a>아이콘 디자인

### <a name="overview"></a>개요
 Visual Studio는 깨끗 한 기 하 도형을 사용 하는 최신 스타일의 아이콘을 사용 합니다 .이 아이콘은 긍정/부정 (밝은/어둡게)의 50/50 잔액 이며, 이해 하기 쉬운 직접 메타포를 사용 합니다. 중요 한 아이콘 디자인 지점은 명확성, 단순화 및 컨텍스트를 중심으로 합니다.

- **명확성:** 아이콘에 의미 및 individuality을 제공 하는 핵심 메타포에 초점을 둡니다.

- **단순화:** 아이콘을 핵심 의미로 축소 합니다. 필요한 요소만 포함 하 고 frills 하지 않고 테마를 가져옵니다.

- **컨텍스트:** 개념 개발 중에 아이콘 역할의 모든 측면을 고려 합니다 .이는 아이콘의 핵심 비유를 구성 하는 요소를 결정할 때 매우 중요 합니다.

  아이콘을 사용 하면 다음과 같은 여러 가지 디자인 요소를 방지할 수 있습니다.

- 해당 하는 경우를 제외 하 고 UI 요소를 나타내는 아이콘을 사용 하지 마세요. UI 요소가 일반적이 고 명확 하거나 고유 하지 않은 경우 보다 추상적 이거나 기호화 된 방법을 선택 합니다.

- 문서, 폴더, 화살표 및 돋보기와 같은 일반적인 요소를 남용 하지 마십시오. 아이콘의 의미에 필요한 경우에만 이러한 요소를 사용 합니다. 예를 들어 오른쪽에 있는 돋보기는 검색, 찾아보기 및 찾기만 표시 해야 합니다.

- 일부 레거시 아이콘 요소는 큐브 뷰의 사용을 유지 하지만 요소에 명확 하지 않은 경우에는 큐브 뷰를 사용 하 여 새 아이콘을 만들지 마십시오.

- 너무 많은 정보를 아이콘에 표시 하지 마세요. 쉽게 인식 하거나 인식할 수 있는 간단한 이미지는 너무 복잡 한 이미지 보다 훨씬 더 유용 합니다. 아이콘은 전체 스토리를 구분할 수 없습니다.

### <a name="icon-creation"></a>아이콘 만들기

#### <a name="concept-development"></a>개념 개발
 Visual Studio의 UI 내에는 다양 한 아이콘 형식이 있습니다. 개발 하는 동안 아이콘 형식을 신중 하 게 고려해 야 합니다. 아이콘 요소에 명확 하지 않거나 드물게 발생 하는 UI 개체를 사용 하지 마세요. 이러한 경우에는 스마트 태그 아이콘을 사용 하는 등의 기호를 선택 합니다. 왼쪽에 있는 추상 태그의 의미는 오른쪽에 있는 모호한 UI 기반 버전 보다 더 명확 합니다.

|||
|-|-|
|**기호화 된 이미지의 올바른 사용**|**기호화 된 이미지의 잘못 된 사용**|
|![올바른 스마트 태그 아이콘](../../extensibility/ux-guidelines/media/0404-01_smarttagcorrect.png "0404-01.txt _SmartTagCorrect")|![잘못 된 스마트 태그 아이콘](../../extensibility/ux-guidelines/media/0404-02_smarttagincorrect.png "0404-02_SmartTagIncorrect")|

 표준, 쉽게 인식할 수 있는 UI 요소가 아이콘에 대해 잘 작동 하는 경우가 있습니다. Add Window는 이러한 예입니다.

|||
|-|-|
|**아이콘의 올바른 UI 요소**|**아이콘의 잘못 된 UI 요소**|
|![올바른 창 추가 아이콘](../../extensibility/ux-guidelines/media/0404-03_addwindowcorrect.png "0404 -03 _AddWindowCorrect")|![잘못 된 창 추가 아이콘](../../extensibility/ux-guidelines/media/0404-04_addwindowincorrect.png "0404-04_AddWindowIncorrect")|

 아이콘의 의미를 반드시 지정 해야 하는 경우가 아니면 문서를 기본 요소로 사용 하지 마세요. 문서 추가 (아래)의 문서 요소를 사용 하지 않으면 의미가 손실 되며, 새로 고침을 사용 하면 문서 요소가 의미를 전달 하는 데 필요 하지 않습니다.

|||
|-|-|
|**문서 아이콘 사용을 수정 합니다.**|**문서 아이콘 사용이 잘못 되었습니다.**|
|![올바른 문서 아이콘](../../extensibility/ux-guidelines/media/0404-05_documenticoncorrect.png "0404 -05 _L")|![잘못 된 문서 아이콘](../../extensibility/ux-guidelines/media/0404-06_documenticonincorrect.png "0404 -06 _DocumentIconIncorrect 않음")|

 "표시"의 개념은 모든 파일 표시 예제와 같이 표시 되는 항목을 가장 잘 보여 주는 아이콘으로 표시 되어야 합니다. 리소스 뷰 예제와 같이 필요한 경우 "보기"의 개념을 나타내기 위해 렌즈 메타포를 사용할 수 있습니다.

|||
|-|-|
|**표시**|**봅니다**|
|![아이콘 표시](../../extensibility/ux-guidelines/media/0404-07_show.png "0404 -07 _")|![보기 아이콘](../../extensibility/ux-guidelines/media/0404-08_view.png "0404-08_View")|

 오른쪽에 연결 된 돋보기 아이콘은 검색, 찾기 및 찾아보기만 표시 해야 합니다. 더하기 기호 또는 빼기 기호가 있는 왼쪽 변형은 확대/축소만 표시 해야 합니다.

|||
|-|-|
|**조건을**|**맞게**|
|![검색 아이콘](../../extensibility/ux-guidelines/media/0404-09_search.png "0404-09_Search")|![확대/축소 아이콘](../../extensibility/ux-guidelines/media/0404-10_zoom.png "0404 -10 _ 확대/축소")|

 트리 뷰에서는 폴더 아이콘과 한정자를 모두 사용 하지 마세요. 사용할 수 있는 경우 한정자만 사용 합니다.

|||
|-|-|
|**올바른 트리 뷰 아이콘**|**잘못 된 트리 뷰 아이콘**|
|![올바른 트리 뷰 아이콘 &#40;1&#41; ](../../extensibility/ux-guidelines/media/0404-11_treeviewcorrect1.png "0404-11_TreeViewCorrect1") ![올바른 트리 뷰 아이콘 &#40;2&#41; ](../../extensibility/ux-guidelines/media/0404-12_treeviewcorrect2.png "0404-12_TreeViewCorrect2")|![잘못 된 트리 뷰 &#40;아이콘&#41; 1](../../extensibility/ux-guidelines/media/0404-13_treeviewincorrect1.png "0404-13_TreeViewIncorrect1") ![잘못 된 트리 &#40;뷰&#41; 아이콘 2](../../extensibility/ux-guidelines/media/0404-14_treeviewincorrect2.png "0404-14_TreeViewIncorrect2")|

### <a name="style-details"></a>스타일 세부 정보

#### <a name="layout"></a>레이아웃
 표준 16x16 아이콘에 대해 표시 된 Stack 요소:

 ![16x16 아이콘의 레이아웃 스택](../../extensibility/ux-guidelines/media/0404-15_layoutstack.png "0404 checks.-15-minutes _LayoutStack")<br />16 x 16 아이콘에 대한 레이아웃 스택

 상태 알림 요소는 독립 실행형 아이콘으로 사용 하는 것이 더 좋습니다. 그러나 작업 완료 아이콘과 같이 기본 요소에 대 한 알림을 누적 하는 컨텍스트가 있습니다.

 ![Visual Studio의 독립 실행형 알림](../../extensibility/ux-guidelines/media/0404-16_standalonenotificationicons.png "0404-16_StandaloneNotificationIcons")<br />독립 실행형 알림 아이콘

 ![작업 완료 아이콘](../../extensibility/ux-guidelines/media/0404-17_taskcomplete.png "0404 -17 _TaskComplete")<br />작업 완료 아이콘

 프로젝트 아이콘은 일반적으로 여러 크기를 포함 하는 .ico 파일입니다. 대부분의 16x16 아이콘에는 같은 요소가 포함 되어 있습니다. 32x32 버전은 해당 하는 경우 프로젝트 형식을 포함 하 여 자세한 정보를 포함 합니다.

 ![Visual Studio의 프로젝트 아이콘](../../extensibility/ux-guidelines/media/0404-18_iconprojectthreesizes.png "0404-18_IconProjectThreeSizes")<br />VB Windows 컨트롤 라이브러리 프로젝트 아이콘, 16x16 및 32x32

 아이콘을 픽셀 프레임 안에 배치 합니다. 가능 하지 않은 경우 아이콘을 프레임의 위쪽 및/또는 오른쪽에 맞춥니다.

 ![픽셀 프레임 내에서 가운데에 있는 아이콘](../../extensibility/ux-guidelines/media/0404-19_iconcentered.png "0404 -19 _L 가운데 맞춤")<br />픽셀 프레임 내의 가운데에 맞춰진 아이콘

 ![픽셀 프레임의 오른쪽 위에 맞춰진 아이콘](../../extensibility/ux-guidelines/media/0404-20_icontopright.png "0404 -20 _IconTopRight")<br />아이콘을 프레임의 오른쪽 위에 맞춥니다.

 ![가운데에 맞춰지고 픽셀 프레임의 위쪽에 맞춰진 아이콘](../../extensibility/ux-guidelines/media/0404-21_icontopalign.png "0404 -21 _IconTopAlign")<br />프레임 가운데에 맞춰지고 프레임의 위쪽에 맞춰진 아이콘

 이상적인 맞춤 및 균형을 유지 하려면 아이콘의 기본 요소를 작업 문자 모양으로 방해 하지 않는지 하지 마십시오. 기본 요소의 왼쪽 위 근처에 문자 모양을 삽입 합니다. 추가 요소를 추가할 때 아이콘의 맞춤 및 균형을 고려 합니다.

|||
|-|-|
|**올바른 맞춤 및 잔액**|**잘못 된 맞춤 및 잔액**|
|![올바른 아이콘 잔액 및 맞춤](../../extensibility/ux-guidelines/media/0404-22_alignbalancecorrect.png "0404-22_AlignBalanceCorrect")|![잘못 된 아이콘 잔액 및 맞춤](../../extensibility/ux-guidelines/media/0404-23_alignbalanceincorrect.png "0404-23_AlignBalanceIncorrect")|

 요소를 공유 하 고 집합에 사용 되는 아이콘에 대해 크기 패리티를 확인 합니다. 잘못 된 페어링에서 원과 화살표는 크기가 클 수 있으며 일치 하지 않습니다.

|||
|-|-|
|**올바른 크기 패리티**|**잘못 된 크기 패리티**|
|![올바른 아이콘 크기 및 패리티](../../extensibility/ux-guidelines/media/0404-24_sizeparitycorrect.png "0404 -24 _SizeParityCorrect.")|![잘못 된 아이콘 크기 및 패리티](../../extensibility/ux-guidelines/media/0404-25_sizeparityincorrect.png "0404 -25 _SizeParityIncorrect")|

 일관 된 선 및 시각적 가중치를 사용 합니다. Side-by-side 비교를 사용 하 여 빌드하는 아이콘이 다른 아이콘과 비교 되는 방식을 평가 합니다. 전체 16x16 프레임을 사용 하지 마세요. 15x15이 하를 사용 합니다. 음수-긍정 (짙은 대비) 비율은 50/50 이어야 합니다.

|||
|-|-|
|**음수-긍정 비율 수정**|**음수-긍정 비율이 잘못 되었습니다.**|
|![아이콘 &#40;1에 대 한 올바른 시각적 가중치&#41;](../../extensibility/ux-guidelines/media/0404-26_visualweightcorrect1.png "0404-26_VisualWeightCorrect1")<br /><br /> ![아이콘 &#40;2에 대 한 올바른 시각적 가중치&#41;](../../extensibility/ux-guidelines/media/0404-27_visualweightcorrect2.png "0404 -27 _VisualWeightCorrect2 ")<br /><br /> ![아이콘 &#40;3의 올바른 시각적 가중치&#41;](../../extensibility/ux-guidelines/media/0404-28_visualweightcorrect3.png "0404-28-preview _VisualWeightCorrect3 ")|![아이콘의 시각적 가중치가 잘못 되었습니다.](../../extensibility/ux-guidelines/media/0404-29_visualweightincorrect.png "0404-29_VisualWeightIncorrect")|

 요소 무결성을 저하 시 키 지 않고 간단 하 고, 비교할 수 있는 도형 및 보조 각도를 사용 하 여 요소를 빌드합니다. 가능 하면 45 ° 또는 90 ° 각도를 사용 합니다.

 ![올바른 아이콘 각도](../../extensibility/ux-guidelines/media/0404-30_iconanglescorrect.png "0404-30_IconAnglesCorrect")

#### <a name="perspective"></a>큐브 뷰
 아이콘을 명확 하 고 이해 하기 쉽게 유지 합니다. 큐브 뷰 및 광원은 필요한 경우에만 사용 합니다. Icon 요소에서 큐브 뷰를 사용 하지 않는 것이 좋지만 일부 요소는이를 제외 하 고 인식할 수 없습니다. 이러한 경우 스타일이 있는 큐브 뷰는 요소의 명확성을 전달 합니다.

 ![3 점 원근감](../../extensibility/ux-guidelines/media/0404-31_3pointperspective.png "0404-31_3PointPerspective")<br />3점 원근감

 ![1 점 관점](../../extensibility/ux-guidelines/media/0404-32_1pointperspective.png "0404 -32 _1PointPerspective")<br />1점 원근감

 대부분의 요소는 오른쪽에 연결 하거나 오른쪽으로 회전 해야 합니다.

 ![오른쪽 사선 아이콘](../../extensibility/ux-guidelines/media/0404-33_angledright.png "0404-33_AngledRight")

 개체에 필요한 명확성을 추가 하는 경우에만 광원을 사용 합니다.

|||
|-|-|
|**올바른 광원 원본**|**잘못 된 광원 원본**|
|![아이콘의 올바른 광원](../../extensibility/ux-guidelines/media/0404-34_lightsourcescorrect.png "0404-34_LightSourcesCorrect")|![아이콘의 잘못 된 광원](../../extensibility/ux-guidelines/media/0404-35_lightsourcesincorrect.png "0404-35_LightSourcesIncorrect")|

 개요를 사용 하 여 가독성을 향상 시키거나 비유를 더 잘 전달 합니다. 음의 긍정 (짙은 조명) 잔액은 50/50입니다.

|||
|-|-|
|**윤곽선의 올바른 사용**|**잘못 된 윤곽선 사용**|
|![올바른 윤곽선](../../extensibility/ux-guidelines/media/0404-36_outlinescorrect.png "0404 -36 _OutlinesCorrect.")|![잘못 된 윤곽선](../../extensibility/ux-guidelines/media/0404-37_outlinesincorrect.png "0404 -37 _OutlinesIncorrect")|

#### <a name="icon-types"></a>아이콘 유형
 **셸 및 명령 모음** 아이콘은 하나 이상의 요소로 구성 됩니다. 하나는 기본, 하나는 하나, 하나의 동작 또는 한 가지입니다.

 ![셸 및 명령 모음 아이콘의 예](../../extensibility/ux-guidelines/media/0404-38_shellicons.png "0404-38_ShellIcons")<br />셸 및 명령 모음 아이콘의 예

 **도구 창 명령 모음** 아이콘은 하나 이상의 요소로 구성 됩니다. 하나는 기본, 단일 한정자, 한 가지 동작 또는 한 상태입니다.

 ![도구 창 명령 모음 아이콘의 예](../../extensibility/ux-guidelines/media/0404-39_toolwindowcommandbaricons.png "0404-39_ToolWindowCommandBarIcons")<br />도구 창 명령 모음 아이콘의 예

 **트리 뷰 disbmbiguator** 아이콘은 하나 이상의 요소로 구성 됩니다. 하나는 기본, 단일 한정자, 한 가지 동작 또는 한 가지입니다.

 ![트리 뷰 disbmbiguator 아이콘의 예](../../extensibility/ux-guidelines/media/0404-40_treeviewicons.png "0404-40_TreeViewIcons")<br />트리 뷰 disbmbiguator 아이콘의 예

 **상태 기반 값 분류** 아이콘은 활성, 활성, 사용 안 함 및 비활성 사용 안 함 상태로 존재 합니다.

 ![상태 기반 값 분류 아이콘의 예](../../extensibility/ux-guidelines/media/0404-41_statebasedtaxonomy.png "0404-41.rpm _StateBasedTaxonomy")<br />상태 기반 값 분류 아이콘의 예

 **IntelliSense** 아이콘은 하나 이상의 다음 요소로 구성 됩니다. 하나는 하나의 기본, 하나는 하나의 한정자, 한 가지는 상태입니다.

 ![IntelliSense 아이콘의 예](../../extensibility/ux-guidelines/media/0404-42_intellisenseicons.png "0404-42_IntelliSenseIcons")<br />IntelliSense 아이콘의 예

 **작은 (16x16) 프로젝트** 아이콘에는 두 개 이상의 요소가 있어야 합니다. 즉, 하나의 기본 및 하나의 한정자가 있어야 합니다.

 ![작은 (16x16) 프로젝트 아이콘의 예](../../extensibility/ux-guidelines/media/0404-43_16x16project1.png "0404-43_16x16Project1") ![16x16 프로젝트 아이콘 &#40;2&#41; ](../../extensibility/ux-guidelines/media/0404-44_16x16project2.png "0404-44_16x16Project2") ![16x16 프로젝트 아이콘 &#40;3&#41; ](../../extensibility/ux-guidelines/media/0404-45_16x16project3.png "0404-45_16x16Project3")<br />작은 (16x16) 프로젝트 아이콘의 예

 **매우 큼 (32x32) 프로젝트** 아이콘은 다음 요소로 구성 됩니다. 하나는 기본, 1 개에서 2 개의 한정자로, 하나는 언어 오버레이입니다.

 ![크게 (32x32) 프로젝트 아이콘의 예](../../extensibility/ux-guidelines/media/0404-46_32x32project.png "0404 -46 _32x32Project 프로젝트")<br />크게 (32x32) 프로젝트 아이콘의 예

### <a name="production-details"></a>프로덕션 세부 정보
 모든 새 UI 요소는 Windows Presentation Foundation (WPF)를 사용 하 여 만들어야 하며 WPF의 모든 새 아이콘은 32 비트 PNG 형식 이어야 합니다. 24 비트 PNG는 투명 하 게 지원 되지 않으므로 아이콘에는 권장 되지 않는 레거시 형식입니다.

 해상도를 96 DPI로 저장 합니다.

#### <a name="file-types"></a>파일 형식

- **32 비트 PNG:** 아이콘의 기본 형식입니다. 단일 래스터 (픽셀) 이미지를 저장할 수 있는 무손실 데이터 압축 파일 형식입니다. 32 비트 PNG 파일은 알파 채널 투명도, 감마 보정 및 인터레이스를 지원 합니다.

- **32 비트 BMP:** 비 WPF 컨트롤의 경우 XP 또는 높은 색이 라고도 하는 32 비트 BMP는 알파 채널 투명도를 사용 하는 트루 색 이미지인 RGB/A 이미지 형식입니다. 알파 채널은 Adobe Photoshop에서 지정 된 투명도 계층으로, 비트맵 내에 추가 (4 번째) 색 채널로 저장 됩니다. 검정 배경은 모든 32 비트 BMP 파일에 아트 워크를 제작 하는 동안 추가 되어 색 깊이에 대 한 빠른 시각적 신호를 제공 합니다. 이 검은색 배경은 UI에서 마스킹할 영역을 나타냅니다.

- **32 비트 ICO:** 프로젝트 아이콘 및 항목 추가 모든 ICO 파일은 알파 채널 투명도 (RGB/A)를 사용 하는 32 비트 트루 색입니다. .ICO 파일은 여러 크기와 색 깊이를 저장할 수 있으므로, Vista 아이콘은 종종 16x16, 32x32, 48x48 및 256x256 이미지 크기를 포함 하는 .ICO 형식으로 되어 있습니다. Windows 탐색기에 제대로 표시 하려면 각 이미지 크기에 대 한 24 비트 및 8 비트 색 깊이에 .ICO 파일을 저장 해야 합니다.

- **XAML:** 디자인 화면 및 Windows 표시기 XAML 아이콘은 크기 조정, 회전, 파일링 및 투명도를 지 원하는 벡터 기반 이미지 파일입니다. 현재는 Visual Studio에서 일반적이 지 않지만 유연성 때문에 더 인기 있습니다.

- **SVG**

- **24 비트 BMP:** Visual Studio 명령 모음입니다. 트루 컬러 RGB 이미지 형식인 24 비트 BMP는 마젠타 (R = 255, G = 0, B = 255)를 사용 하 여 녹아웃 투명도 계층의 색 키로 투명도 계층을 만드는 아이콘 규칙입니다. 24 비트 BMP에서는 모든 자홍 서피스가 배경색을 사용 하 여 표시 됩니다.

- **24 비트 GIF:** Visual Studio 명령 모음 투명도를 지 원하는 트루 컬러 RGB 이미지 형식입니다. GIF 파일은 마법사 아트 워크 및 GIF 애니메이션에서 자주 사용 됩니다.

### <a name="icon-construction"></a>아이콘 생성
 Visual Studio에서 가장 작은 아이콘 크기는 16x16입니다. 일반적으로 사용 되는 가장 큰 값은 32x32입니다. 아이콘을 디자인할 때 16x16, 24x24 또는 32x32 프레임 전체를 채우지 않도록 주의 하세요. 이해 하기 쉬운 것은 사용자를 인식 하는 데 필수적입니다. 아이콘을 작성 하는 경우 다음 사항을 따릅니다.

- 아이콘은 명확 하 고 이해 하기 쉬워야 일관 되어야 합니다.

- 상태 알림 요소를 아이콘 기준 요소 위에 누적 하지 않고 단일 아이콘으로 사용 하는 것이 좋습니다. 특정 컨텍스트에서 UI를 사용 하려면 상태 요소를 기본 요소와 쌍으로 연결 해야 할 수 있습니다.

- 프로젝트 아이콘은 일반적으로 여러 크기를 포함 하는 .ico 파일입니다. 16x16, 24x24 및 32x32 아이콘만 업데이트 됩니다. 대부분의 16x16 및 24x24 아이콘에는 같은 요소가 포함 됩니다. 32x32 아이콘에는 해당 되는 경우 프로젝트 언어 형식을 포함 하 여 자세한 내용이 포함 되어 있습니다.

- 32x32 아이콘의 경우 기본 요소에는 일반적으로 2 픽셀의 선 가중치가 있습니다. 1 ~ 2 픽셀 선 두께는 세부 요소에 사용할 수 있습니다. 최적 판단을 사용 하 여 더 적합 한 것을 결정 합니다.

- 16x16 및 24x24 아이콘의 요소 사이에 적어도 1 픽셀 간격이 있습니다. 32x32 아이콘의 경우 요소 사이와 modifier 및 base 요소 사이에 2 픽셀 간격을 사용 합니다.

  ![크기가 16x16, 24x24 및 32x32 인 아이콘의 요소 간격](../../extensibility/ux-guidelines/media/0404-47_elementspacing.png "0404 -47 _ElementSpacing")<br />크기가 16x16, 24x24 및 32x32 인 아이콘의 요소 간격

#### <a name="color-and-accessibility"></a>색 및 접근성
 Visual Studio 규정 준수 지침을 적용 하려면 제품의 모든 아이콘이 색 및 대비에 대 한 접근성 요구 사항을 통과 해야 합니다. 이는 아이콘 반전을 통해 수행 되며, 디자인 하는 경우 제품에서 프로그래밍 방식으로 반전 된다는 점을 인식 해야 합니다.

 Visual Studio 아이콘에서 색을 사용 하는 방법에 대 한 자세한 내용은 [이미지에서 색 사용](../../extensibility/ux-guidelines/images-and-icons-for-visual-studio.md#BKMK_UsingColorInImages)을 참조 하세요.

## <a name="BKMK_UsingColorInImages"></a>이미지에서 색 사용

### <a name="overview"></a>개요
 Visual Studio의 아이콘은 주로 단색입니다. 색은 특정 정보를 전달 하기 위해 예약 되어 있으며 장식에는 적용 되지 않습니다. 색이 사용 됩니다.

- 작업을 나타내려면

- 상태 알림에 대 한 사용자 경고

- 언어 소속을 지정 하려면

- IntelliSense 내에서 항목을 구분 하려면

### <a name="accessibility"></a>액세스 가능성
 Visual Studio 규정 준수 지침을 적용 하려면 제품에 체크 인 한 모든 아이콘이 색 및 대비에 대 한 접근성 요구 사항을 통과 해야 합니다. 시각적 언어 팔레트의 색은 테스트 되었으며 이러한 요구 사항을 충족 합니다.

#### <a name="color-inversion-for-dark-themes"></a>어두운 테마의 색 반전
 Visual Studio 어두운 테마에서 아이콘이 올바른 명암비로 표시 되도록 하기 위해 반전은 프로그래밍 방식으로 적용 됩니다. 이 가이드의 색은 올바르게 반전 되도록 파트에서 선택 되었습니다. 이 색상표에 대 한 색 사용을 제한 하거나 반전이 적용 될 때 예기치 않은 결과를 얻을 수 있습니다.

 ![색이 반전 된 아이콘의 예](../../extensibility/ux-guidelines/media/0405-01_darkthemeinversion.png "0405-01.txt _DarkThemeInversion")<br />색이 반전 된 아이콘의 예

### <a name="base-palette"></a>기본 색상표
 모든 표준 아이콘에는 세 가지 기본 색이 포함 되어 있습니다. 3D 도구 아이콘에 대해 하나 또는 두 개의 예외를 포함 하는 아이콘에는 그라데이션 또는 그림자가 포함 되지 않습니다.

|사용법|name|값 (밝은 테마)|Swatch|예제|
|-----------|----------|---------------------------|------------|-------------|
|배경/어둡게|VS BG|424242/66, 66, 66|![견본 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|![기본 색상표 예](../../extensibility/ux-guidelines/media/0405-02_basepaletteexample.png "0405-02_BasePaletteExample")|
|전경/밝은|VS FG|F0EFF1/240239241|![견본 F0EFF1](../../extensibility/ux-guidelines/media/0405_f0eff1.png "0405_F0EFF1")||
|윤곽선|VS Out|F6F6F6/246246246|![견본 F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")||

 기본 색 외에도 각 아이콘에는 확장 된 색상표에서 하나의 추가 색이 포함 될 수 있습니다.

### <a name="extended-palette"></a>확장 된 색상표

#### <a name="action-modifiers"></a>동작 한정자
 아래 4 가지 색은 작업 한정자에 필요한 작업 유형을 표시 합니다.

|사용법|name|값 (모든 테마)|Swatch|
|-----------|----------|--------------------------|------------|
|양수|VS 동작 녹색|388A34/56138, 52|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|
|음수|VS 동작 빨강|A1260D/161, 38, 13|![견본 A1260D](../../extensibility/ux-guidelines/media/0405_a1260d.png "0405_A1260D")|
|중립|VS 작업 Blue|00539C/0, 83156|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|
|만들기/새로 만들기|VS 작업 주황색|C27D1A/194156, 26|![견본 C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|

##### <a name="examples"></a>예
 녹색은 "Add", "Run", "Play" 및 "Validate"와 같은 긍정 작업 한정자에 사용 됩니다.

|||||
|-|-|-|-|
|![실행 아이콘](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405-03_ActionModifierRun")<br />Run|![쿼리 실행 아이콘](../../extensibility/ux-guidelines/media/0405-04_executequery.png "0405-04_ExecuteQuery")<br />쿼리 실행|![모든 단계 재생 아이콘](../../extensibility/ux-guidelines/media/0405-05_playallsteps.png "-05 0405")<br />모든 단계 재생|![컨트롤 추가 아이콘](../../extensibility/ux-guidelines/media/0405-06_addcontrol.png "0405-06_AddControl")<br />컨트롤 추가|

 빨간색은 "삭제", "중지", "취소" 및 "닫기"와 같은 음수 동작 한정자에 사용 됩니다.

|||||
|-|-|-|-|
|![관계 삭제 아이콘](../../extensibility/ux-guidelines/media/0405-07_deleterelationship.png "0405-07_DeleteRelationship")<br />관계 삭제|![열 삭제 아이콘](../../extensibility/ux-guidelines/media/0405-08_deletecolumn.png "0405-08_DeleteColumn")<br />열 삭제|![쿼리 중지 아이콘](../../extensibility/ux-guidelines/media/0405-09_stopquery.png "0405 -09 _StopQuery")<br />쿼리 중지|![오프 라인 연결 아이콘](../../extensibility/ux-guidelines/media/0405-10_connectionoffline.png "0405 -10 _ConnectionOffline")<br />오프 라인 연결|

 Blue는 "열기", "다음", "이전", "가져오기" 및 "내보내기"와 같이 주로 화살표로 표시 되는 중립 작업 한정자에 적용 됩니다.

|||||
|-|-|-|-|
|![필드로 이동 아이콘](../../extensibility/ux-guidelines/media/0405-11_gotofield.png "0405-11_GoToField")<br />이동 필드|![일괄 처리&#45;체크 인 아이콘](../../extensibility/ux-guidelines/media/0405-12_batchedcheckin.png "0405 -12 _BatchedCheckIn")<br />일괄 처리 된 체크 인|![주소 편집기 아이콘](../../extensibility/ux-guidelines/media/0405-13_addresseditor.png "0405-13_AddressEditor")<br />주소 편집기|![연결 편집기 아이콘](../../extensibility/ux-guidelines/media/0405-14_associationeditor.png "0405 -14 _AssociationEditor")<br />연결 편집기|

 진한 황금색은 주로 "New" 한정자에 사용 됩니다.

|||||
|-|-|-|-|
|![새 프로젝트 아이콘](../../extensibility/ux-guidelines/media/0405-15_newproject.png "0405 checks.-15-minutes _NewProject")<br />새 프로젝트|![새 그래프 만들기 아이콘](../../extensibility/ux-guidelines/media/0405-16_createnewgraph.png "0405-16_CreateNewGraph")<br />새 그래프 만들기|![새 단위 테스트 아이콘](../../extensibility/ux-guidelines/media/0405-17_newunittest.png "0405 -17 _NewUnitTest")<br />새 단위 테스트|![새 목록 항목 아이콘](../../extensibility/ux-guidelines/media/0405-18_newlistitem.png "0405 -18 _NewListItem")<br />새 목록 항목|

#### <a name="special-cases"></a>특수 한 경우
 특수 한 경우에는 색이 지정 된 동작 한정자를 독립 실행형 아이콘으로 독립적으로 사용할 수 있습니다. 아이콘에 사용 되는 색은 아이콘이 연결 된 동작을 반영 합니다. 이 사용은 다음을 비롯 한 아이콘의 작은 하위 집합으로 제한 됩니다.

||||||
|-|-|-|-|-|
|![실행 아이콘](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405-03_ActionModifierRun")<br />Run|![중지 아이콘](../../extensibility/ux-guidelines/media/0405-19_stop.png "0405 -19 _Stop")<br />Stop|![삭제 아이콘](../../extensibility/ux-guidelines/media/0405-20_delete.png "0405-20_Delete")<br />삭제|![저장 아이콘](../../extensibility/ux-guidelines/media/0405-21_save.png "0405-21_Save")<br />저장|![뒤로 탐색 아이콘](../../extensibility/ux-guidelines/media/0405-22_navigateback.png "0405-22_NavigateBack")<br />뒤로 탐색|

### <a name="code-hierarchy-palette"></a>코드 계층 구조 팔레트

#### <a name="folder"></a>폴더

|사용법|name|값 (모든 테마)|Swatch|예제|
|-----------|----------|--------------------------|------------|-------------|
|Folders|폴더|DCB67A/220182122|![견본 DCB67A](../../extensibility/ux-guidelines/media/0405_dcb67a.png "0405_DCB67A")|![폴더 색 아이콘](../../extensibility/ux-guidelines/media/0405-23_foldercolor.png "0405 -23 _FolderColor")|

#### <a name="visual-studio-languages"></a>Visual Studio 언어
 Visual Studio에서 사용할 수 있는 각 공용 언어 또는 플랫폼에는 연결 된 색이 있습니다. 이러한 색은 기본 아이콘 또는 복합 아이콘의 오른쪽 위 모퉁이에 표시 되는 언어 한정자에 사용 됩니다.

|사용법|name|값 (모든 테마)|Swatch|
|-----------|----------|--------------------------|------------|
|ASP, HTML, WPF|ASP HTML WPF Blue|0095D/0149215|![견본 0095=](../../extensibility/ux-guidelines/media/0405_0096d7.png "0405_0096D7")|
|C++|CPP 자주|9B4F96/155, 79150|![견본 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|
|C#|CS 녹색 (VS 동작 녹색)|388A34/56138, 52|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|
|CSS|CSS 빨강|BD1E2D/189, 30, 45|![견본 BD1E2D](../../extensibility/ux-guidelines/media/0405_bd1e2d.png "0405_BD1E2D")|
|F#|FS 자주|672878/103, 40120|![견본 672878](../../extensibility/ux-guidelines/media/0405_672878.png "0405_672878")|
|JavaScript|JS 주황색|F16421/241100, 33|![견본 F16421](../../extensibility/ux-guidelines/media/0405_f16421.png "0405_F16421")|
|VB|VB Blue (VS 작업 Blue)|00539C/0, 83156|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|
|TypeScript|TS 주황색|E04C06/224, 76, 6|![견본 E04C06](../../extensibility/ux-guidelines/media/0405_e04c06.png "0405_E04C06")|
|Python|PY 녹색|879636/135150, 54|![견본 879636](../../extensibility/ux-guidelines/media/0405_879636.png "0405_879636")|

##### <a name="examples-of-icons-with-language-modifiers"></a>언어 한정자가 있는 아이콘의 예

|||||||
|-|-|-|-|-|-|
|![Visual Basic 아이콘](../../extensibility/ux-guidelines/media/0405-25_vb.png "0405 -25 _VB")<br />VB|![C&#35; 아이콘](../../extensibility/ux-guidelines/media/0405-26_csharp.png "0405 -26 _CSharp")<br />C#|![C&#43; &#43; 아이콘](../../extensibility/ux-guidelines/media/0405-27_cplusplus.png "0405-27_CPlusPlus")<br />C++|![F&#35; 아이콘](../../extensibility/ux-guidelines/media/0405-28_fsharp.png "0405-28-preview _FSharp")<br />F#|![JavaScript 아이콘](../../extensibility/ux-guidelines/media/0405-29_javascript.png "0405 -29 _JavaScript")<br />JavaScript|![Python 아이콘](../../extensibility/ux-guidelines/media/0405-30_python.png "0405 -30 _Python")<br />Python|
|![HTML 아이콘](../../extensibility/ux-guidelines/media/0405-31_html.png "0405 -31 _HTML")<br />HTML|![WPF 아이콘](../../extensibility/ux-guidelines/media/0405-32_wpf.png "0405 -32 _WPF")<br />WPF|![ASP 아이콘](../../extensibility/ux-guidelines/media/0405-33_asp.png "0405 -33 _ASP")<br />ASP|![CSS 아이콘](../../extensibility/ux-guidelines/media/0405-34_css.png "0405 -34 _CSS")<br />CSS|![TypeScript 아이콘](../../extensibility/ux-guidelines/media/0405-35_typescript.png "0405 -35 _TypeScript")<br />TypeScript||

#### <a name="intellisense"></a>IntelliSense
 IntelliSense 아이콘은 배타 색상표를 사용 합니다. 이러한 색은 사용자가 IntelliSense 팝업 목록의 여러 항목을 신속 하 게 구분할 수 있도록 하는 데 사용 됩니다.

|사용법|name|값 (모든 테마)|Swatch|
|-----------|----------|--------------------------|------------|
|클래스, 이벤트|VS 작업 주황색|C27D1A/194125, 26|![견본 C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|
|확장 메서드, 메서드, 모듈, 대리자|VS 동작 자주|652D90/101, 45144|![견본 652D90](../../extensibility/ux-guidelines/media/0405_652d90.png "0405_652D90")|
|Field, Enum Item, 매크로, 구조체, 공용 구조체 값 형식, 연산자, 인터페이스|VS 작업 Blue|00539C/0, 83156|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|
|Object|VS 동작 녹색|388A34/56138, 52|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|
|상수, 예외, 열거형 항목, 맵, 맵 항목, 네임 스페이스, 템플릿, 형식 정의|배경 (VS BG)|424242/66, 66, 66|![견본 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|

##### <a name="examples-of-intellisense-icons"></a>IntelliSense 아이콘의 예

||||||
|-|-|-|-|-|
|![IntelliSense 클래스 아이콘](../../extensibility/ux-guidelines/media/0405-36_intellisenseclass.png "0405-36_IntelliSenseClass")<br />클래스|![IntelliSense private 이벤트 아이콘](../../extensibility/ux-guidelines/media/0405-37_intellisenseprivateevent.png "0405-37_IntelliSensePrivateEvent")<br />Private 이벤트|![IntelliSense 대리자 아이콘](../../extensibility/ux-guidelines/media/0405-38_intellisensedelegate.png "0405-38_IntelliSenseDelegate")<br />대리자|![IntelliSense 메서드 friend 아이콘](../../extensibility/ux-guidelines/media/0405-39_intellisensemethodfriend.png "0405-39_IntelliSenseMethodFriend")<br />메서드 Friend|![필드 아이콘](../../extensibility/ux-guidelines/media/0405-40_field.png "0405 -40 _Field")<br />필드|
|![IntelliSense 보호 된 열거형 항목 아이콘](../../extensibility/ux-guidelines/media/0405-41_intellisenseprotectedenumitem.png "0405-41.rpm _IntelliSenseProtectedEnumItem")<br />Protected Enum 항목|![IntelliSense 개체 아이콘](../../extensibility/ux-guidelines/media/0405-42_intellisenseobject.png "0405-42_IntelliSenseObject")<br />Object|![IntelliSense 템플릿 아이콘](../../extensibility/ux-guidelines/media/0405-43_intellisensetemplate.png "0405-43_IntelliSenseTemplate")<br />템플릿|![IntelliSense 예외 바로 가기 아이콘](../../extensibility/ux-guidelines/media/0405-44_intellisenseexceptionshortcut.png "0405-44_IntelliSenseExceptionShortcut")<br />예외 바로 가기||

### <a name="notifications"></a>알림
 Visual Studio의 알림은 상태를 나타내는 데 사용 됩니다. 알림 팔레트는 다음 네 가지 색 및 검은색 또는 흰색 전경 채우기 옵션을 사용 하 여 다음 상태 수준으로 알림을 정의 합니다.

|사용법|name|값 (모든 테마)|Swatch|
|-----------|----------|--------------------------|------------|
|상태: 중립|알림 Blue (VS Blue)|1BA1E2/27161226|![견본 1BA1E2](../../extensibility/ux-guidelines/media/0405_1ba1e2.png "0405_1BA1E2")|
|상태: 긍정|알림 녹색 (VS Green)|339933/51153, 51|![견본 339933](../../extensibility/ux-guidelines/media/0405_339933.png "0405_339933")|
|상태: 음수|알림 빨강 (VS Red)|E51400/229, 20, 0|![견본 E51400](../../extensibility/ux-guidelines/media/0405_e51400.png "0405_E51400")|
|상태: 경고|알림 노랑 (VS 주황색)|FFCC00/255204, 0|![견본 FFCC00](../../extensibility/ux-guidelines/media/0405_ffcc00.png "0405_FFCC00")|
|전경 채우기|알림 검정 (검정)|000000/0, 0, 0|![견본 &#35;000000](../../extensibility/ux-guidelines/media/0405_000000.png "0405_000000")|
|전경 채우기|알림 흰색 (흰색)|FFFFFF/255255255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|

#### <a name="examples-of-notification-icons"></a>알림 아이콘의 예

|||||
|-|-|-|-|
|![경고 아이콘](../../extensibility/ux-guidelines/media/0405-45_alert.png "0405 -45 _Alert")<br />경고|![경고 아이콘](../../extensibility/ux-guidelines/media/0405-48_warning.png "0405 -48 _Warning")<br />경고|![완료 아이콘](../../extensibility/ux-guidelines/media/0405-46_complete.png "0405 -46 _Complete")<br />완료|![중지 아이콘](../../extensibility/ux-guidelines/media/0405-47_stop.png "0405 -47 _Stop")<br />Stop|

### <a name="visual-studio-online"></a>Visual Studio Online
 일반적으로 Visual Studio Online은 브라우저에서 호스팅되는 기능으로 구성 됩니다. 색은 환경 마다 다르지만 스타일은 동일 하 게 유지 됩니다.

|그룹|사용법|name|값 (모든 테마)|Swatch|
|-----------|-----------|----------|--------------------------|------------|
|TFS|배경|TFSO BG|656565/101, 101, 101|![견본 656565](../../extensibility/ux-guidelines/media/0405_656565.png "0405_656565")|
|TFS|윤곽선|TFSO OUT|FFFFFF/255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|
|Napa|배경|하얀|FFFFFF/255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|
|모나코|배경|하얀|FFFFFF/255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|
|F12|배경|하얀|FFFFFF/255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|
|F12|보통|F12 Grey_Primary|555555/85, 85, 85|![견본 555555](../../extensibility/ux-guidelines/media/0405_555555.png "0405_555555")|
|F12|가리키기|F12 Blue_Hover|2279BF/34121191|![견본 2279BF](../../extensibility/ux-guidelines/media/0405_2279bf.png "0405_2279BF")|
|F12|사용 안 함|F12 LtGrey_Disabled|ABABAC/171171172|![견본 ABABAC](../../extensibility/ux-guidelines/media/0405_ababac.png "0405_ABABAC")|
|F12|가리키기 배경|가리키기 bg|D9EBF7/217235247|![견본 D9EBF7](../../extensibility/ux-guidelines/media/0405_d9ebf7.png "0405_D9EBF7")|
|F12|누른 배경|누른 bg|B2D7F0/178215240|![견본 B2D7F0](../../extensibility/ux-guidelines/media/0405_b2d7f0.png "0405_B2D7F0")|
|F12|윤곽선|VS OUT|F6F6F6/246246246|![견본 F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")|
|F12|정보|정보|00BCF2/0188242|![견본 00BCF2](../../extensibility/ux-guidelines/media/0405_00bcf2.png "0405_00BCF2")|
|F12|경고|경고|F28300/242131, 0|![견본 F28300](../../extensibility/ux-guidelines/media/0405_f28300.png "0405_F28300")|
|F12|오류/부정|Error_Negative|E81123/232, 17, 35|![견본 E81123](../../extensibility/ux-guidelines/media/0405_e81123.png "0405_E81123")|
|F12|시작/긍정|Start_Positive|009E49/0158, 73|![견본 009E49](../../extensibility/ux-guidelines/media/0405_009e49.png "0405_009E49")|
|F12|중단 유형|중단 유형|9B4F96/155, 79150|![견본 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|
|F12|이벤트 표시|이벤트 표시|A51F00/165, 31, 0|![견본 A51F00](../../extensibility/ux-guidelines/media/0405_a51f00.png "0405_A51F00")|
|F12|사용자 표시|사용자 표시|F16220/241, 98, 32|![견본 F16220](../../extensibility/ux-guidelines/media/0405_f16220.png "0405_F16220")|

#### <a name="examples-of-visual-studio-online-icons"></a>Visual Studio Online 아이콘의 예

|TFS 온라인||||
|----------------|-|-|-|
|![TFS 온라인 팀 아이콘](../../extensibility/ux-guidelines/media/0405-49_tfsonlineteam.png "0405-49_TFSOnlineTeam")<br />온라인 팀|![TFS 정보 아이콘](../../extensibility/ux-guidelines/media/0405-50_tfsinformation.png "0405 -50 _TFSInformation")<br />정보|![TFS 기록 아이콘](../../extensibility/ux-guidelines/media/0405-51_tfshistory.png "0405-51_TFSHistory")<br />기록|![TFS 분기 아이콘](../../extensibility/ux-guidelines/media/0405-52_tfsbranch.png "0405 -52 _TFSBranch")<br />분기|

|Napa||||
|----------|-|-|-|
|![Napa 콘텐츠 아이콘](../../extensibility/ux-guidelines/media/0405-53_napacontent.png "0405-53_NapaContent")<br />콘텐츠|![Napa office 메일 아이콘](../../extensibility/ux-guidelines/media/0405-54_napaofficemail.png "0405-54_NapaOfficeMail")<br />Office 메일|![Napa SharePoint 아이콘](../../extensibility/ux-guidelines/media/0405-55_napasharepoint.png "0405-55_NapaSharePoint")<br />SharePoint|![Napa 작업 창 아이콘](../../extensibility/ux-guidelines/media/0405-56_napataskpane.png "0405-56_NapaTaskPane")<br />작업 창|

|모나코||||
|------------|-|-|-|
|![모나코 파일 아이콘](../../extensibility/ux-guidelines/media/0405-57_monacofiles.png "0405-57_MonacoFiles")<br />파일|![모나코 Git 아이콘](../../extensibility/ux-guidelines/media/0405-58_monacogit.png "0405-58_MonacoGit")<br />Git|![모나코 검색 아이콘](../../extensibility/ux-guidelines/media/0405-59_monacosearch.png "0405-59_MonacoSearch")<br />검색|![모나코 텍스트 아이콘](../../extensibility/ux-guidelines/media/0405-60_monacotext.png "0405-60_MonacoText")<br />텍스트|

|F12|||
|---------|-|-|
|![F12 예쁜 코드 아이콘](../../extensibility/ux-guidelines/media/0405-61_f12prettycode.png "0405-61_F12PrettyCode")<br />예쁜 코드|![F12 경고 아이콘](../../extensibility/ux-guidelines/media/0405-62_f12warning.png "0405 -62 _F12Warning")<br />경고|![F12 에뮬레이션 아이콘](../../extensibility/ux-guidelines/media/0405-63_f12emulate.png "0405 -63 _F12Emulate 에뮬레이트")<br />에뮬레이션|