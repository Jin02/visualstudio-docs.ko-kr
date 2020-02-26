---
title: UpdateManifestForBrowserApplication 작업 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UpdateManifestForBrowserApplication task [WPF MSBuild]
- adding the <hostInBrowser /> element to the application manifest [WPF MSBuild]
- building XBAP projects [WPF MSBuild]
- UpdateManifestForBrowserApplication task [WPF MSBuild], parameters
ms.assetid: 653339f7-654b-4d64-a26a-5c9f27036895
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a78add284a5cea966d1176645649eed19017addd
ms.sourcegitcommit: 2ae2436dc3484b9dfa10e0483afba1e5a02a52eb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77579538"
---
# <a name="updatemanifestforbrowserapplication-task"></a>UpdateManifestForBrowserApplication 작업
<xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> 작업은 [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] 프로젝트를 빌드할 때 애플리케이션 매니페스트( *\<projectname&gt;.exe.manifest*)에 **\<hostInBrowser /&gt;** 요소를 추가하기 위해 실행합니다.

## <a name="task-parameters"></a>작업 매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`ApplicationManifest`|필수 **ITaskItem[]** 매개 변수입니다.<br /><br /> `<hostInBrowser />` 요소를 추가할 애플리케이션 매니페스트 파일의 경로와 이름을 지정합니다.|
|`HostInBrowser`|필수 **Boolean** 매개 변수입니다.<br /><br /> **\<hostInBrowser /&gt;** 요소를 포함하도록 애플리케이션 매니페스트를 수정할지 여부를 지정합니다. **true**이면 새 **\<hostInBrowser />** 요소가 **\<entryPoint />** 요소에 포함됩니다. 포함된 요소는 누적됩니다. 즉, 기존 **\<hostInBrowser />** 요소를 제거하거나 덮어쓰지 않습니다. 대신 추가 **\<hostInBrowser />** 요소가 만들어집니다. **false**이면 애플리케이션 매니페스트가 수정되지 않습니다.|

## <a name="remarks"></a>설명
 [!INCLUDE[TLA2#tla_xbap#plural](../msbuild/includes/tla2sharptla_xbapsharpplural_md.md)]는 [!INCLUDE[TLA#tla_clickonce](../msbuild/includes/tlasharptla_clickonce_md.md)] 배포를 통해 실행되므로 지원되는 배포 및 애플리케이션 매니페스트를 사용하여 게시되어야 합니다. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)]는 [GenerateApplicationManifest](generateapplicationmanifest-task.md) 작업을 사용하여 애플리케이션 매니페스트를 생성합니다.

 그러고 나서 다음 예제에서와 같이 브라우저에서 호스트되도록 애플리케이션을 구성하기 위해 추가적인 **\<hostInBrowser /&gt;** 요소를 애플리케이션 매니페스트에 추가해야 합니다.

```xml
<!--MyXBAPApplication.exe.manifest-->
<?xml version="1.0" encoding="utf-8"?>
<asmv1:assembly ... >
    <asmv1:assemblyIdentity ... />
    <application />
    <entryPoint>
      ...
      <hostInBrowser xmlns="urn:schemas-microsoft-com:asm.v3" />
    </entryPoint>
  ...
/>
```

 [!INCLUDE[TLA2#tla_xbap](../msbuild/includes/tla2sharptla_xbap_md.md)] 프로젝트를 빌드할 때 `<hostInBrowser />` 요소를 추가하기 위해 <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> 작업이 실행됩니다.

## <a name="example"></a>예제
 다음 예제에서는 애플리케이션 매니페스트 파일에 `<hostInBrowser />` 요소를 포함하는 방법을 보여줍니다.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="UpdateManifestForBrowserApplicationTask">
    <UpdateManifestForBrowserApplication
      ApplicationManifest="MyXBAPApplication.exe.manifest"
      HostInBrowser="true" />
  </Target>
</Project>
```

## <a name="see-also"></a>참조
- [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)
- [작업 참조](../msbuild/wpf-msbuild-task-reference.md)
- [MSBuild 참조](../msbuild/msbuild-reference.md)
- [작업 참조](../msbuild/msbuild-task-reference.md)
- [WPF 애플리케이션 빌드(WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
- [WPF XAML 브라우저 애플리케이션 개요](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)