---
title: XML 편집기에서 XML 문서 유효성 검사
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59b8ed5c74d998b47ff4a187b420695eab5be035
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807723"
---
# <a name="xml-document-validation"></a>XML 문서 유효성 검사

XML 편집기 XML 1.0 구문을 확인 하 고도 입력할 때 데이터 유효성 검사를 수행 합니다. 이 편집기에서는 DTD(문서 종류 정의) 또는 스키마를 사용하여 유효성을 검사할 수 있습니다. XML 1.0 올바른 형식의 오류가 빨간색 물결 무늬 밑줄로 강조되며 DTD 또는 스키마 유효성 검사를 기준으로 의미 오류가 파란색 물결 무늬 밑줄로 강조됩니다. 각 오류에는 오류 목록에서 연결된 항목이 있습니다. 물결 무늬 밑줄 위에서 마우스를 멈추면 오류 메시지를 볼 수 있습니다.

 컴파일된 스키마의 `targetNamespace`와 요소의 xmlns 선언을 비교하여 유효성 검사에 사용된 스키마를 찾을 수 있습니다. 우선 순위에 따라 나열된 다음 위치 중 하나에서 컴파일된 스키마가 로드됩니다.

- 지정 된 파일 이름을 사용 합니다 **스키마** 문서의 필드 **속성** 창입니다.

- 인라인 스키마 또는 DTD

- 외부 DTD 또는 `xsd:schemaLocation` 및 `xsd:noNamespaceSchemaLocation` 특성

- "x 스키마" XDR 스키마 네임스페이스 URI

스키마에 비어 있지 않은 대상 네임스페이스가 있을 경우 다음 추가 위치에서 스키마를 찾을 수도 있습니다.

- 스키마가 포함된 다른 편집기 창

- 현재 솔루션의 스키마

- 스키마 캐시 디렉터리의 스키마

## <a name="xslt-files"></a>XSLT 파일
 XSLT 파일을 편집 하는 경우는 *xslt.xsd* 스키마 캐시에 있는 파일 유효성 검사가 사용 됩니다. 유효성 검사 오류는 파란색 물결 무늬 밑줄로 표시되고 XSLT 컴파일러 오류는 빨간색 물결 무늬 밑줄로 표시됩니다.

## <a name="xml-schema-xsd-files"></a>XML 스키마 (XSD) 파일
 XML 스키마 파일을 편집 하는 경우는 *xsdschema.xsd* 스키마 캐시에 있는 파일 유효성 검사가 사용 됩니다. 유효성 검사 오류는 파란색 물결 무늬 밑줄로 표시되고 컴파일 오류는 빨간색 물결 무늬 밑줄로 표시됩니다.

## <a name="see-also"></a>참고자료

- [XML 편집기](../xml-tools/xml-editor.md)