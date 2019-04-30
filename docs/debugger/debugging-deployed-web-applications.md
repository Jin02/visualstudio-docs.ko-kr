---
title: 배포 된 ASP.NET 응용 프로그램 디버그 | Microsoft Docs
ms.date: 06/30/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET Web applications
- Web services, debugging
- XML, debugging Web services
- debugging Web services
- ASP.NET, debugging Web applications
- XML Web services, debugging
ms.assetid: b938a91b-be96-416f-83bc-4177e7f3929a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: f911cafb8ee0bdd341ce13c6eb38423ae4d3f473
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399363"
---
# <a name="debugging-deployed-aspnet-applications"></a>배포 된 ASP.NET 응용 프로그램 디버깅
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 배포된 응용 프로그램을 디버깅하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스에 연결하고 디버거에서 해당 응용 프로그램에 대한 기호에 액세스할 수 있는지 확인해야 합니다. 또한 해당 응용 프로그램의 소스 파일도 찾아서 열어야 합니다. 자세한 내용은 [지정할 기호 (.pdb) 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md), [방법: ASP.NET 프로세스의 이름을 찾으려면](../debugger/how-to-find-the-name-of-the-aspnet-process.md), 및 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)합니다.

> [!WARNING]
> 에 연결 하는 경우는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스 디버깅 및 적중 된 중단점의에서 모든 관리 코드가 작업자 프로세스 중단 합니다. 서버의 모든 사용자에 대해 작업이 중지될 수 있습니다. 프로덕션 서버에서 디버깅하려면 프로덕션 작업에 미칠 수 있는 모든 영향을 고려해야 합니다.

[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스에 연결하는 프로세스는 다른 모든 원격 프로세스에 연결하는 방법과 동일합니다. 연결된 상태에서 적절한 프로젝트가 열려 있지 않으면 애플리케이션이 중단될 때 대화 상자가 표시됩니다. 이 대화 상자에는 응용 프로그램의 소스 파일 위치를 지정하라는 메시지가 표시됩니다. 대화 상자에서 지정한 파일 이름은 웹 서버에 있는 디버그 기호에 지정한 파일 이름과 일치해야 합니다. 자세한 내용은 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다. IIS에서 원격 디버깅을 설정 하려면을 참조 하세요 [Remote Debugging ASP.NET on a Remote IIS Computer](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)합니다.

> [!NOTE]
> 대부분의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에서는 비즈니스 논리나 다른 유용한 코드가 포함된 DLL을 참조합니다. 앱을 배포 하는 경우 참조 되는 이러한 DLL 로컬 컴퓨터에서 웹 응용 프로그램의 가상 디렉터리의 \bin 폴더에 복사 합니다. 디버깅하는 경우 웹 응용 프로그램이 로컬 컴퓨터에 있는 DLL 복사본이 아니라 가상 디렉터리에 있는 DLL 복사본을 참조한다는 점에 주의합니다.

## <a name="see-also"></a>참고 항목
- [ASP.NET 애플리케이션 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [방법: ASP.NET 애플리케이션에 디버깅 사용](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [방법: ASP.NET 프로세스의 이름 찾기](../debugger/how-to-find-the-name-of-the-aspnet-process.md)
- [기호 파일(.pdb) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)