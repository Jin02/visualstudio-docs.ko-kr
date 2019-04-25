---
title: 옵션 페이지, 글꼴 및 색 노드 속성
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5363d71082128c13146c445fe312424be7e4340
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945596"
---
# <a name="options-page-fonts-and-colors-node-properties"></a>옵션 페이지, 글꼴 및 색 노드 속성
이 문서에서는 **옵션** 대화 상자의 **환경** 범주에 있는 **글꼴 및 색** 범주 아래에 표시되도록 등록된 도구 창의 글꼴 및 색 속성을 설명합니다. 이는 VSPackage가 설치 또는 제거될 경우 변경할 수 있는 색 항목 그룹의 동적 특성을 지원합니다.

 다음 섹션에서는 등록된 창 형식의 예제와 각 창에 사용할 수 있는 속성을 보여 줍니다.

## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>텍스트 편집기 또는 프린터 또는 대화 상자 및 도구 창
 `DTE.Properties("FontsAndColors", "TextEditor")`

 또는

 `DTE.Properties("FontsAndColors", "Printer")`

 또는

 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`

|속성 항목 이름|값|설명|
| - |-----------|-----------------|
|FontFamily|Get/Set(문자열)|사용할 글꼴 이름(예: "Courier New").|
|FontCharacterSet|Get/Set (<xref:EnvDTE.vsFontCharSet>)|사용할 문자 집합의 형식을 지정하는 <xref:EnvDTE.vsFontCharSet> 값(예: 히브리어 또는 러시아어)입니다.|
|FontSize|Get/Set(Short)|사용할 글꼴 크기(포인트). 예: 10 또는 12.|

## <a name="see-also"></a>참고 항목

- [옵션 설정 제어](https://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)
- [옵션 페이지에서 속성 항목의 이름 확인](https://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)
- [옵션 페이지, 환경, 노드 속성](../../ide/reference/options-page-environment-node-properties.md)
- [옵션 페이지, 텍스트 편집기 노드 속성](../../ide/reference/options-page-text-editor-node-properties.md)