---
title: CommandPlacements 요소 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CommandPlacements
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 78a5724a-3b9f-4c78-9c0d-8faa3924f81c
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dbe65cc38bd14d859507d795ce32657f53ca8b44
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184305"
---
# <a name="commandplacements-element"></a>CommandPlacements 요소
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

CommandPlacements 요소 그룹 CommandPlacement 요소 및 기타 CommandPlacements 그룹화 합니다.  
  
 CommandPlacements 요소는 선택 사항입니다. 없는 명령, 그룹 또는 메뉴를 보조 위치에 포함 되어야 합니다,.vsct 파일의이 섹션을 포함할 필요가 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<CommandPlacements>  
  <CommandPlacement>... </CommandPlacement>  
  <CommandPlacement>... </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|CommandPlacements|CommandPlacement 요소를 그룹화 하 고 기타 CommandPlacements 그룹화 합니다.|  
|[CommandPlacement 요소](../extensibility/commandplacement-element.md)|단추, 그룹 및 메뉴 둘 이상의 그룹 또는 메뉴에 포함 될 수 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|명령을 나타내는 모든 요소를 정의 합니다.|  
  
## <a name="example"></a>예제  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>참고 항목  
 [CommandPlacement 요소](../extensibility/commandplacement-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
