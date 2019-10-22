---
title: XML 스키마
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.xmleditor.schemasdialog
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11743756ffd8f59520448d2687dbada6d4eaca40
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72608044"
---
# <a name="xml-schemas-dialog-box"></a>XML 스키마 대화 상자

Xml **스키마** 대화 상자는 xml 문서와 연결할 XSD (xml 스키마 정의 언어) 스키마를 선택 하는 데 사용 됩니다. 스키마 캐시에서 스키마를 선택하거나 캐시에 없는 스키마를 지정할 수 있습니다. 선택한 스키마는 스키마 집합의 일부분으로 간주됩니다. 스키마 집합은 IntelliSense 및 XML 문서 유효성 검사에 사용됩니다.

**Xml 스키마** 대화 상자는 문서 속성 창에서 **스키마** 단추를 클릭 하거나 **xml** 메뉴에서 **스키마** 를 선택 하 여 액세스할 수 있습니다.

## <a name="uielement-list"></a>UI 요소 목록

**사용**

XML 스키마를 사용할 방법을 선택합니다.

- **자동**. 이 스키마는 현재 문서에서는 사용되지 않지만 자동 연결에 사용할 수 있습니다. XML 문서가 이 스키마의 `targetNamespace`와 일치하는 네임스페이스를 선언하는 경우 해당 스키마가 자동으로 연결되고 스키마 집합에 포함됩니다.

- **이 스키마를 사용**합니다. 이 스키마를 현재 문서에서 사용하고 있습니다. 사용자가 이 열에서 이 스키마를 클릭하여 사용하도록 명시적으로 요청했거나, 스키마가 일치하는 `targetNamespace`를 기반으로 하여 자동으로 연결되었습니다.

- **선택한 스키마를 사용 하지 마십시오**. 이 스키마는 일치하는 `targetNamespace`가 있는 경우에도 현재 문서에서 사용되지 않습니다. 이 설정은 스키마 캐시 또는 솔루션에 동일한 스키마의 둘 이상의 버전이 있을 때 충돌을 해결하는 데 유용합니다.

**대상 네임 스페이스**

XML 스키마와 연결된 대상 네임스페이스를 표시합니다.

**파일 이름**

XML 스키마 파일 이름을 표시합니다.

**추가**

스키마 집합에 추가할 추가 스키마를 선택할 수 있는 **XSD 스키마 열기** 대화 상자를 엽니다. 스키마 집합에 스키마를 추가 하는 경우 열 **사용** 값 **이이 스키마를 사용**하도록 설정 됩니다.

**제거**

현재 선택된 스키마를 스키마 집합에서 제거합니다. 그러면 스키마가 메모리 내 스키마 캐시에서 제거되지만 파일 시스템에서는 제거되지 않습니다.

## <a name="see-also"></a>참조

- [방법: 사용할 XML 스키마 선택](../xml-tools/how-to-select-the-xml-schemas-to-use.md)
- [스키마 캐시](../xml-tools/schema-cache.md)