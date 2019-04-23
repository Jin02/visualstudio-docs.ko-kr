---
title: '연습: 사용자 지정 편집기 만들기 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f85963712fa1b051ea7256e6f805fe8e7c7e70d0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056552"
---
# <a name="walkthrough-create-a-custom-editor"></a>연습: 사용자 지정 편집기 만들기
VSPackage 프로젝트 템플릿은에서 간단한 사용자 지정 편집기를 만들 수 있습니다 C++입니다. VSPackage 프로젝트 템플릿은 C# 또는 Visual Basic 프로젝트를 더 이상 지원합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.

## <a name="prerequisites"></a>전제 조건
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.

## <a name="the-visual-studio-package-project-template"></a>Visual Studio 패키지 프로젝트 템플릿
 Visual Studio 패키지 프로젝트 템플릿을 찾을 수 있습니다 합니다 **새 프로젝트** 대화 상자의 합니다  **C++ 확장성** 폴더입니다.

### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Visual Studio 패키지 템플릿을 사용 하 여 VSPackage를 만들려면

1. Visual Studio 패키지 템플릿을 사용 하 여 프로젝트를 만듭니다.

2. 선택 된 **사용자 지정 편집기** 옵션을 클릭 **다음**합니다. 합니다 **편집기 옵션** 페이지가 나타납니다.

3. 편집기의 이름을 입력 합니다 **편집기 이름을** 상자입니다. 편집기를 사용 하 여 연결 하려는 파일 확장명을 입력 합니다 **파일 확장명** 상자입니다. 편집기는이 확장을 사용 하 여 파일 수 있습니다. 파일 확장명은 Windows에만 Visual Studio에 등록 됩니다. 편집기를 사용 하 여 만든 새 문서에 대 한 기본 파일 이름을 입력 합니다 **기본 파일 이름은** 상자입니다.

4. 지정한 폴더에 VSPackage를 만들려면 **마침** 을 클릭합니다.

### <a name="to-test-your-custom-editor"></a>사용자 지정 편집기를 테스트 하려면

1. 에 **파일** 메뉴에서 **새로 만들기** 을 클릭 한 다음 **파일**합니다.

2. 에 **설치 된 템플릿** 창의 **새 파일** 대화 상자에서 파일 템플릿을 다음 파일 형식에 등록 합니다.

3. 클릭 **열고** 를 보고 문서를 편집 합니다.

     편집기는 잘라내기 및 붙여넣기, 찾기 및 바꾸기, 및 오픈 로드 작업을 지원합니다.

## <a name="see-also"></a>참고자료
- [VSPackage](../extensibility/internals/vspackages.md)