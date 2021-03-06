---
title: Manifest to Code | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 17ecacea-397d-4a97-b003-01bd5d56e936
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e21f266cc0dea39cfbaba660ef3557af6023c104
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85536125"
---
# <a name="manifest-to-code"></a>Manifest to Code
Manifest to Code 도구는 Visual Studio 이미지 서비스에 대해 imagemanifest 파일을 사용 하 고 c + +, c #, VB 또는 Visual Studio 확장용 vsct 파일에서 이미지 매니페스트의 값을 참조 하기 위한 래퍼 파일을 생성 하는 콘솔 응용 프로그램입니다. 이 도구는 Visual Studio 이미지 서비스에서 직접 이미지를 요청 하는 데 사용할 수 있는 래퍼 파일을 생성 하거나 코드가 자체 UI 및 렌더링을 처리 하지 않는 경우 Api를 통해 매니페스트 값을 전달 하는 데 사용할 수 있습니다.

## <a name="how-to-use-the-tool"></a>이 도구를 사용 하는 방법
 **구문**

 ManifestToCode/manifest: \<Image Manifest file> /language: \<Code Language>\<Optional Args>

 **인수**

|**스위치 이름**|**참고**|**필수 또는 선택**|
|-|-|-|
|/manifest|코드 래퍼를 만들거나 업데이트 하는 데 사용할 이미지 매니페스트의 경로입니다.|필수|
|/language|코드 래퍼를 생성할 언어입니다.<br /><br /> 유효한 값: CPP, c + +, CS, CSharp, c #, VB 또는 VSCT 값은 대/소문자를 구분 하지 않습니다.<br /><br /> VSCT 언어 옵션의 경우/monikerClass,/classAccess 및/namespace 옵션이 무시 됩니다.|필수|
|/imageIdClass|도구에서 만든 imageIdClass 및 연결 된 파일의 이름입니다. C + + 언어 옵션의 경우 .h 파일만 생성 됩니다.<br /><br /> 기본값: \<Manifest Path> \MyImageIds.\<Lang Ext>|선택 사항|
|/monikerClass|도구에서 만든 monikerClass 및 연결 된 파일의 이름입니다. C + + 언어 옵션의 경우 .h 파일만 생성 됩니다. VSCT 언어에 대해서는 무시 됩니다.<br /><br /> 기본값: \<Manifest Path> \MyMonikers.\<Lang Ext>|선택 사항|
|/classAccess|ImageIdClass 및 monikerClass에 대 한 액세스 한정자입니다. 액세스 한정자가 지정 된 언어에 대해 유효한 지 확인 합니다. VSCT 언어 옵션에 대해서는이 옵션이 무시 됩니다.<br /><br /> 기본값: 공용|선택 사항|
|/namespace|코드 래퍼에 정의 된 네임 스페이스입니다. VSCT 언어 옵션에 대해서는이 옵션이 무시 됩니다. '. ' 또는 ':: '는 선택한 언어 옵션에 관계 없이 올바른 네임 스페이스 구분 기호입니다.<br /><br /> 기본값: MyImages|선택 사항|
|/noLogo|이 플래그를 설정 하면 제품 및 저작권 정보 인쇄를 중지 합니다.|선택 사항|
|/?|도움말 정보를 인쇄 합니다.|선택 사항|
|/help|도움말 정보를 인쇄 합니다.|선택|

 **예제**

- ManifestToCode/manifest: D:\MyManifest.imagemanifest/language: CSharp

- ManifestToCode/smanifest: D:\MyManifest.imagemanifest/language: c + +/namespace: My:: Namespace/imageIdClass: MyImageIds/monikerClass: MyMonikers/classAccess: friend

- ManifestToCode/manifest: D:\MyManifest.imagemanifest/language: VSCT/imageIdClass: MyImageIds

## <a name="notes"></a>참고

- Manifest from Resources 도구에 의해 생성 된 이미지 매니페스트와 함께이 도구를 사용 하는 것이 좋습니다.

- 도구는 코드 래퍼를 생성 하는 기호 항목만 찾습니다. 이미지 매니페스트에 기호가 없으면 생성 된 코드 래퍼가 비어 있게 됩니다. 기호를 사용 하지 않는 이미지 또는 이미지 집합이 이미지 매니페스트에 있는 경우 코드 래퍼에서 제외 됩니다.

## <a name="sample-output"></a>샘플 출력
 **C # 래퍼**

 C #에 대 한 단순 이미지 ID 및 이미지 모니커 클래스 쌍은 아래 코드와 비슷합니다.

