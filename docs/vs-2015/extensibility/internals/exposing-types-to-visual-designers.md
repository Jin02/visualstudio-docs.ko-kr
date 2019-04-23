---
title: 비주얼 디자이너에 형식 노출 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a50b298dfafe093e404c6575b16a074d106522ee
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60103435"
---
# <a name="exposing-types-to-visual-designers"></a>비주얼 디자이너에 형식 노출
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 비주얼 디자이너를 표시 하려면 디자인 타임에 클래스 및 형식 정의에 대 한 액세스를 있어야 합니다. 클래스는 미리 정의 된 집합 (참조 및 해당 종속성)은 현재 프로젝트의 전체 종속성 집합을 포함 하는 어셈블리에서에서 로드 됩니다. 비주얼 디자이너에 대 한 액세스 클래스 및 사용자 지정 도구에서 생성 된 파일에 정의 된 형식에 필요한 수도 있습니다.  
  
 합니다 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] 고 [!INCLUDE[csprcs](../../includes/csprcs-md.md)] 프로젝트 시스템 임시 노트북을 통해 생성 된 클래스 및 형식에 액세스 하기 위한 지원을 제공 실행 파일 (임시 Pe). 사용자 지정 도구에서 생성 된 모든 파일 형식을 해당 어셈블리에서 로드 되 고 디자이너에 노출 수 있도록 임시 어셈블리로 컴파일할 수 있습니다. 각 사용자 지정 도구의 출력을 별도 임시 PE로 컴파일되고만 생성 된 파일을 컴파일할 수 있는 여부에 따라 달라 집니다이 임시 컴파일 성공 여부. 프로젝트를 전체적으로 빌드되지 않을 수 있지만 개별 임시 Pe 디자이너에 사용할 수 있습니다.  
  
 프로젝트 시스템 이러한 변경은 사용자 지정 도구를 실행 한 결과 사용자 지정 도구의 출력 파일의 변경 내용 추적에 대 한 전체 지원을 제공 합니다. 사용자 지정 도구를 실행할 때마다 새 임시 PE 생성 하 고 적절 한 알림을 디자이너에 전송 됩니다.  
  
> [!NOTE]
>  임시 프로그램 실행 파일 생성 파일 백그라운드에서 발생 하기 때문에 오류 없이 컴파일이 실패 하는 경우 사용자에 게 보고 됩니다.  
  
 임시 PE 지원 기능을 활용 하는 사용자 지정 도구는 다음 규칙을 따라야 합니다.  
  
- `GeneratesDesignTimeSource` 레지스트리에서 1로 설정 되어야 합니다.  
  
     프로그램 실행 파일 컴파일 안 함이 설정이 없으면 이루어집니다.  
  
- 생성된 된 코드는 전역 프로젝트 설정과 동일한 언어에서 여야 합니다.  
  
     요청 된 확장으로 사용자 지정 도구가 보고 하는 항목에 관계 없이 임시 PE 컴파일됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> 제공한 `GeneratesDesignTimeSource` 레지스트리에서 1로 설정 됩니다. 확장명은.vb에서.cs 또는.jsl; 될 필요가 없습니다. 모든 확장 수 있습니다.  
  
- 사용자 지정 도구에서 생성 한 코드는 유효 해야 하 고 자체를 사용 하 여 프로젝트에 있는 참조의 집합만 시에 컴파일해야 하 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 실행을 완료 합니다.  
  
     임시 PE 컴파일시 컴파일러에 제공 된 유일한 소스 파일은 사용자 지정 도구 출력. 따라서 임시 PE를 사용 하는 사용자 지정 도구는 프로젝트의 다른 파일로 독립적으로 컴파일할 수 있는 출력 파일을 생성 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BuildManager 개체 소개](http://msdn.microsoft.com/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [단일 파일 생성기 구현](../../extensibility/internals/implementing-single-file-generators.md)   
 [프로젝트의 기본 Namespace를 결정합니다.](../../misc/determining-the-default-namespace-of-a-project.md)   
 [단일 파일 생성기 등록](../../extensibility/internals/registering-single-file-generators.md)
