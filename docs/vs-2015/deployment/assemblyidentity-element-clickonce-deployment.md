---
title: '&lt;assemblyIdentity&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce deployment manifest]
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bfc2ff97a2eb465fe7306ebe368a20e2a7fd8638
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58983349"
---
# <a name="ltassemblyidentitygt-element-clickonce-deployment"></a>&lt;assemblyIdentity&gt; 요소 (ClickOnce 배포)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

주 어셈블리를 식별 하는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 응용 프로그램입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `assemblyIdentity` 요소는 필수입니다. 자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 요소. 배포의 알기 쉬운 이름 확인용으로 식별합니다.<br /><br /> 경우 `name` 특수 문자가 포함 된 작은따옴표 또는 큰따옴표와 같은 응용 프로그램 활성화에 실패할 수 있습니다.|  
|`version`|필수 요소. 다음 형식으로 어셈블리의 버전 번호를 지정 합니다. `major.minor.build.revision`합니다.<br /><br /> 이 값을 응용 프로그램 업데이트를 트리거하는 업데이트 된 매니페스트에서 증가 해야 합니다.|  
|`publicKeyToken`|필수 요소. 배포 매니페스트 서명에 사용 된 공개 키의 sha-1 해시 값의 마지막 8 바이트를 나타내는 16 자리의 16 진수 문자열을 지정 합니다. 로그인 하는 데 사용 되는 공개 키 2048 비트 해야 합니다. 이상.<br /><br /> 어셈블리를 서명 하는 것이 좋지만 선택 사항, 있지만이 특성은 필수입니다. 어셈블리 서명 되어 있지 않으면 자체 서명 된 어셈블리에서 값을 복사 하거나 "더미" 모두 0 값을 사용 해야 합니다.|  
|`processorArchitecture`|필수 요소. 프로세서를 지정합니다. 유효한 값은 `msil` 모든 프로세서에 대해 `x86` 32 비트 Windows에 대 한 `IA64` 64 비트 Windows에 대 한 및 `Itanium` Intel 64 비트 Itanium 프로세서에 대 한 합니다.|  
|`type`|필수 요소. Windows side-by-side-설치 기술 사용 하 여 비교 합니다. 허용 된 값만 `win32`합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `assemblyIdentity` 요소에는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 배포 매니페스트 합니다. 이 코드 예제는에 대해 제공 된 큰 예제의 일부 합니다 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 항목입니다.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity> 요소](../deployment/assemblyidentity-element-clickonce-application.md)