```csharp
//-----------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by the ManifestToCode tool.
//     Tool Version: 14.0.15198
// </auto-generated>
//-----------------------------------------------------------------------------

using System;

namespace MyImages
{
    public static class MyImageIds
    {
        public static readonly Guid AssetsGuid = new Guid("{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}");

        public const int MyImage1 = 0;
        public const int MyImage2 = 1;
    }
}
//-----------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by the ManifestToCode tool.
//     Tool Version: 14.0.15198
// </auto-generated>
//-----------------------------------------------------------------------------

using Microsoft.VisualStudio.Imaging.Interop;

namespace MyImages
{
    public static class MyMonikers
    {
        public static ImageMoniker MyImage1 { get { return new ImageMoniker { Guid = MyImageIds.AssetsGuid, Id = MyImageIds.MyImage1 }; } }
        public static ImageMoniker MyImage2 { get { return new ImageMoniker { Guid = MyImageIds.AssetsGuid, Id = MyImageIds.MyImage2 }; } }
    }
}
```

 **C + + 래퍼**

 C + +에 대 한 간단한 이미지 ID 및 이미지 모니커 클래스 쌍은 아래 코드와 비슷합니다.

```cpp
//-----------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by the ManifestToCode tool.
//     Tool Version: 14.0.15198
// </auto-generated>
//-----------------------------------------------------------------------------

#pragma once

#include <guiddef.h>

namespace MyImages {

class MyImageIds {
public:

    static const GUID AssetsGuid;

    static const int MyImage1 = 0;
    static const int MyImage2 = 1;

};

__declspec(selectany) const GUID MyImageIds::AssetsGuid = {0x442d8739,0xefde,0x46a4,{0x8f,0x29,0xe3,0xa1,0xe5,0xe7,0xf8,0xb4}};

}
//-----------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by the ManifestToCode tool.
//     Tool Version: 14.0.15198
// </auto-generated>
//-----------------------------------------------------------------------------

#pragma once

#include "ImageParameters140.h"
#include "MyImageIds.h"

namespace MyImages {

class MyMonikers {
public:

    static const ImageMoniker MyImage1;
    static const ImageMoniker MyImage2;

};

__declspec(selectany) const ImageMoniker MyMonikers::MyImage1 = { MyImageIds::AssetsGuid, MyImageIds::MyImage1 };
__declspec(selectany) const ImageMoniker MyMonikers::MyImage2 = { MyImageIds::AssetsGuid, MyImageIds::MyImage2 };

}
```

 **Visual Basic 래퍼**

 Visual Basic에 대 한 단순 이미지 ID 및 이미지 모니커 클래스 쌍은 아래 코드와 비슷합니다.

```vb
' -----------------------------------------------------------------------------
'  <auto-generated>
'      This code was generated by the ManifestToCode tool.
'      Tool Version: 14.0.15198
'  </auto-generated>
' -----------------------------------------------------------------------------

Imports System

Namespace MyImages

    Public Module MyImageIds

        Public Shared ReadOnly AssetsGuid As Guid = New Guid("{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}")

        Public Const MyImage1 As Integer = 0
        Public Const MyImage2 As Integer = 1

    End Module

End Namespace
' -----------------------------------------------------------------------------
'  <auto-generated>
'      This code was generated by the ManifestToCode tool.
'      Tool Version: 14.0.15198
'  </auto-generated>
' -----------------------------------------------------------------------------

Imports Microsoft.VisualStudio.Imaging.Interop

Namespace MyImages

    Public Module MyMonikers

        Public Readonly Property MyImage1
            Get
                Return New ImageMoniker With {.Guid = MyImageIds.AssetsGuid, .Id = MyImageIds.MyImage1}
            End Get
        End Property

        Public Readonly Property MyImage2
            Get
                Return New ImageMoniker With {.Guid = MyImageIds.AssetsGuid, .Id = MyImageIds.MyImage2}
            End Get
        End Property

    End Module

End Namespace
```

 **VSCT 래퍼**

 Vsct 파일의 이미지 Id 집합은 다음과 유사 합니다.

```xml
<?xml version='1.0' encoding='utf-8'?>
<!--
- [auto-generated]
     This code was generated by the ManifestToCode tool.
     Tool Version: 14.0.15198
- [/auto-generated]
-->
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable">
  <Symbols>
    <GuidSymbol name="AssetsGuid" value="{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}">
      <IDSymbol name="MyImage1" value="0" />
      <IDSymbol name="MyImage2" value="1" />
    </GuidSymbol>
  </Symbols>
</CommandTable>
```
