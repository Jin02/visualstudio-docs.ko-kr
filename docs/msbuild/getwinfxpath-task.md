---
title: GetWinFXPath 작업 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- getting the directory of the current .NET Framework runtime [WPF MSBuild]
- GetWinFXPath task [WPF MSBuild], parameters
- GetWinFXPath task [WPF MSBuild]
- obtaining the path to the current .NET Framework runtime [WPF MSBuild]
ms.assetid: b1dfb467-f3d3-47f3-83ef-af7b0e33a772
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c95e5ad882d7021b597d7ba0ad8c38177f4a5136
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996510"
---
# <a name="getwinfxpath-task"></a>GetWinFXPath 작업
<xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> 작업은 현재 [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] 런타임의 디렉터리를 반환합니다.

## <a name="task-parameters"></a>작업 매개 변수

| 매개 변수 | 설명 |
|-------------------| - |
| `WinFXPath` | 선택적 **String** 출력 매개 변수입니다.<br /><br /> [!INCLUDE[TLA2#tla_winfx](../msbuild/includes/tla2sharptla_winfx_md.md)] 런타임의 실제 경로를 지정합니다. |
| `WinFXNativePath` | 필수 **String** 매개 변수입니다.<br /><br /> 네이티브 [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] 런타임의 경로를 지정합니다. |
| `WinFXWowPath` | 필수 **String** 매개 변수입니다.<br /><br /> 64비트 시스템의 32비트 **Windows** 모듈에서 [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] 어셈블리의 경로를 지정합니다. |

## <a name="remarks"></a>주의
 <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> 작업이 64비트 프로세서에서 실행되는 경우 **WinFXPath** 매개 변수는 **WinFXWowPath** 매개 변수에 저장된 경로로 설정되고, 그렇지 않으면 **WinFXPath** 매개 변수는 **WinFXNativePath** 매개 변수에 저장된 경로로 설정됩니다.

## <a name="example"></a>예제
 다음 예제에서는 **GetWinFXPath** 작업을 사용하여 [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] 런타임에 대한 네이티브 경로를 검색하는 방법을 보여 줍니다.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.GetWinFXPath"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="GetWinFXPathTask">
    <GetWinFXPath
      WinFXNativePath="c:\WinFXNative"
      WinFXWowPath="c:\WinFXWowNative" />
  </Target>
  <Import Project="$(MSBuildBinPath)\Microsoft.WinFX.targets" />
</Project>
```

## <a name="see-also"></a>참고 항목
- [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)
- [작업 참조](../msbuild/wpf-msbuild-task-reference.md)
- [MSBuild 참조](../msbuild/msbuild-reference.md)
- [작업 참조](../msbuild/msbuild-task-reference.md)
- [WPF 애플리케이션 빌드(WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
