---
title: 옵션, 텍스트 편집기, XML, 기타
ms.date: 10/29/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 58de904e1697a820a2f4bc6f88fbff5237cabc30
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72666585"
---
# <a name="options-text-editor-xml-miscellaneous"></a>옵션, 텍스트 편집기, XML, 기타

**기타** 옵션 페이지를 사용하여 XML 편집기에 대한 자동 완성 및 스키마 설정을 변경할 수 있습니다. 기타 XML 옵션에 액세스하려면 **도구** > **옵션** > **텍스트 편집기** > **XML**을 선택한 다음, **기타**를 선택합니다.

## <a name="auto-insert"></a>자동 삽입

**닫기 태그**

텍스트 편집기는 XML 요소를 작성할 때 닫기 태그를 추가합니다. 요소 시작 태그를 선택하면 편집기는 일치하는 네임스페이스 접두사를 비롯해 일치하는 닫는 태그를 삽입합니다. 이 확인란은 기본적으로 선택되어 있습니다.

**특성 따옴표**

XML 특성을 만들 때 편집기는 `="` 및 `"` 문자를 삽입하고, 큰따옴표 안에 캐럿( **^** )을 배치합니다. 이 확인란은 기본적으로 선택되어 있습니다.

**네임스페이스 선언**

편집기에서는 네임스페이스 선언이 필요한 위치에 항상 네임스페이스 선언이 자동으로 삽입됩니다. 이 확인란은 기본적으로 선택되어 있습니다.

**기타 태그(주석, CDATA)**

주석, CDATA, DOCTYPE, 처리 명령 및 기타 태그가 자동으로 완성됩니다. 이 확인란은 기본적으로 선택되어 있습니다.

## <a name="network"></a>네트워크

**DTD 및 스키마 자동 다운로드**

HTTP 위치에서 스키마 및 DTD(문서 종류 정의)가 자동으로 다운로드됩니다. 이 기능은 자동 프록시 서버 검색 기능을 설정한 상태로 System.Net을 사용합니다. 이 확인란은 기본적으로 선택되어 있습니다.

## <a name="outlining"></a>개요

**개요 모드로 파일 열기**

파일을 열 때 개요 기능을 활성화합니다. 이 확인란은 기본적으로 선택되어 있습니다.

## <a name="caching"></a>캐싱

**스키마**

스키마 캐시의 위치를 지정합니다. **찾아보기** 단추를 클릭하면 새 창에서 현재 스키마 캐시 위치를 엽니다. 기본 위치는 *%VsInstallDir%\xml\Schemas*입니다.

## <a name="see-also"></a>참고 항목

- [XML 옵션 - 서식 지정](options-text-editor-xml-formatting.md)
- [Visual Studio의 XML 도구](../../xml-tools/xml-tools-in-visual-studio.md)