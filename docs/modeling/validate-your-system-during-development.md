---
title: 개발하는 동안 시스템 유효성 검사
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 328b600a21adf274d1d016f595438eb5622ee853
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663742"
---
# <a name="validate-your-system-during-development"></a>개발하는 동안 시스템 유효성 검사

Visual Studio를 사용 하면 사용자 요구 사항과 시스템 아키텍처에 맞게 소프트웨어를 일관 되 게 유지할 수 있습니다.

이러한 각 기능을 지원하는 Visual Studio의 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)를 참조하세요.

## <a name="key-tasks"></a>주요 작업

다음 작업을 사용 하 여 소프트웨어의 유효성을 검사 합니다.

|**태스크**|**관련 항목**|
|-|-|
|**소프트웨어가 사용자 요구 사항을 충족하는지 확인합니다**.<br /><br />시스템 및 해당 구성 요소의 테스트를 구성 하는 데 도움이 되는 요구 사항 및 아키텍처 모델을 사용 합니다. 이렇게 하면 사용자 및 기타 이해 관계자에게 중요한 요구 사항을 테스트하는지 확인할 수 있고 요구 사항이 변경될 때 테스트를 빠르게 업데이트할 수 있습니다.|[모델에서 테스트 개발](../modeling/develop-tests-from-a-model.md) - |
|**소프트웨어와 의도한 시스템 디자인의 일관성이 유지되는지 확인합니다.**<br /><br />종속성 다이어그램은 응용 프로그램 구성 요소 간의 의도 한 종속성을 설명 합니다. 개발하는 동안 코드의 실제 종속성이 의도한 디자인을 따르는지 확인할 수 있습니다.|- [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />[종속성 다이어그램을 사용 하 여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md) - |

## <a name="external-resources"></a>외부 리소스

|**범주**|**Links**|
|-|-|
|**비디오**|비디오 ](../data-tools/media/playvideo.gif) [Channel 9: Doug 7: Visual Studio 2010을 사용 하 여 코드 이해 및 시스템 디자인](https://channel9.msdn.com/shows/VS2010Launch/Doug-Seven-Code-Understanding-and-Systems-Design-with-Visual-Studio-2010) 에 ![link<br /><br /> 비디오 ](../data-tools/media/playvideo.gif)에 ![link [Channel 9: 응용 프로그램 설계](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-5-architecting-an-application))|
|**포럼**|- [Visual Studio 시각화 및 모델링 도구](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />- [Visual Studio 확장성](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)|

## <a name="see-also"></a>참조

- [사용자 요구 사항 모델링](../modeling/model-user-requirements.md)
- [분석 및 모델 아키텍처](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
