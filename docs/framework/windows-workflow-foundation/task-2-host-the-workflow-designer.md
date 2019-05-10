---
title: '작업 2: 워크플로 디자이너 호스트'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: cce90c6b7f5edfaf960415f0a5d0787f8eee526b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665294"
---
# <a name="task-2-host-the-workflow-designer"></a>작업 2: 워크플로 디자이너 호스트
인스턴스를 호스트 하는 절차에 설명 합니다 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Windows Presentation Foundation (WPF) 응용 프로그램에서입니다.  
  
 절차는 구성 합니다 **표** designer가 들어 있는 컨트롤의 인스턴스를 프로그래밍 방식으로 만듭니다는 <xref:System.Activities.Presentation.WorkflowDesigner> 기본값을 포함 하는 <xref:System.Activities.Statements.Sequence> 활동, 디자이너 메타 데이터를 제공 등록 모든 기본 제공 활동 및 호스트에 대 한 디자이너 지원 합니다 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 에 [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 응용 프로그램입니다.  
  
### <a name="to-host-the-workflow-designer"></a>워크플로 디자이너를 호스트하려면  
  
1. 만든 HostingApplication 오픈 프로젝트 [작업 1: 새 Windows Presentation Foundation 응용 프로그램을 만드는](task-1-create-a-new-wpf-app.md)합니다.  
  
2. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]를 쉽게 사용할 수 있도록 창의 크기를 조정합니다. 이 위해 선택 **MainWindow** 디자이너를 표시 하려면 F4 키를 누릅니다.는 **속성** 창에서를 **레이아웃** 섹션을 설정 합니다 **너비** 값을 600으로 하며 **높이** 350 값으로.  
  
3. 선택 하 여 표 이름을 설정 합니다 **그리드** 디자이너에서 패널 (안의 상자 클릭를 **MainWindow**) 설정를 **이름** 맨 위에 있는 속성을  **속성** "추가한 다음 grid1" 창입니다.  
  
4. 에 **속성** 창에서 줄임표 (**...** ) 옆에 `ColumnDefinitions` 열려는 속성을 **컬렉션 편집기** 대화 상자.  
  
5. 에 **컬렉션 편집기** 대화 상자에서 클릭 합니다 **추가** 단추를 세 번 레이아웃에 세 개의 열을 삽입할 합니다. 첫 번째 열이 포함 됩니다는 **도구 상자**, 두 번째 열을 호스트 하는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], 세 번째 열 속성 검사자에 사용 됩니다.  
  
6. 설정의 `Width` 값 가운데 열의 속성을 "4 *"입니다.  
  
7. **확인** 을 클릭하여 변경 내용을 저장합니다. 다음 XAML이 MainWindow.xaml 파일에 추가됩니다.  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. **솔루션 탐색기**MainWindow.xaml을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다. 다음 단계에 따라 코드를 수정합니다.  
  
    1. 다음 네임스페이스를 추가합니다.  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2. <xref:System.Activities.Presentation.WorkflowDesigner>의 인스턴스를 보관할 전용 멤버 필드를 선언하려면 `MainWindow`에 다음 코드를 추가합니다.  
  
        ```csharp  
        public partial class MainWindow : Window  
        {  
            private WorkflowDesigner wd;  
  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
        }  
        ```  
  
    3. 다음 `AddDesigner` 메서드를 `MainWindow` 클래스에 추가합니다. 구현의 인스턴스를 만듭니다는 <xref:System.Activities.Presentation.WorkflowDesigner>, 추가 <xref:System.Activities.Statements.Sequence> 활동을 추가한 다음 grid1의 가운데 열에 배치 **그리드**합니다.  
  
        ```csharp  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
        ```  
  
    4. 디자이너 메타데이터를 등록하여 모든 기본 제공 활동에 대한 디자이너 지원을 추가합니다. 그러면 도구 상자의 활동을 <xref:System.Activities.Statements.Sequence>의 원래 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 활동으로 끌어 놓을 수 있습니다. 이렇게 하려면 `RegisterMetadata` 메서드를 `MainWindow` 클래스에 추가합니다.  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         활동 디자이너를 등록 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 사용자 지정 활동 디자이너를 만드는](how-to-create-a-custom-activity-designer.md)합니다.  
  
    5. `MainWindow` 클래스 생성자에서 앞에서 선언한 메서드에 호출을 추가하여 디자이너 지원을 위한 메타데이터를 등록하고 <xref:System.Activities.Presentation.WorkflowDesigner>를 만듭니다.  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  `RegisterMetadata` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 포함한 기본 제공 활동의 디자이너 메타데이터를 등록합니다. `AddDesigner` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 사용하기 때문에 `RegisterMetadata` 메서드를 먼저 호출해야 합니다.  
  
9. F5 키를 눌러 솔루션을 빌드하고 실행합니다.  
  
10. 참조 [작업 3: 도구 상자 및 PropertyGrid 창 만들기](task-3-create-the-toolbox-and-propertygrid-panes.md) 추가 하는 방법을 알아보려면 **도구 상자** 하 고 **PropertyGrid** 재 호스트 된 워크플로 디자이너를 지원 합니다.  
  
## <a name="see-also"></a>참고자료

- [워크플로 디자이너 재호스트](rehosting-the-workflow-designer.md)
- [작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기](task-1-create-a-new-wpf-app.md)
- [작업 3: 도구 상자 및 PropertyGrid 창 만들기](task-3-create-the-toolbox-and-propertygrid-panes.md)
