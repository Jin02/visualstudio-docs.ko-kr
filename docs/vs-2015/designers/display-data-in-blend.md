---
title: Blend에서 데이터 표시 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 87d31b6c-4607-4121-bb7d-cfc80390ab93
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: fa084ee92d7e262cb04661b4bbf26eefb74b9e06
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72664659"
---
# <a name="display-data-in-blend"></a>Blend에서 데이터 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

페이지의 레이아웃을 사용자 지정할 때 디자이너에서 예제 데이터를 볼 수 있습니다. 예제 데이터는 처음부터 새로 또는 기존 클래스를 사용하여 생성할 수 있습니다. 예제 데이터 실행 시 앱에 표시되는 *라이브 데이터* 에 연결할 수도 있습니다.

 **항목 내용:**

- [예제 데이터 생성](#Scratch)

- [클래스에서 예제 데이터 생성](#Existing)

- [WPF 애플리케이션에 라이브 데이터 표시](#LiveWPF)

- [스토어 또는 Phone 앱에 라이브 데이터 표시](#LiveStore)

## <a name="Scratch"></a> 예제 데이터 생성
 예제 데이터를 생성하려면 XAML 문서를 엽니다. **데이터** 패널에서 **예제 데이터** ![ ](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "만들기 30540d76-7256-43ce-b5d9-4b2edf3d339f") 만들기 단추를 선택한 다음 **새 샘플 데이터**를 선택 합니다.

 **데이터** 패널에서 데이터 구조를 정의한 다음 모든 페이지의 UI 요소에 바인딩합니다.

 ![](../designers/media/496d7ebc-fe46-42f6-95a8-57b0e5be5d49.png "496d7ebc-fe46-42f6-95a8-57b0e5be5d49")

 앱을 실행할 때 샘플 데이터가 페이지에 표시 되도록 하려면 **데이터 원본 옵션** ![ ](../designers/media/ae1fd260-4f84-420d-b196-45fde357d81d.png "ae1fd260-4f84-420d-b196-45fde357d81d")을 선택한 다음 **응용 프로그램 실행 시 사용**을 선택 합니다.

 ![](../designers/media/05d5356d-91bb-4e6b-b3f7-29b76852c4b3.png "05d5356d-91bb-4e6b-b3f7-29b76852c4b3")

 **짧은 비디오 보기:** ![설치 된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [에서 샘플 데이터를 처음부터 만듭니다](http://www.bing.com/videos/search?q=blend%20data&qs=n&form=QBVR&pq=blend%20data&sc=8-7&sp=-1&sk=#view=detail&mid=F8F2449A76956D480FD2F8F2449A76956D480FD2).

 **짧은 비디오 보기:** ![설치 된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Blend를 사용 하 여 일부 데이터 바인딩을 혼합](https://www.youtube.com/watch?v=LSwPB6CAvjg)합니다.

## <a name="Existing"></a> 클래스에서 예제 데이터 생성
 데이터 구조를 설명하는 클래스를 이미 만들었으면 이 클래스에서 예제 데이터를 생성할 수 있습니다.

 클래스에서 예제 데이터를 생성 하려면 XAML 문서를 열고 **데이터** 패널에서 **예제 데이터** ![ ](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "만들기 30540d76-7256-43ce-b5d9-4b2edf3d339f") 만들기 단추를 클릭 한 다음 **클래스에서 예제 데이터 만들기**를 클릭 합니다.

 **짧은 비디오 보기:** ![설치 된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [클래스에서 샘플 데이터 만들기](http://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=video&cd=1&cad=rja&uact=8&ved=0CB0QtwIwAA&url=http%3A%2F%2Fchannel9.msdn.com%2FShows%2FInside%2BWindows%2BPhone%2FIWP54--Windows-Phone-Data-Binding-and-the-Magic-of-XAML&ei=F1oHVNryM4ysogSJ2oDYDw&usg=AFQjCNEYvw1WA1rdF7bfpj5RwMLUs7RCVg)

 **짧은 비디오 보기:** ![설치 된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Blend를 사용 하 여 일부 데이터 바인딩을 혼합](https://www.youtube.com/watch?v=LSwPB6CAvjg)합니다.

## <a name="LiveWPF"></a> WPF 애플리케이션에 라이브 데이터 표시
 **짧은 비디오 보기:** ![설치 된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [XML 데이터 원본 만들기](https://www.youtube.com/watch?v=RjQueappjqk&feature=youtube_gdata)

## <a name="LiveStore"></a> 스토어 또는 Phone 앱에 라이브 데이터 표시
 [데이터 및 파일(XAML) 작업](https://msdn.microsoft.com/library/windows/apps/xaml/br229562.aspx)을 참조하세요.

## <a name="see-also"></a>관련 항목:
 [Blend for Visual Studio를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)
