---
title: CommandTable 요소 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bb2b874f7bbe94e383e9e7fba755dcc373a93150
ms.sourcegitcommit: 374f5ec9a5fa18a6d4533fa2b797aa211f186755
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77477043"
---
# <a name="commandtable-element"></a>CommandTable 요소
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

CommandTable은 vsct 파일의 루트 요소입니다. 이 파일은 VSPackage에서 IDE에 제공 하는 명령의 실제 레이아웃 및 형식을 정의 하는 파일입니다. 명령에는 메뉴 항목, 메뉴, 도구 모음, 콤보 상자 등이 포함 될 수 있습니다. 자세한 내용은 [Visual Studio Command Table (.Vsct) Files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```xml  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >  
  <Extern>... </Extern>  
  <Include>... </Include>  
  <Define>... </Define>  
  <Commands>... </Commands>  
  <CommandPlacements>... </CommandPlacements>  
  <VisibilityConstraints>... </VisibilityConstraints>  
  <KeyBindings>... </KeyBindings>  
  <UsedCommands... </UsedCommands>  
  <Symbols>... </Symbols>  
</CommandTable>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
| 특성 |                                                                                                                   설명                                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   xmlns   |                                   필수입니다. XML 네임 스페이스:<br /><br /> `xmlns="<http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable>"`<br /><br /> `xmlns:xs="<http://www.w3.org/2001/XMLSchema>"`                                   |
| language  | (선택 사항) Language 특성은 명령 테이블의 모든 \<문자열 > 요소에 대 한 기본 언어를 지정 하는 데 사용할 수 있습니다.  언어가 지정 되지 않은 경우 현재 프로세스의 언어가 사용 됩니다.<br /><br /> language="en-us" |
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Extern 요소](../extensibility/extern-element.md)|(선택 사항) 컴파일러에 대 한 전처리기 지시문을 포함 합니다.|  
|[Include 요소](../extensibility/include-element.md)|(선택 사항) 컴파일에 포함할 파일에 대 한 경로를 포함 합니다.|  
|[Define 요소](../extensibility/define-element.md)|(선택 사항) 지정 된 이름 및 값을 지정 하 여 기호를 정의 합니다.|  
|[Commands 요소](../extensibility/commands-element.md)|(선택 사항) 다른 모든 요소를 포함 하는 VSPackage에 대 한 모든 명령을 정의 하는 부모 요소입니다.|  
|[CommandPlacements 요소](../extensibility/commandplacements-element.md)|(선택 사항) 명령 모음에서 명령을 배치할 위치를 정의 합니다.|  
|[VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)|(선택 사항) 명령 및 도구 모음의 정적 표시 여부를 결정 합니다.|  
|[KeyBindings 요소](../extensibility/keybindings-element.md)|(선택 사항) 명령에 대 한 바로 가기 키 조합 (있는 경우)을 지정 합니다.|  
|[UsedCommands 요소](../extensibility/usedcommands-element.md)|(선택 사항) VSPackage이 다른 Vspackage에서 원래 지 원하는 고유한 기능 버전을 선택적으로 구현할 수 있습니다.|  
|[Symbols 요소](https://msdn.microsoft.com/f2ddd0aa-c3dd-439e-834d-28f136a27ffa)|(선택 사항) 컴파일러에 대 한 기호 데이터 (Guid, Id 등)를 포함 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음||  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
