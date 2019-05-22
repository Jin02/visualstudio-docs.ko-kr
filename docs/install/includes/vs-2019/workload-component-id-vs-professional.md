---
title: Visual Studio Professional 2019 워크로드 및 구성 요소 ID
titleSuffix: ''
description: 작업 및 구성 요소 ID를 사용하여 명령줄로 Visual Studio를 설치하거나 VSIX 매니페스트에서 종속성으로 지정합니다.
keywords: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 04/02/2019
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.topic: include
ms.openlocfilehash: 23cbd90b81bcc05fef34040b4934c7152f79ae41
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65848897"
---
## <a name="visual-studio-core-editor-included-with-visual-studio-professional-2019"></a>Visual Studio 핵심 편집기(Visual Studio Professional 2019에 포함)

**ID:** Microsoft.VisualStudio.Workload.CoreEditor

**설명:** 구문 인식 코드 편집, 소스 코드 제어, 작업 항목 관리 등을 포함하는 Visual Studio 코어 셸 환경입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | C++ 사용자용 Visual Studio 시작 페이지 | 16.0.28315.86 | Optional

## <a name="azure-development"></a>Azure 개발

**ID:** Microsoft.VisualStudio.Workload.Azure

**설명:** 클라우드 앱 개발, 리소스 생성, Docker 지원 등 컨테이너를 빌드하기 위한 Azure SDK, 도구 및 프로젝트입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | 필수
Component.Microsoft.VisualStudio.Web.AzureFunctions | Azure WebJobs Tools | 16.0.28714.129 | 필수
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET Core 2.1 개발 도구 | 16.0.28516.191 | 필수
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 컴퓨팅 에뮬레이터 | 16.0.28720.110 | 필수
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.FSharp.WebTemplates | 웹 프로젝트에 대한 F# 언어 지원 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.ComponentGroup.Azure.Prerequisites | Azure 개발 필수 구성 요소 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Azure WebJobs Tools | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake 및 Stream Analytics 도구 | 16.0.28720.110 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 16.0.28516.191 | 권장
Microsoft.VisualStudio.Component.AspNet45 | 고급 ASP.NET 기능 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.Azure.Kubernetes.Tools | Visual Studio Tools for Kubernetes | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.ResourceManager.Tools | Azure Resource Manager 핵심 도구 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Azure.ServiceFabric.Tools | Service Fabric 도구 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services 빌드 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | .NET 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.Azure.CloudServices | Azure Cloud Services 도구 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.ComponentGroup.Azure.ResourceManager.Tools | Azure Resource Manager 도구 | 16.0.28528.71 | 권장
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.4.6.1.DeveloperTools | .NET Framework 4.6.1 개발 도구 | 16.0.28621.142 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.Core.Component.SDK.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.2 | .NET Core 2.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.NetCore.ComponentGroup.Web.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.Component.Azure.Storage.AzCopy | Azure Storage AzCopy | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 16.0.28625.61 | Optional

## <a name="data-storage-and-processing"></a>데이터 스토리지 및 처리

**ID:** Microsoft.VisualStudio.Workload.Data

**설명:** SQL Server, Azure Data Lake 또는 Hadoop을 사용하여 데이터 솔루션을 연결, 개발 및 테스트하세요.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | 권장
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | 권장
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake 및 Stream Analytics 도구 | 16.0.28720.110 | 권장
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 16.0.28516.191 | 권장
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 권장
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 컴퓨팅 에뮬레이터 | 16.0.28720.110 | 권장
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services 빌드 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 권장
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 권장
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.FSharp.Desktop | F# 데스크톱 언어 지원 | 16.0.28315.86 | Optional

## <a name="data-science-and-analytical-applications"></a>데이터 과학 및 분석 애플리케이션

**ID:** Microsoft.VisualStudio.Workload.DataScience

