---
title: '연습: 시작 페이지 사용자 지정 XAML 추가 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 193cea35fb7aa852b996aead6a26fd4e26b7b331
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "59002841"
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>연습: 시작 페이지에 사용자 지정 XAML 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 사용자 지정 Visual Studio 시작 페이지를 만들려면 웹 브라우저를 포함 하는 방법을 보여 줍니다.  
  
## <a name="adding-custom-xaml"></a>사용자 지정 XAML 추가  
  
1.  지침에 따라 시작 페이지를 만들려면 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md)합니다.  
  
2.  MainWindow.xaml 파일에서 찾기는 \<그리드 > 섹션입니다.  
  
3.  추가 \<TabControl > 요소 및 \<TabItem > 내는 \< 그리드 > 요소를 다음 예제에서와 같이 합니다.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
4.  추가 하 \<TabItem >를 사용 하 여를 \<단추 > 요소는 새 프로젝트를 엽니다.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="MyButton" Height="Auto">  
                <Button Name="btnNewProj" Content="New Project"   
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
                    CommandParameter="File.NewProject" >  
                </Button>  
            </TabItem>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
## <a name="testing-the-custom-start-page"></a>사용자 지정 시작 페이지 테스트  
  
1.  F5 키를 누릅니다.  
  
     사용자 지정 시작 페이지와 설치 되어 있지만 선택 되지 않은 Visual Studio의 실험적 인스턴스가 열립니다.  
  
2.  Visual Studio의 실험적 인스턴스에서 엽니다는 **도구 상자로 / 환경** 페이지입니다.  
  
3.  선택 **시작**합니다. 에 **시작 페이지 사용자 지정** 목록에서.xaml 파일을 선택한, 클릭 **확인**합니다.  
  
4.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
5.  클릭 합니다 **Bing** 탭 합니다.  
  
     Bing 웹 페이지 표시 됩니다.  
  
6.  클릭 합니다 **MyButton** 탭 합니다.  
  
     표시는 **MyProject** 열리는 단추를 **새 프로젝트** 대화 합니다.  
  
7.  실험적 인스턴스를 닫습니다.  
  
## <a name="applying-the-custom-start-page"></a>사용자 지정 시작 페이지를 적용합니다.  
  
#### <a name="to-test-the-custom-start-page"></a>사용자 지정 시작 페이지를 테스트 하려면  
  
1.  **도구 / 옵션 / 환경**를 선택 **시작**합니다. 에 **시작 페이지 사용자 지정** 목록에서.xaml 파일을 선택한, 클릭 **확인**합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이제 Visual Studio 시작 페이지는 웹 브라우저 탭 및 MyButton 탭을 표시 하는 탭을 있습니다. 사용 하 여 다른 기능을 포함 하는 사용자 지정 시작 페이지를 만들 수는 *코드 숨김* 모델에 표시 된 대로 사용자 지정.dll을 추가할 [시작 페이지에 사용자 정의 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)합니다. 결과.vsix 파일을 게시 하 여 다른 사용자와 사용자 지정 시작 페이지를 공유할 수 있습니다 합니다 [Visual Studio Marketplace](https://marketplace.visualstudio.com/) 웹 사이트 또는 다른 웹 사이트 또는 네트워크 공유 합니다. 자세한 내용은 [Deploying Custom Start Pages](../extensibility/deploying-custom-start-pages.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [WPF 컨테이너 컨트롤](http://msdn.microsoft.com/a0177167-d7db-4205-9607-8ae316952566)
