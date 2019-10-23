---
title: RegPkg 패키지 등록 문제 해결 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 386a1a17c036207d122e4b3c7cb142a628dcfe38
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722272"
---
# <a name="troubleshooting-regpkg-package-registration"></a>RegPkg 패키지 등록 문제 해결
> [!NOTE]
> Visual Studio에서 패키지를 등록 하는 기본 방법은. .pkgdef 파일을 사용 하는 것입니다. 이렇게 하면 시스템 레지스트리에 액세스할 필요 없이 확장 배포를 수행할 수 있습니다. .Pkgdef 파일은 [Createpkgdef 유틸리티](../../extensibility/internals/createpkgdef-utility.md)를 사용 하 여 만듭니다.

 @No__t_0에서 RegPkg를 사용 하 여 패키지를 등록 하려면 패키지에 적절 한 RegPkg 버전을 사용 해야 합니다.

## <a name="regpkg-versions-related-to-package-versions"></a>패키지 버전과 관련 된 RegPkg 버전
 RegPkg에는 두 가지 버전이 있습니다. @No__t_0에는 하나의 버전이 포함 되어 있습니다. 이 버전을 사용 하 여 다음 어셈블리 중 하나를 사용 하 여 빌드된 패키지를 등록 합니다.

1. VisualStudioShell.

2. VisualStudioShell.

3. VisualStudioShell.

   이전 VisualStudio 어셈블리를 사용 하 여 빌드된 패키지는 등록할 수 없습니다.

   이전 버전의 RegPkg는 VisualStudio 어셈블리를 사용 하 여 빌드된 패키지를 등록할 수 있습니다. 그러나 해당 어셈블리의 이후 버전을 사용 하 여 작성 된 패키지는 등록할 수 없습니다.

## <a name="see-also"></a>참조
- [VSPackage](../../extensibility/internals/vspackages.md)