**설명:** 데이터 과학 애플리케이션을 만들기 위한 언어 및 도구입니다(Python 및 F# 지원 포함).

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.PythonTools | Python 언어 지원 | 16.0.28625.61 | 권장
Microsoft.Component.PythonTools.Minicondax64 | Python miniconda | 16.0.28625.61 | 권장
Microsoft.Component.PythonTools.Web | Python 웹 지원 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.FSharp.Desktop | F# 데스크톱 언어 지원 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 권장
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 16.0.28625.61 | Optional
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python 네이티브 개발 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.140 | MSVC v140 - VS 2015 C++ 빌드 도구(v14.00) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | Optional

## <a name="net-desktop-development"></a>.NET 데스크톱 개발

**ID:** Microsoft.VisualStudio.Workload.ManagedDesktop

**설명:** C#, Visual Basic 및 F#을 사용하여 WPF, Windows Forms 및 콘솔 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET 데스크톱 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Microsoft.ComponentGroup.Blend | Blend for Visual Studio | 16.0.28315.86 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 16.0.28516.191 | 권장
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time 디버거 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 도구 | 16.0.28315.86 | 권장
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 16.0.28528.71 | Optional
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | Optional
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.4.6.1.DeveloperTools | .NET Framework 4.6.1 개발 도구 | 16.0.28621.142 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.Core.Component.SDK.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET Core 2.1 개발 도구 | 16.0.28516.191 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.2 | .NET Core 2.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.FSharp.Desktop | F# 데스크톱 언어 지원 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | Optional
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | Optional

## <a name="game-development-with-unity"></a>Unity를 사용한 게임 개발

**ID:** Microsoft.VisualStudio.Workload.ManagedGame

**설명:** 강력한 플랫폼 간 개발 환경인 Unity를 사용하여 2D 및 3D 게임을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 개발 도구 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Unity | Visual Studio Tools for Unity | 16.0.28315.86 | 필수
Component.UnityEngine.x64 | Unity 2018.3 64비트 편집기 | 16.0.28707.178 | 권장
Component.UnityEngine.x86 | Unity 5.6 32비트 편집기 | 16.0.28707.178 | 권장

## <a name="linux-development-with-c"></a>C++를 사용한 Linux 개발

**ID:** Microsoft.VisualStudio.Workload.NativeCrossPlat

**설명:** Linux 환경에서 실행되는 애플리케이션을 만들고 디버그합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.MDD.Linux | Linux 개발용 C++ | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 16.0.28315.86 | 필수
Component.Linux.CMake | Linux용 C++ CMake 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 권장
Component.MDD.Linux.GCC.arm | Embedded 및 IoT 개발 도구 | 16.0.28625.61 | Optional

## <a name="desktop-development-with-c"></a>C++를 사용한 데스크톱 개발

**ID:** Microsoft.VisualStudio.Workload.NativeDesktop

**설명:** Microsoft C++ 도구 세트, ATL 또는 MFC를 사용하여 Windows 데스크톱 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | C++ 2019 재배포 가능 업데이트 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Visual C++ 핵심 데스크톱 기능 | 16.0.28315.86 | 필수
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time 디버거 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.ATL | v142 빌드 도구용 C++ ATL(x86 및 x64) | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.CMake.Project | Windows용 C++ CMake 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.TestAdapterForBoostTest | Test Adapter for Boost.Test | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.VC.TestAdapterForGoogleTest | Test Adapter for Google Test | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 권장
Component.Incredibuild | IncrediBuild - 빌드 가속화 | 16.0.28528.71 | Optional
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.3 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 16.0.28625.61 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.VC.140 | MSVC v140 - VS 2015 C++ 빌드 도구(v14.00) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | v142 빌드 도구용 C++ MFC(x86 및 x64) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | v142 빌드 도구용 C++/CLI 지원 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | v142 빌드 도구용 C++ 모듈(x64/x86 – 실험적) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.v141.x86.x64 | MSVC v141 – VS 2017 C++ x64/x86 빌드 도구(v14.16) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299 | Windows 10 SDK(10.0.16299.0) | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK(10.0.17134.0) | 16.0.28517.75 | Optional

## <a name="game-development-with-c"></a>C++를 사용한 게임 개발

**ID:** Microsoft.VisualStudio.Workload.NativeGame

**설명:** C++의 모든 기능을 사용하여 DirectX, Unreal 또는 Cocos2d로 구동하는 전문 게임을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | C++ 2019 재배포 가능 업데이트 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | 권장
Component.Android.NDK.R16B | Android NDK(R16B) | 16.0.28728.38 | Optional
Component.Android.SDK25.Private | Android SDK 설치(API 레벨 25)(C++를 통해 모바일 개발을 할 수 있도록 로컬 설치) | 16.0.28625.61 | Optional
Component.Ant | Apache Ant(1.9.3) | 1.9.3.8 | Optional
Component.Cocos | Cocos | 16.0.28315.86 | Optional
Component.Incredibuild | IncrediBuild - 빌드 가속화 | 16.0.28528.71 | Optional
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.3 | Optional
Component.MDD.Android | C++ Android 개발 도구 | 16.0.28517.75 | Optional
Component.OpenJDK | OpenJDK(Microsoft 배포) | 16.0.28625.61 | Optional
Component.Unreal | 언리얼 엔진 설치 관리자 | 16.0.28625.61 | Optional
Component.Unreal.Android | Unreal 엔진용 Android IDE 지원 | 16.0.28625.61 | Optional
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 16.0.28516.191 | Optional
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 대상 및 빌드 작업 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299 | Windows 10 SDK(10.0.16299.0) | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK(10.0.17134.0) | 16.0.28517.75 | Optional

## <a name="mobile-development-with-c"></a>C++를 사용한 모바일 개발

**ID:** Microsoft.VisualStudio.Workload.NativeMobile

**설명:** C++를 사용하여 iOS, Android 또는 Windows용 플랫폼 간 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Android.SDK25.Private | Android SDK 설치(API 레벨 25)(C++를 통해 모바일 개발을 할 수 있도록 로컬 설치) | 16.0.28625.61 | 필수
Component.OpenJDK | OpenJDK(Microsoft 배포) | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | 필수
Component.Android.NDK.R16B | Android NDK(R16B) | 16.0.28728.38 | 권장
Component.Ant | Apache Ant(1.9.3) | 1.9.3.8 | 권장
Component.MDD.Android | C++ Android 개발 도구 | 16.0.28517.75 | 권장
Component.Android.NDK.R16B_3264 | Android NDK(R16B)(32비트) | 16.0.28728.38 | Optional
Component.Google.Android.Emulator.API25.Private | Google Android 에뮬레이터(API 레벨 25)(로컬 설치) | 16.0.28625.61 | Optional
Component.HAXM.Private | Intel HAXM(Hardware Accelerated Execution Manager)(로컬 설치) | 16.0.28528.71 | Optional
Component.Incredibuild | IncrediBuild - 빌드 가속화 | 16.0.28528.71 | Optional
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.3 | Optional
Component.MDD.IOS | C++ iOS 개발 도구 | 16.0.28517.75 | Optional

## <a name="net-core-cross-platform-development"></a>.NET Core 플랫폼 간 개발

**ID:** Microsoft.VisualStudio.Workload.NetCoreTools

**설명:** Docker 지원이 포함된 .NET Core, ASP.NET Core, HTML/JavaScript 및 컨테이너를 사용하여 플랫폼 간 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | 필수
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET Core 2.1 개발 도구 | 16.0.28516.191 | 필수
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.FSharp.WebTemplates | 웹 프로젝트에 대한 F# 언어 지원 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Component.Microsoft.VisualStudio.Web.AzureFunctions | Azure WebJobs Tools | 16.0.28714.129 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 컴퓨팅 에뮬레이터 | 16.0.28720.110 | 권장
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | .NET 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Azure WebJobs Tools | 16.0.28621.142 | 권장
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | 웹 개발용 클라우드 도구 | 16.0.28621.142 | 권장
Microsoft.Net.Core.Component.SDK.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.2 | .NET Core 2.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.NetCore.ComponentGroup.Web.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | 개발 시간 IIS 지원 | 16.0.28315.86 | Optional

## <a name="mobile-development-with-net"></a>.NET을 사용한 모바일 개발

**ID:** Microsoft.VisualStudio.Workload.NetCrossPlat

**설명:** Xamarin을 사용하여 iOS, Android 또는 Windows용 플랫폼 간 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Xamarin | Xamarin | 16.0.28625.61 | 필수
Component.Xamarin.RemotedSimulator | Xamarin 원격 시뮬레이터 | 16.0.28315.86 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET Core 2.1 개발 도구 | 16.0.28516.191 | 필수
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.Merq | 일반 Xamarin 내부 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.MonoDebugger | Mono 디버거 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions.TemplateEngine | ASP.NET 템플릿 엔진 | 16.0.28315.86 | 필수
Component.Android.SDK27 | Android SDK 설치(API 레벨 27) | 16.0.28517.75 | 권장
Component.OpenJDK | OpenJDK(Microsoft 배포) | 16.0.28625.61 | 권장

## <a name="aspnet-and-web-development"></a>ASP.NET 및 웹 개발

**ID:** Microsoft.VisualStudio.Workload.NetWeb

**설명:** Docker 지원이 포함된 ASP.NET, ASP.NET Core, HTML/JavaScript 및 컨테이너를 사용하여 웹 애플리케이션을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | 필수
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET Core 2.1 개발 도구 | 16.0.28516.191 | 필수
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.FSharp.WebTemplates | 웹 프로젝트에 대한 F# 언어 지원 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Component.Microsoft.VisualStudio.Web.AzureFunctions | Azure WebJobs Tools | 16.0.28714.129 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 16.0.28516.191 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.AspNet45 | 고급 ASP.NET 기능 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 컴퓨팅 에뮬레이터 | 16.0.28720.110 | 권장
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | .NET 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 도구 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Azure WebJobs Tools | 16.0.28621.142 | 권장
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | 웹 개발용 클라우드 도구 | 16.0.28621.142 | 권장
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.4.6.1.DeveloperTools | .NET Framework 4.6.1 개발 도구 | 16.0.28621.142 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.Core.Component.SDK.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.2 | .NET Core 2.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.NetCore.ComponentGroup.Web.2.2 | .NET Core 2.2 개발 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 16.0.28625.61 | Optional
Microsoft.VisualStudio.ComponentGroup.AdditionalWebProjectTemplates | 추가 프로젝트 템플릿(이전 버전) | 16.0.28621.142 | Optional
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | 개발 시간 IIS 지원 | 16.0.28315.86 | Optional

## <a name="nodejs-development"></a>Node.js 개발

**ID:** Microsoft.VisualStudio.Workload.Node

**설명:** 비동기 이벤트 구동 JavaScript 런타임인 Node.js를 사용하여 확장 가능한 네트워크 애플리케이션을 빌드합니다. 

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Node.Tools | Node.js 개발 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | Optional

## <a name="officesharepoint-development"></a>Office/SharePoint 개발

**ID:** Microsoft.VisualStudio.Workload.Office

**설명:** C#, VB 및 JavaScript를 사용하여 Office와 SharePoint 추가 기능, SharePoint 솔루션 및 VSTO 추가 기능을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | 필수
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET 데스크톱 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Sharepoint.Tools | Visual Studio용 Office 개발자 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.Workflow | Windows Workflow Foundation | 16.0.28315.86 | 필수
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.TeamOffice | VSTO(Visual Studio Tools for Office) | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.4.6.1.DeveloperTools | .NET Framework 4.6.1 개발 도구 | 16.0.28621.142 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 16.0.28516.191 | Optional
Microsoft.VisualStudio.ComponentGroup.Sharepoint.WIF | Windows Identity Foundation 3.5 | 16.0.28621.142 | Optional

## <a name="python-development"></a>Python 개발

**ID:** Microsoft.VisualStudio.Workload.Python

**설명:** Python에 대한 편집, 디버깅, 대화형 개발 및 소스 제어입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.PythonTools | Python 언어 지원 | 16.0.28625.61 | 필수
Component.CPython3.x64 | Python 3 64비트(3.7.2) | 3.7.2 | 권장
Component.Microsoft.VisualStudio.LiveShare | Live Share | 1.0.12 | 권장
Microsoft.Component.PythonTools.Minicondax64 | Python miniconda | 16.0.28625.61 | 권장
Microsoft.Component.PythonTools.Web | Python 웹 지원 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 16.0.28315.86 | 권장
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 16.0.28517.75 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 권장
Component.CPython2.x64 | Python 2 64비트(2.7.15) | 2.7.15 | Optional
Component.CPython2.x86 | Python 2 32비트(2.7.15) | 2.7.15 | Optional
Component.CPython3.x86 | Python 3 32비트(3.7.2) | 3.7.2 | Optional
Component.Microsoft.VisualStudio.RazorExtension | Razor 언어 서비스 | 16.0.28714.129 | Optional
Component.Microsoft.Web.LibraryManager | 라이브러리 관리자 | 16.0.28315.86 | Optional
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 16.0.28625.61 | Optional
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python 네이티브 개발 도구 | 16.0.28621.142 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | Optional
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | Optional
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 컴퓨팅 에뮬레이터 | 16.0.28720.110 | Optional
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services 빌드 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.MSSQL.CMDLnUtils | SQL Server 명령줄 유틸리티 | 16.0.28707.177 | Optional
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.140 | MSVC v140 - VS 2015 C++ 빌드 도구(v14.00) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | Optional
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET 및 웹 개발 도구 필수 조건 | 16.0.28621.142 | Optional

## <a name="universal-windows-platform-development"></a>유니버설 Windows 플랫폼 개발

**ID:** Microsoft.VisualStudio.Workload.Universal

**설명:** C#, VB 또는 C++(선택 사항)를 사용하여 유니버설 Windows 플랫폼용 애플리케이션을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.NetFX.Native | .NET 네이티브 | 16.0.28315.86 | 필수
Microsoft.ComponentGroup.Blend | Blend for Visual Studio | 16.0.28315.86 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Core.Component.SDK.2.1 | .NET Core 2.1 개발 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.DiagnosticTools | .NET 프로파일링 도구 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Graphics | 이미지 및 3D 모델 편집기 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 16.0.28517.75 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 16.0.28315.86 | 필수
Microsoft.VisualStudio.Component.TypeScript.3.3 | TypeScript 3.3 SDK | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK(10.0.17763.0) | 16.0.28517.75 | 필수
Microsoft.VisualStudio.ComponentGroup.UWP.NetCoreAndStandard | .NET 네이티브 및 .NET Standard | 16.0.28516.191 | 필수
Microsoft.VisualStudio.ComponentGroup.UWP.Support | 유니버설 Windows 플랫폼 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin용 유니버설 Windows 플랫폼 도구 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 16.0.28621.142 | 필수
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | Optional
Microsoft.Component.VC.Runtime.OSSupport | v142 빌드 도구용 C++ 유니버설 Windows 플랫폼 런타임 | 16.0.28625.61 | Optional
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.UWP.VC.ARM64 | v142 빌드 도구용 C++ 유니버설 Windows 플랫폼 지원(ARM64) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | C++ 2019 재배포 가능 업데이트 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | MSVC v142 – VS 2019 C++ ARM 빌드 도구(v14.20) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | MSVC v142 – VS 2019 C++ ARM64 빌드 도구(v14.20) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.v141.ARM | MSVC v141 – VS 2017 C++ ARM 빌드 도구(v14.16) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.v141.ARM64 | MSVC v141 – VS 2017 C++ ARM64 빌드 도구(v14.16) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.v141.x86.x64 | MSVC v141 – VS 2017 C++ x64/x86 빌드 도구(v14.16) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299 | Windows 10 SDK(10.0.16299.0) | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK(10.0.17134.0) | 16.0.28517.75 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.IpOverUsb | USB 디바이스 연결 | 16.0.28320.51 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Visual C++ 핵심 데스크톱 기능 | 16.0.28315.86 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.VC | C++(v142) 유니버설 Windows 플랫폼 도구 | 16.0.28621.142 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.VC.v141 | C++(v141) 유니버설 Windows 플랫폼 도구 | 16.0.28621.142 | Optional

## <a name="visual-studio-extension-development"></a>Visual Studio 확장 개발

**ID:** Microsoft.VisualStudio.Workload.VisualStudioExtension

**설명:** Visual Studio용 추가 기능 및 확장(새 명령, 코드 분석기 및 도구 창 포함)을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.SDK | .NET Framework 4.7.2 SDK | 16.0.28517.75 | 필수
Microsoft.Net.Component.4.7.2.TargetingPack | .NET Framework 4.7.2 타기팅 팩 | 16.0.28517.75 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.7.2 개발 도구 | 16.0.28516.191 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 16.0.28714.129 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 16.0.28625.61 | 필수
Microsoft.VisualStudio.Component.VSSDK | Visual Studio SDK | 16.0.28315.86 | 필수
Microsoft.VisualStudio.ComponentGroup.VisualStudioExtension.Prerequisites | Visual Studio 확장 개발 필수 구성 요소 | 16.0.28621.142 | 필수
Microsoft.VisualStudio.Component.DiagnosticTools | .NET 프로파일링 도구 | 16.0.28625.61 | 권장
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 16.0.28625.61 | 권장
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 16.0.28528.71 | Optional
Microsoft.Component.CodeAnalysis.SDK | .NET Compiler Platform SDK | 16.0.28625.61 | Optional
Microsoft.Component.VC.Runtime.OSSupport | v142 빌드 도구용 C++ 유니버설 Windows 플랫폼 런타임 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.ClassDesigner | 클래스 디자이너 | 16.0.28528.71 | Optional
Microsoft.VisualStudio.Component.DslTools | Modeling SDK | 16.0.28315.86 | Optional
Microsoft.VisualStudio.Component.VC.ATL | v142 빌드 도구용 C++ ATL(x86 및 x64) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | v142 빌드 도구용 C++ MFC(x86 및 x64) | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | C++ 핵심 기능 | 16.0.28625.61 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | MSVC v142 – VS 2019 C++ x64/x86 빌드 도구(v14.20) | 16.0.28625.61 | Optional

## <a name="unaffiliated-components"></a>독립적 구성 요소

이러한 구성 요소는 작업에 포함되지 않지만 개별 구성 요소로 선택할 수 있습니다.

구성 요소 ID | name | 버전
--- | --- | ---
Component.GitHub.VisualStudio | Visual Studio용 GitHub 확장 | 2.5.9.5485
Component.Xamarin.Inspector | Xamarin Inspector | 16.0.28315.86
Component.Xamarin.Profiler | Xamarin Profiler | 16.0.28315.86
Component.Xamarin.Workbooks | Xamarin Workbooks | 16.0.28315.86
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 16.0.28707.177
Microsoft.Component.HelpViewer | 도움말 뷰어 | 16.0.28625.61
Microsoft.NetCore.1x.ComponentGroup.Web | 웹용 .NET Core 1.0 - 1.1 개발 도구 | 16.0.28621.142
Microsoft.VisualStudio.Component.AzureDevOps.OfficeIntegration | Azure DevOps Office 통합 | 16.0.28625.61
Microsoft.VisualStudio.Component.DependencyValidation.Community | 종속성 유효성 검사 | 16.0.28517.75
Microsoft.VisualStudio.Component.Git | Windows용 GIT | 16.0.28625.61
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 16.0.28625.61
Microsoft.VisualStudio.Component.LinqToSql | LINQ to SQL 도구 | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATL.ARM | v142 빌드 도구용 C++ ATL(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATL.ARM.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ ATL(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATL.ARM64 | v142 빌드 도구용 C++ ATL(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATL.ARM64.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ ATL(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATL.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ ATL(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.ATLMFC.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ MFC(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.MFC.ARM | v142 빌드 도구용 C++ MFC(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.MFC.ARM.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ MFC(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.MFC.ARM64 | v142 빌드 도구용 C++ MFC(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.MFC.ARM64.Spectre | 스펙터 완화를 지원하는 v142 빌드 도구용 C++ MFC(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.Redist.MSM | C++ 2019 재배포 가능 MSM | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.Runtimes.ARM.Spectre | MSVC v142 – VS 2019 C++ ARM 스펙터 완화 라이브러리(v14.20) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.Runtimes.ARM64.Spectre | MSVC v142 – VS 2019 C++ ARM64 스펙터 완화 라이브러리(v14.20) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.Runtimes.x86.x64.Spectre | MSVC v142 – VS 2019 C++ x64/x86 스펙터 완화 라이브러리(v14.20)  | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ARM.Spectre | MSVC v141 – VS 2017 C++ ARM 스펙터 완화 라이브러리(v14.16) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ARM64.Spectre | MSVC v141 – VS 2017 C++ ARM64 스펙터 완화 라이브러리(v14.16) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL | v141 빌드 도구용 C++ ATL(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL.ARM | v141 빌드 도구용 C++ ATL(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL.ARM.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ ATL(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL.ARM64 | v141 빌드 도구용 C++ ATL(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL.ARM64.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ ATL(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.ATL.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ ATL(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.CLI.Support | v141 빌드 도구용 C++/CLI 지원 | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC | v141 빌드 도구용 C++ MFC(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC.ARM | v141 빌드 도구용 C++ MFC(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC.ARM.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ MFC(ARM) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC.ARM64 | v141 빌드 도구용 C++ MFC(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC.ARM64.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ MFC(ARM64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.MFC.Spectre | 스펙터 완화를 지원하는 v141 빌드 도구용 C++ MFC(x86 및 x64) | 16.0.28625.61
Microsoft.VisualStudio.Component.VC.v141.x86.x64.Spectre | MSVC v141 – VS 2017 C++ x64/x86 스펙터 완화 라이브러리(v14.16) | 16.0.28625.61
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 16.0.28707.177
Microsoft.VisualStudio.Component.WinXP | VS 2017(v141) 도구용 C++ Windows XP 지원[사용되지 않음] | 16.0.28625.61
Microsoft.VisualStudio.Web.Mvc4.ComponentGroup | ASP.NET MVC 4 | 16.0.28621.142
