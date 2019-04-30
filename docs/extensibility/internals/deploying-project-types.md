---
title: 프로젝트 형식 배포 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e89f74d940182cd92fd15f726676f0979d21186
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861362"
---
# <a name="deploy-project-types"></a>프로젝트 형식 배포
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 새 프로젝트 형식 aggregator를 설치 (*ProjectAggregator2.dll*) 및 Windows Installer 패키지를 재배포에 대 한도 (*ProjectAggregator2.msi*). 관리 코드 프로젝트 형식에 대해 새 집계가 사용 해야 합니다. 제한 사항을 위반 ProjectAggregator2 작동을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aggregator 관리 코드 프로젝트 형식을 올바르게 작동 하지 못하도록 하는 프로젝트입니다. 다음 단계를 새 집계를 사용 하 여 VSPackage를 변경 하는 방법에 설명 합니다.

1. 솔루션에서 NativeHierarchyWrapper 프로젝트를 제거 합니다.

2. 설치 프로그램에서 NativeHierarchyWrapper 이진 파일을 제거 합니다.

3. 추가 *ProjectAggregator2.msi* 에 설치 합니다.