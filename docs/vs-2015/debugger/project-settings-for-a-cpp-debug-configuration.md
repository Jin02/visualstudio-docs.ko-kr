---
title: 프로젝트 설정에 대 한는 C++ 디버그 구성 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCGPUDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.SymbolPath
- VC.Project.IVCClusterDebugPageObject.ApplicationCommand
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.VCDebugSettings.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCGPUDebugPageObject.CommandArguments
- VC.Project.VCDebugSettings.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunWorkingDirectory
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunCommand
- VC.Project.IVCGPUDebugPageObject.WorkingDirectory
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCClusterDebugPageObject.MPIRunArguments
- VC.Project.IVCClusterDebugPageObject.MPIAcceptFilter
- VC.Project.IVCGPUDebugPageObject.RemoteConnection
- VC.Project.VCDebugSettings.PDBPath
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.VCDebugSettings.SQLDebugging
- VC.Project.VCDebugSettings.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ShimCommand
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.VCDebugSettings.Command
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ApplicationArguments
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCGPUDebugPageObject.DeploymentDirectory
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.Environment
- VC.Project.IVCGPUDebugPageObject.BreakpointBehavior
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
- VC.Project.IVCGPUDebugPageObject.AcceleratorType
- VC.Project.IVCGPUDebugPageObject.Environment
- VC.Project.VCDebugSettings.RemoteMachine
- VC.Project.IVCGPUDebugPageObject.AdditionalFilesToDeploy
- VC.Project.VCDebugSettings.WorkingDirectory
- vs.debug.builds
- VC.Project.VCDebugSettings.Attach
- VC.Project.VCDebugSettings.HttpUrl
- VC.Project.IVCClusterDebugPageObject.MPIAcceptMode
- VC.Project.IVCGPUDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCGPUDebugPageObject.Command
- VC.Project.VCDebugSettings.Remote
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.VCDebugSettings.EnvironmentMerge
- VC.Project.IVCGPUDebugPageObject.MachineName
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- DEBUG linker option
- -PDB linker option
- -Zl compiler option [C++]
- /DEBUG linker option
- /PDBSTRIPPED linker option
- /MAPINFO linker option
- -Zd compiler option [C++]
- -DEBUG linker option
- MAPINFO linker option
- /ZI compiler option [C++]
- ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debugger settings
- project settings [Visual Studio], debug configurations
- mapfiles, project settings
- debug configurations, C++
- project settings [Visual Studio]
- /PDB linker option
- -PDBSTRIPPED linker option
- debug builds, project settings
- PDB linker option
- projects [Visual Studio], debug configurations
- project configurations, debug
- Zd compiler option [C++]
- MAP linker option
- /Z7 compiler option [C++]
- .pdb files, debug build project settings
- -MAP linker option
- -MAPINFO linker option
- /Zd compiler option [C++]
- PDBSTRIPPED linker option
- -Z7 compiler option [C++]
- pdb files, debug build project settings
- /MAP linker option
ms.assetid: 860c7f13-a108-4fe5-8fca-d235cd3ca1cb
caps.latest.revision: 52
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca9ff0678ba2c7abafa0d988efa09437ccd27dca
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687564"
---
# <a name="project-settings-for-a-c-debug-configuration"></a>C++ 디버그 구성에 대한 프로젝트 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C 또는 시각적 개체에 대 한 프로젝트 설정을 변경할 수 있습니다 C++ 디버그 구성에는 **속성 페이지** 대화 상자에 설명 된 대로 [방법: 디버그 및 릴리스 구성 설정](../debugger/how-to-set-debug-and-release-configurations.md)을 참조하세요. 다음 표에서는 **속성 페이지** 대화 상자에서 디버거 관련 설정을 확인할 수 있는 위치에 대해 설명합니다.  
  
