---
title: 파일을 복사할 위치를 지정 합니다. | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec54a2d3150b0e8e11b19d2ca739324d7388f1f0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63407647"
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>방법: Visual Studio의 파일 복사 위치 지정
ClickOnce를 사용하여 응용 프로그램을 게시하는 경우 `Publish Location` 속성에서 응용 프로그램 파일 및 매니페스트가 배치되는 위치를 지정합니다. 이 위치는 파일 경로나 FTP 서버에 대한 경로가 될 수 있습니다.

 `Publish Location` 속성은 **프로젝트 디자이너**의 **게시** 페이지나 게시 마법사를 사용하여 지정할 수 있습니다. 자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)를 참조하세요.

> [!NOTE]
> ClickOnce를 사용하여 애플리케이션 버전을 둘 이상 설치하면 이전 애플리케이션 버전이 지정한 게시 위치의 Archive 폴더로 이동합니다. 이러한 방식으로 이전 버전이 보관되므로 설치 디렉터리에 이전 버전의 폴더가 남지 않습니다.

### <a name="to-specify-a-publishing-location"></a>게시 위치를 지정하려면

1. **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **게시** 탭을 클릭합니다.

3. **게시 위치** 필드에 다음 형식 중 하나를 사용하여 게시 위치를 입력합니다.

   - 파일 공유나 디스크 경로에 게시하려면 UNC 경로(*\\\Server\ApplicationName*)나 파일 경로(*C:\Deploy\ApplicationName*)를 사용하여 경로를 입력합니다.

   - FTP 서버에 게시하려면 <em>ftp://ftp.microsoft.com/\<ApplicationName></em> 서식을 사용하여 경로를 입력합니다.

     찾아보기(**...**) 단추가 작동하려면 **게시 위치** 상자에 텍스트가 있어야 합니다.

## <a name="see-also"></a>참고자료
- [ClickOnce 애플리케이션 게시](../deployment/publishing-clickonce-applications.md)
- [방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)