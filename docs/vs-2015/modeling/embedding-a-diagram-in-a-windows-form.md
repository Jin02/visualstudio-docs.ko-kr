---
title: Windows 폼에 다이어그램 포함 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: fa6cd040-7c88-4329-b9c3-2a80b312610f
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 440b60697d4ab1e88f535b6c5ef824bc74e19c48
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068693"
---
# <a name="embedding-a-diagram-in-a-windows-form"></a>Windows Forms에 다이어그램 포함
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DSL 다이어그램에 표시 되는 Windows 컨트롤에서 포함할 수 있습니다는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 창입니다.  
  
## <a name="embedding-a-diagram"></a>다이어그램 포함  
  
#### <a name="to-embed-a-dsl-diagram-in-a-windows-control"></a>Windows 컨트롤에서 DSL 다이어그램을 포함 하려면  
  
1. 새 **사용자 정의 컨트롤** DslPackage 프로젝트 파일입니다.  
  
2. 사용자 정의 컨트롤에 패널 컨트롤을 추가 합니다. 이 패널에는 DSL 다이어그램 포함 됩니다.  
  
     필요한 다른 컨트롤을 추가 합니다.  
  
     컨트롤의 앵커 속성을 설정 합니다.  
  
3. 솔루션 탐색기에서 사용자 정의 컨트롤 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기**합니다. 코드에이 생성자 및 변수를 추가 합니다.  
  
    ```csharp  
  
    internal UserControl1(MyDSLDocView docView, Control content)  
      : this()  
    {  
      panel1.Controls.Add(content);  
      this.docView = docView;  
    }  
    private MyDSLDSLDocView docView;  
  
    ```  
  
4. 다음과 같은 콘텐츠로 DslPackage 프로젝트에 새 파일을 추가 합니다.  
  
    ```  
    using System.Windows.Forms;  
    namespace Company.MyDSL  
    {  
      partial class MyDSLDocView  
      {  
        private UserControl1 container;  
        public override IWin32Window Window  
        {  
          get  
          {  
            if (container == null)  
            {  
              // Put our own form inside the DSL window:  
              container = new UserControl1(this,  
                (Control)base.Window);  
            }  
            return container;  
    } } } }  
  
    ```  
  
5. DSL을 테스트 하려면 F5 키를 눌러 및 샘플 모델 파일을 엽니다. 컨트롤 내부에 다이어그램이 표시 됩니다. 도구 상자 및 기타 기능 정상적으로 작동 합니다.  
  
#### <a name="updating-the-form-using-store-events"></a>저장소 이벤트를 사용 하 여 폼을 업데이트 합니다.  
  
1. 폼 디자이너에서 추가 된 **ListBox** 라는 `listBox1`합니다. 모델에 요소 목록이 나타납니다. 사용 하 여 모델 synchronism 유지 됩니다 *이벤트를 저장할*합니다. 자세한 내용은 [이벤트 처리기 전파 변경 외부 모델](../modeling/event-handlers-propagate-changes-outside-the-model.md)합니다.  
  
2. 사용자 지정 코드 파일에서 추가 메서드를 재정의 DocView 클래스:  
  
    ```  
  
    partial class MyDSLDocView  
    {  
     /// <summary>  
     /// Register store event listeners.  
     /// This method is called when the model and diagram    
     /// have completed loading.   
     /// </summary>  
     protected override bool LoadView()  
      {  
        bool result = base.LoadView();  
        Store store = this.DocData.Store;  
        EventManagerDirectory emd = store.EventManagerDirectory;  
        DomainClassInfo componentClass = store.DomainDataDirectory.FindDomainClass(typeof(ExampleElement));  
        emd.ElementAdded.Add(componentClass, new EventHandler<ElementAddedEventArgs>(AddElement));  
        emd.ElementDeleted.Add(componentClass, new EventHandler<ElementDeletedEventArgs>(RemoveElement));  
  
        // Do the initial parts list:  
        container.SetUpFormFromModel();  
        return result;  
      }  
     /// <summary>  
     /// Listener method called on creation of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void AddElement(object sender, ElementAddedEventArgs e)  
     {  
       container.Add(e.ModelElement as ExampleElement);  
     }  
     /// <summary>  
     /// Listener method called after deletion of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void RemoveElement(object sender, ElementDeletedEventArgs e)  
     {  
       container.Remove(e.ModelElement as ExampleElement);  
     }  
  
    ```  
  
3. 코드 숨김에서 사용자 정의 컨트롤 추가 및 제거 하는 요소에 대 한 수신 대기 하는 메서드를 삽입 합니다.  
  
    ```  
  
          public partial class UserControl1 : UserControl { ...  
  
    private ExampleModel modelRoot;  
  
    internal void Add(ExampleElement e) { UpdatePartsList(); }  
    internal void Remove(ExampleElement e) { UpdatePartsList(); }  
  
    internal void SetUpFormFromModel()  
    {  
      modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;  
      UpdatePartsList();  
    }  
  
    private void UpdatePartsList()  
    {  
      StringBuilder builder = new StringBuilder();  
      listBox1.Items.Clear();  
      foreach (ExampleElement c in modelRoot.Elements)  
      {  
        listBox1.Items.Add(c.Name);  
      }  
    }  
  
    ```  
  
4. DSL을 테스트 하려면 f5 키를 생성 하 고 실험적 인스턴스의 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], 샘플 모델 파일을 엽니다.  
  
     올바른지 모든 추가 또는 삭제 후 실행 취소 및 다시 실행 및 목록 상자 모델의 요소 목록을 표시 되는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)