> [!WARNING]
> 디버그 프로젝트 설정은 합니다 **구성 속성/디버깅** Windows 스토어 앱 및 작성 된 구성 요소에 대 한 범주 C++ 다릅니다. 참조 [디버그 세션 시작 (VB, C#, C++ 및 XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) Windows 개발자 센터에서.  
  
 에 사용할 디버거를 지정 합니다 **실행할 디버거** 목록 상자입니다. 이 선택에 따라 표시되는 속성이 달라집니다.  
  
 각 디버그 속성 설정은 솔루션을 저장할 때마다 솔루션의 "사용자별" 파일(.vcxproj.user)에 자동으로 작성되어 저장됩니다.  
  
### <a name="configuration-properties-folder-debugging-category"></a>구성 속성 폴더(디버깅 범주)  
  
|**설정**|**설명**|  
|-----------------|---------------------|  
|**실행할 디버거**|실행할 디버거를 지정합니다. 다음 항목을 선택할 수 있습니다.<br /><br /> -   **로컬 Windows 디버거**<br />-   **원격 Windows 디버거**<br />-   **웹 브라우저 디버거**<br />-   **웹 서비스 디버거**|  
|**명령**(로컬 Windows 디버거)|로컬 컴퓨터에서 디버깅하고 있는 프로그램을 시작하는 명령을 지정합니다.|  
|**원격 명령**(원격 Windows 디버거)|원격 컴퓨터의 .exe에 대한 경로입니다. 원격 컴퓨터에서 입력할 때와 같이 경로를 입력합니다.|  
|**명령 인수** (로컬 Windows 디버거 및 원격 Windows 디버거)|- 위에서 지정한 명령의 인수를 지정합니다.<br /><br /> 이 상자에서는 다음과 같은 리디렉션 연산자를 사용할 수 있습니다.<br /><br /> < `file`<br /> 파일에서 stdin을 읽습니다.<br /><br /> > `file`<br /> stdout을 파일에 씁니다.<br /><br /> >> `file`<br /> stdout을 파일에 추가합니다.<br /><br /> 2> `file`<br /> stderr을 파일에 씁니다.<br /><br /> 2>> `file`<br /> stderr을 파일에 추가합니다.<br /><br /> 2> &1<br /> stderr(2) 출력을 stdout(1)과 동일한 위치로 보냅니다.<br /><br /> 1> &2<br /> stdout(1) 출력을 stderr(2)과 동일한 위치로 보냅니다.<br /><br /> 대부분의 경우 이러한 연산자는 콘솔 애플리케이션에만 적용됩니다.|  
|**작업 디렉터리**|EXE가 있는 프로젝트 디렉터리에 상대적인 디버깅 중인 프로그램의 작업 디렉터리를 지정합니다. 이 설정을 비워 두면 프로젝트 디렉터리가 작업 디렉터리가 됩니다. 원격 디버깅의 경우 프로젝트 디렉터리는 원격 서버에 있습니다.|  
|**연결**(로컬 Windows 디버거 및 원격 Windows 디버거)|애플리케이션을 시작할지 아니면 애플리케이션에 연결할지를 지정합니다. 기본 설정은 아니요입니다.|  
|**원격 서버 이름**(원격 Windows 디버거)|애플리케이션을 디버깅할 다른 컴퓨터의 이름을 지정합니다.<br /><br /> RemoteMachine 빌드 매크로이 속성의 값으로 설정 자세한 내용은 [빌드 명령 및 속성 매크로](https://msdn.microsoft.com/library/239bd708-2ea9-4687-b264-043f1febf98b)합니다.|  
|**연결**(원격 Windows 디버거)|원격 디버깅을 위해 표준 및 인증 없는 연결 형식 사이를 전환할 수 있습니다. **원격 서버 이름** 상자에 원격 컴퓨터 이름을 지정합니다. 연결 형식에는 다음이 포함됩니다.<br /><br /> -   **Windows 인증을 사용한 원격**<br />-   **인증 안 함 (네이티브 전용)을 사용한 원격**<br /><br /> **참고** 인증을 사용하지 않는 원격 디버깅의 경우 원격 컴퓨터가 보안 위반에 취약할 수 있습니다. Windows 인증 모드를 사용하는 것이 더 안전합니다.<br /><br /> 자세한 내용은 [원격 디버깅 설치](../debugger/remote-debugging.md)합니다.|  
|**HTTP URL**(웹 서비스 디버거 및 웹 브라우저 디버거)|디버깅하려는 프로젝트가 있는 URL을 지정합니다.|  
|**디버거 형식**|사용할 디버거 형식을 지정 합니다. **네이티브 전용**, **관리 전용**를 **GPU 전용**를 **혼합**를 **자동** (기본값) 또는 **스크립트**.<br /><br /> -   **네이티브 전용**은 비관리 C++ 코드에 사용합니다.<br />-   **관리 전용**은 공용 언어 런타임에서 실행되는 코드(관리 코드)에 사용합니다.<br />-   **혼합**은 관리 코드와 비관리 코드 둘 다에 사용할 수 있는 디버거를 호출합니다.<br />-   **자동**은 컴파일러와 EXE 정보에 따라 디버거 형식을 결정합니다.<br />-   **스크립트**는 스크립트용 디버거를 호출합니다.<br />-   **GPU 전용**은 GPU 디바이스 또는 DirectX 기준 래스터라이저에서 실행되는 C++ AMP 코드에 사용합니다. 참조 [GPU 코드 디버그](../debugger/debugging-gpu-code.md)합니다.|  
|**환경** (로컬 Windows 디버거)|디버깅할 프로그램의 환경 변수를 지정합니다. 표준 환경 변수 구문을 사용 하 여 (예를 들어 `PATH="%SystemRoot%\..."`). 이러한 변수는 **환경 병합** 설정에 따라 시스템 환경과 병합되거나 시스템 환경을 재정의합니다. 설정 열을 클릭하면 "편집…"이 나타납니다. 환경 변수를 편집하려면 해당 링크를 클릭합니다.|  
|**환경 병합**(로컬 Windows 디버거)|**환경** 상자에 지정한 변수를 운영 체제에 정의된 환경과 병합할지 여부를 결정합니다. 기본 설정은 예입니다.|  
|**SQL 디버깅**(MPI 클러스터 디버거를 제외한 모든 디버거)|[!INCLUDE[vcprvc](../includes/vcprvc-md.md)] 애플리케이션에서 SQL 프로시저를 디버깅할 수 있습니다. 기본 설정은 아니요입니다.|  
|**디버깅 가속기 형식**(GPU 디버깅만 해당)|디버깅에 사용할 GPU 디바이스를 지정합니다. 호환되는 GPU 디바이스용 디바이스 드라이버를 설치하면 옵션이 더 추가됩니다. 기본 설정은 "GPU - 소프트웨어 에뮬레이터"입니다.|  
|**GPU 기본 중단점 동작**(GPU 디버깅만 해당)|SIMD 이동의 각 스레드에 대해 중단점 이벤트가 발생하는지 여부를 지정합니다. 기본 설정은 이동당 한 번만 중단점 이벤트를 발생시키는 것입니다.|  
|**Amp 기본 액셀러레이터** (GPU 디버깅만 해당)|GPU 코드를 디버깅할 때 기본 AMP 액셀러레이터를 지정합니다. 문제의 원인이 사용자 코드가 아닌 하드웨어나 드라이버 때문인지 알아보려면 **WARP 소프트웨어 액셀러레이터**를 선택합니다.|  
|**배포 디렉터리**(원격 Windows 디버거)|시작하기 전에 프로젝트 출력을 복사할 원격 컴퓨터의 경로를 지정합니다. 경로는 원격 컴퓨터의 네트워크 공유이거나 원격 컴퓨터의 폴더에 대한 경로일 수 있습니다. 기본 설정은 비어 있습니다. 즉, 프로젝트 출력이 네트워크 공유에 복사되지 않습니다. 파일을 배포할 수 있도록 하려면 Configuration Manager 대화 상자에서 **배포** 확인란도 선택해야 합니다. 자세한 내용은 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)을 참조하세요.|  
|**배포할 추가 파일**(원격 Windows 디버거)|배포 디렉터리 속성이 설정된 경우 배포 디렉터리에 복사할 추가 파일의 세미콜론으로 구분된 목록입니다. 기본 설정은 비어 있습니다. 즉, 배포 디렉터리에 복사되는 추가 파일이 없습니다. 파일을 배포할 수 있도록 하려면 Configuration Manager 대화 상자에서 **배포** 확인란도 선택해야 합니다. 자세한 내용은 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)을 참조하세요.|  
|**Visual C++ 디버그 런타임 라이브러리 배포**(원격 Windows 디버거)|배포 디렉터리 속성이 설정된 경우 현재 플랫폼의 Visual C++ 디버그 런타임 라이브러리를 네트워크 공유에 복사할지 여부를 지정합니다. 기본 설정은 예입니다.|  
  
### <a name="cc-folder-general-category"></a>C/C++ 폴더(일반 범주)  
  
|설정|설명|  
|-------------|-----------------|  
|**디버그 정보 형식**([/Z7, /Zd, /Zi, /ZI](https://msdn.microsoft.com/library/ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8))|프로젝트에 대해 만들어질 디버그 정보 형식을 지정합니다.<br /><br /> 기본 옵션(/ZI)을 지정하면 편집하며 계속하기와 호환되는 형식의 프로그램 데이터베이스(PDB)가 만들어집니다. 자세한 내용은 [/z7, /Zd, /Zi, /ZI (디버그 정보 형식)](https://msdn.microsoft.com/library/ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8)합니다.|  
  
### <a name="cc-folder-optimization-category"></a>C/C++ 폴더(최적화 범주)  
  
|설정|설명|  
|-------------|-----------------|  
|**Optimization**|컴파일러에서 생성하는 코드를 최적화할지 여부를 지정합니다. 코드를 최적화하면 실행되는 코드가 변경됩니다. 최적화된 코드는 소스 코드와 더 이상 일치하지 않으므로 디버깅이 어려워집니다.<br /><br /> 기본 옵션 (**사용 안 함 (/ 0d**) 최적화를 표시 하지 않습니다. 최적화를 해제한 상태로 코드를 개발한 다음 프로덕션 버전의 코드를 만들 때 최적화를 설정할 수 있습니다.|  
  
### <a name="linker-folder-debugging-category"></a>링커 폴더(디버깅 범주)  
  
|설정|설명|  
|-------------|-----------------|  
|**디버그 정보 생성**([/DEBUG](https://msdn.microsoft.com/library/1af389ae-3f8b-4d76-a087-1cdf861e9103))|/Z7, /Zd, Zi 또는 /ZI로 지정된 형식의 디버그 정보를 포함하도록 링커에 지시합니다.|  
|**프로그램 데이터베이스 파일 생성**([/PDB:name](https://msdn.microsoft.com/library/d23db0ce-10cb-427a-bc60-d6b2a852723d))|이 상자에 PDB 파일의 이름을 지정합니다. 디버그 정보 형식으로 ZI 또는 /Zi를 선택해야 합니다.|  
|**전용 기호 제거**([/PDBSTRIPPED:filename](https://msdn.microsoft.com/library/9b9e0070-6a13-4142-8180-19c003fbbd55))|PDB 파일에 전용 기호를 포함하지 않으려면 이 상자에 PDB 파일의 이름을 지정합니다. 이 옵션을 사용하면 PDB 파일을 생성하는 컴파일러 또는 링커 옵션(예: /DEBUG, /Z7, /Zd 또는 /Zi)으로 프로그램 이미지를 빌드할 때 두 번째 PDB(프로그램 데이터베이스) 파일이 만들어집니다. 이 두 번째 PDB 파일에서는 고객에게 제공하지 않을 기호가 생략됩니다. 자세한 내용은 [/PDBSTRIPPED(전용 기호 제거)](https://msdn.microsoft.com/library/9b9e0070-6a13-4142-8180-19c003fbbd55)를 참조하세요.|  
|**맵 파일 생성**([/MAP](https://msdn.microsoft.com/library/9ccce53d-4e36-43da-87b0-7603ddfdea63))|링크할 때 맵 파일을 생성하도록 링커에 지시합니다. 기본 설정은 아니요입니다. 자세한 내용은 [/MAP(맵 파일 생성)](https://msdn.microsoft.com/library/9ccce53d-4e36-43da-87b0-7603ddfdea63)을 참조하세요.|  
|**맵 파일 이름** ([/map:](https://msdn.microsoft.com/library/9ccce53d-4e36-43da-87b0-7603ddfdea63)*이름*)|맵 파일 생성을 선택하면 이 상자에서 맵 파일을 지정할 수 있습니다. 자세한 내용은 [/MAP(맵 파일 생성)](https://msdn.microsoft.com/library/9ccce53d-4e36-43da-87b0-7603ddfdea63)을 참조하세요.|  
|**맵 내보내기**([/MAPINFO:EXPORTS](https://msdn.microsoft.com/library/533d2bce-f9b7-4fea-ae1c-0b4864c9d10b))|내보낸 함수를 맵 파일에 포함합니다. 기본 설정은 아니요입니다. 자세한 내용은 [/MAPINFO (맵파일에 정보 포함)](https://msdn.microsoft.com/library/533d2bce-f9b7-4fea-ae1c-0b4864c9d10b)합니다.|  
|**디버깅 가능한 어셈블리**([/ASSEMBLYDEBUG](https://msdn.microsoft.com/library/533d2bce-f9b7-4fea-ae1c-0b4864c9d10b))|링커 /ASSEMBLYDEBUG 옵션의 설정을 지정합니다. 다음과 같은 값을 사용할 수 있습니다.<br /><br /> -   **내보낸 디버깅 가능한 특성이 없습니다**.<br />-   **런타임 추적만 사용하고 최적화는 사용하지 않습니다 (/ASSEMBLYDEBUG)** . 이것이 기본 설정입니다.<br />-   **런타임 추적은 사용하지 않고 최적화만 사용합니다 (/ASSEMBLYDEBUG:DISABLE)** .<br />-    **\<부모 또는 프로젝트 기본값에서 상속>** .<br />- 자세한 내용은 [/ASSEMBLYDEBUG(DebuggableAttribute 추가)](https://msdn.microsoft.com/library/94443af3-470c-41d7-83a0-7434563d7982)를 참조하세요.|  
  
 Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings 인터페이스를 사용하여 프로그래밍 방식으로 구성 속성 폴더(디버그 범주)에 있는 이러한 설정을 변경할 수 있습니다. 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)   
 [Visual C++ 프로젝트 만들기 및 관리](https://msdn.microsoft.com/library/11003cd8-9046-4630-a189-a32bf3b88047)   
 [/ASSEMBLYDEBUG(DebuggableAttribute 추가)](https://msdn.microsoft.com/library/94443af3-470c-41d7-83a0-7434563d7982)   
 [빌드 명령 및 속성에 대한 일반 매크로](https://msdn.microsoft.com/library/239bd708-2ea9-4687-b264-043f1febf98b)
