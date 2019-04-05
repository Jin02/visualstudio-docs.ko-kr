---
title: VSIXLanguagePack 요소 (VSIX 언어 팩 스키마) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7b4ba4e98b8b2d42485a7594d5bab658e1bd6ccb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984005"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>VSIXLanguagePack 요소 (VSIX 언어 팩 스키마)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

필수 요소. VSIX 언어 팩에 대 한 루트 요소를 제공합니다. VSIX 언어 팩 VSIX 패키지 지역화 된 설치 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`xmlns`|VSIX 언어 팩 스키마가 정의 된 XML 네임 스페이스입니다.|  
  
## <a name="xmlns-attribute"></a>xmlns 특성  
  
|값|설명|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|필수 요소. 언어 팩에 대 한 스키마를 정의 하는 파일의 위치입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[LocalizedName 요소](../extensibility/localizedname-element-vsix-language-pack-schema.md)|필수 요소. 확장을 설치의 지역화 된 이름입니다.|  
|[LocalizedDescription 요소](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|필수 요소. 확장을 설치의 지역화 된 설명입니다.|  
|[MoreInfoURL 요소](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|선택 사항입니다. 링크 확장에 대 한 지역화 된 정보입니다.|  
|[License 요소](../extensibility/license-element-vsix-language-pack-schema.md)|선택 사항입니다. 지역화 된 버전의 확장에 대 한 라이선스 파일의 경로입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음||  
  
## <a name="element-information"></a>요소 정보  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    네임스페이스    | http://schemas.microsoft.com/developer/vsx-schema-lp/2010 |
|   스키마 이름   |                 VSIX 언어 팩 스키마                 |
| 유효성 검사 파일 |                VSIXLanguagePackSchema.xsd                 |
|  비워 둘 수 있습니다.   |                            아니요                             |
  
## <a name="see-also"></a>참고 항목  
 [VSX 언어 팩 스키마 참조](../extensibility/vsx-language-pack-schema-reference.md)   
 [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)   
 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
