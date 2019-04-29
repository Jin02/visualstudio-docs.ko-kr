---
title: IDSymbol 요소 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 39ef9d059353f143c80e8956fa14f1812dc90859
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861852"
---
# <a name="idsymbol-element"></a>IDSymbol 요소
`IDSymbol` 요소 메뉴, 그룹 또는 명령을 나타내는 guid: id 쌍의 ID를 포함 합니다. 부모에서 가져온 GUID `GuidSymbol` 요소입니다. `IDSymbol` 요소에는 `name` 특성에 포함 되어 있는 ID에 대 한 친숙 한 이름을 지정 하는 `value` 특성.

## <a name="syntax"></a>구문

```xml
<IDSymbol name=ElementName value="0x0010" />
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|name|필수 요소. 이름 ID 기호입니다.|
|값|필수 요소. ID 기호의 숫자 ID 값입니다.|

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[GuidSymbol 요소](../extensibility/guidsymbol-element.md)|메뉴, 그룹 또는 명령을 나타내는 guid: id 쌍의 GUID를 포함 합니다. `IDSymbol` 요소를 그룹화합니다.|

## <a name="remarks"></a>설명
 모든 `IDSymbol` 요소에는 주어진 `GuidSymbol` 요소는 고유 해야 합니다. `value`합니다. 그러나 `IDSymbol` 으로 부모가 서로 다른 패키지에 동일한 값을 가진 요소가 있을 수 있습니다.

## <a name="see-also"></a>참고자료
- [Visual Studio 명령 테이블 (.vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)