---
title: 프로젝트 디자이너, 빌드 이벤트 페이지(C#)
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba429c116d44a5d79d935fe3a1ad07b6d5f36f79
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461848"
---
# <a name="build-events-page-project-designer-c"></a>프로젝트 디자이너, 빌드 이벤트 페이지(C#)

**프로젝트 디자이너**의 **빌드 이벤트** 페이지를 사용하여 빌드 구성 지침을 지정합니다. 또한 빌드 후 이벤트를 실행할 조건을 지정할 수 있습니다. 자세한 내용은 [방법: 빌드 이벤트 지정(C#)](../../ide/how-to-specify-build-events-csharp.md) 및 [방법: 빌드 이벤트 지정(Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)을 참조하세요.

## <a name="uielement-list"></a>UI 요소 목록

**구성**

이 컨트롤은 이 페이지에서 편집할 수 없습니다. 이 컨트롤에 대한 설명은 [프로젝트 디자이너, 빌드 페이지(C#)](../../ide/reference/build-page-project-designer-csharp.md)를 참조하세요.

**플랫폼**

이 컨트롤은 이 페이지에서 편집할 수 없습니다. 이 컨트롤에 대한 설명은 [프로젝트 디자이너, 빌드 페이지(C#)](../../ide/reference/build-page-project-designer-csharp.md)를 참조하세요.

**빌드 전 이벤트 명령줄**

빌드를 시작하기 전에 실행할 명령을 지정합니다. 긴 명령을 입력하려면 **빌드 전 편집**을 클릭하여 [빌드 전 이벤트/빌드 후 이벤트 명령줄](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md) 대화 상자를 표시합니다.

> [!NOTE]
> 프로젝트가 최신 상태이고 빌드가 트리거되지 않으면 빌드 전 이벤트가 실행되지 않습니다.

**빌드 후 이벤트 명령줄**

빌드가 끝난 후 실행할 명령을 지정합니다. 긴 명령을 입력하려면 **빌드 후 편집**을 클릭하여 **빌드 전 이벤트/빌드 후 이벤트 명령줄** 대화 상자를 표시합니다.

> [!NOTE]
> .bat 파일을 실행하는 모든 빌드 후 이벤트 명령 앞에 `call` 문을 추가합니다. 예를 들어 `call C:\MyFile.bat` 또는 `call C:\MyFile.bat call C:\MyFile2.bat`로 이름을 지정할 수 있습니다.

**빌드 후 이벤트 실행**

다음 표에 나와 있는 것처럼 실행할 빌드 후 이벤트에 대한 다음 조건을 지정합니다.

|옵션|결과|
|------------|------------|
|**항상**|빌드의 성공 여부에 관계 없이 빌드 후 이벤트가 실행됩니다.|
|**빌드가 성공한 경우**|빌드에 성공하면 빌드 후 이벤트가 실행됩니다. 따라서 이벤트는 빌드가 성공하는 한 최신 프로젝트에도 실행됩니다.|
|**빌드에서 프로젝트 출력을 업데이트한 경우**|컴파일러의 출력 파일(.exe 또는.dll)이 이전 컴파일러 출력 파일과 다른 경우에만 빌드 후 이벤트가 실행됩니다. 따라서 프로젝트가 최신 상태이면 빌드 후 이벤트가 실행되지 않습니다.|

## <a name="see-also"></a>참고 항목

- [방법: 빌드 이벤트 지정(Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [방법: 빌드 이벤트 지정(C#)](../../ide/how-to-specify-build-events-csharp.md)
- [프로젝트 속성 참조](../../ide/reference/project-properties-reference.md)
- [컴파일 및 빌드](../../ide/compiling-and-building-in-visual-studio.md)