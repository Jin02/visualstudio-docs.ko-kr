---
title: FeatureProperties 요소 | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperties element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6860a91067daa6da1d4223ae5060385087ad3433
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967333"
---
# <a name="featureproperties-element"></a>FeatureProperties 요소
  SharePoint에 배포 될 때 기능을 사용 하 여 포함 된 속성 값의 컬렉션입니다. 기능이 배포 된 후에 코드에서 속성 값을 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```xml
<FeatureProperties>
  <FeatureProperty.../>
</FeatureProperties>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성
 없음

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[FeatureProperty](../sharepoint/featureproperty-element.md)|선택적 요소입니다.<br /><br /> 키/값 형식으로 사용자 지정 속성을 나타냅니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint 프로젝트 항목을 나타냅니다. 이 요소는 필수 루트 요소에는 `.spdata` 파일.|

## <a name="remarks"></a>설명
 기능 속성에 대 한 자세한 내용은 참조 하세요. [프로젝트 항목에 패키징 및 배포 정보를 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다.

## <a name="element-information"></a>요소 정보

|요소|설명|
|-------------|-----------------|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|
|**비어 있을 수 있습니다.**|아니요|

## <a name="see-also"></a>참고자료
- [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)
- [프로젝트 항목에 패키징 및 배포 정보를 제공 합니다.](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
