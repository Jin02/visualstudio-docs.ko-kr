---
title: LocalizedDescription 요소 (VSIX 언어 팩 스키마) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 766a1732-bbaf-4875-b276-feb42169633a
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9e626e532c462199d38ddb3f1044bab25d389995
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62568953"
---
# <a name="localizeddescription-element-vsix-language-pack-schema"></a>LocalizedDescription 요소 (VSIX 언어 팩 스키마)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

필수 요소. 확장 프로그램의 지역화 된 설명을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<LocalizedDescription>Localized description of the extension</LocalizedDescription>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|없음||  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[VSIX LanguagePack 요소](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|필수 요소. VSIX 언어 팩에 대 한 루트 요소를 제공합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 필수 요소. 대상 언어에서 확장의 텍스트 설명입니다.  
  
## <a name="element-information"></a>요소 정보  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    네임스페이스    | http://schemas.microsoft.com/developer/vsx-schema-lp/2010 |
|   스키마 이름   |                 VSIX 언어 팩 스키마                 |
| 유효성 검사 파일 |                VSIXLanguagePackSchema.xsd                 |
|  비워 둘 수 있습니다.   |                      적용할 수 없음                       |
  
## <a name="see-also"></a>참고 항목  
 [VSX 언어 팩 스키마 참조](../extensibility/vsx-language-pack-schema-reference.md)   
 [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)   
 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
