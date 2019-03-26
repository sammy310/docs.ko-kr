---
title: '작업 2: 워크플로 디자이너 호스트'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: e02134408b38e5c9aee9c59d86b1dfce032653d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708641"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="ca22b-102">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="ca22b-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="ca22b-103">인스턴스를 호스트 하는 절차에 설명 합니다 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Windows Presentation Foundation (WPF) 응용 프로그램에서입니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="ca22b-104">절차는 구성 합니다 **표** designer가 들어 있는 컨트롤의 인스턴스를 프로그래밍 방식으로 만듭니다는 <xref:System.Activities.Presentation.WorkflowDesigner> 기본값을 포함 하는 <xref:System.Activities.Statements.Sequence> 활동, 디자이너 메타 데이터를 제공 등록 모든 기본 제공 활동 및 호스트에 대 한 디자이너 지원 합니다 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 에 [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="ca22b-105">워크플로 디자이너를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="ca22b-105">To host the workflow designer</span></span>  
  
1.  <span data-ttu-id="ca22b-106">만든 HostingApplication 오픈 프로젝트 [작업 1: 새 Windows Presentation Foundation 응용 프로그램을 만드는](task-1-create-a-new-wpf-app.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>  
  
2.  <span data-ttu-id="ca22b-107">[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]를 쉽게 사용할 수 있도록 창의 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="ca22b-108">이 위해 선택 **MainWindow** 디자이너를 표시 하려면 F4 키를 누릅니다.는 **속성** 창에서를 **레이아웃** 섹션을 설정 합니다 **너비** 값을 600으로 하며 **높이** 350 값으로.</span><span class="sxs-lookup"><span data-stu-id="ca22b-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3.  <span data-ttu-id="ca22b-109">선택 하 여 표 이름을 설정 합니다 **그리드** 디자이너에서 패널 (안의 상자 클릭를 **MainWindow**) 설정를 **이름** 맨 위에 있는 속성을  **속성** "추가한 다음 grid1" 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4.  <span data-ttu-id="ca22b-110">에 **속성** 창에서 줄임표 (**...** ) 옆에 `ColumnDefinitions` 열려는 속성을 **컬렉션 편집기** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ca22b-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="ca22b-111">에 **컬렉션 편집기** 대화 상자에서 클릭 합니다 **추가** 단추를 세 번 레이아웃에 세 개의 열을 삽입할 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="ca22b-112">첫 번째 열이 포함 됩니다는 **도구 상자**, 두 번째 열을 호스트 하는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], 세 번째 열 속성 검사자에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6.  <span data-ttu-id="ca22b-113">설정의 `Width` 값 가운데 열의 속성을 "4 \*"입니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7.  <span data-ttu-id="ca22b-114">**확인** 을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="ca22b-115">다음 XAML이 MainWindow.xaml 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  <span data-ttu-id="ca22b-116">**솔루션 탐색기**MainWindow.xaml을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="ca22b-117">다음 단계에 따라 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-117">Modify the code by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ca22b-118">다음 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <span data-ttu-id="ca22b-119"><xref:System.Activities.Presentation.WorkflowDesigner>의 인스턴스를 보관할 전용 멤버 필드를 선언하려면 `MainWindow`에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
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
  
    3.  <span data-ttu-id="ca22b-120">다음 `AddDesigner` 메서드를 `MainWindow` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="ca22b-121">구현의 인스턴스를 만듭니다는 <xref:System.Activities.Presentation.WorkflowDesigner>, 추가 <xref:System.Activities.Statements.Sequence> 활동을 추가한 다음 grid1의 가운데 열에 배치 **그리드**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
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
  
    4.  <span data-ttu-id="ca22b-122">디자이너 메타데이터를 등록하여 모든 기본 제공 활동에 대한 디자이너 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="ca22b-123">그러면 도구 상자의 활동을 <xref:System.Activities.Statements.Sequence>의 원래 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 활동으로 끌어 놓을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="ca22b-124">이렇게 하려면 `RegisterMetadata` 메서드를 `MainWindow` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         <span data-ttu-id="ca22b-125">활동 디자이너를 등록 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 사용자 지정 활동 디자이너를 만드는](how-to-create-a-custom-activity-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5.  <span data-ttu-id="ca22b-126">`MainWindow` 클래스 생성자에서 앞에서 선언한 메서드에 호출을 추가하여 디자이너 지원을 위한 메타데이터를 등록하고 <xref:System.Activities.Presentation.WorkflowDesigner>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
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
        >  <span data-ttu-id="ca22b-127">`RegisterMetadata` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 포함한 기본 제공 활동의 디자이너 메타데이터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="ca22b-128">`AddDesigner` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 사용하기 때문에 `RegisterMetadata` 메서드를 먼저 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="ca22b-129">F5 키를 눌러 솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="ca22b-130">참조 [작업 3: 도구 상자 및 PropertyGrid 창 만들기](task-3-create-the-toolbox-and-propertygrid-panes.md) 추가 하는 방법을 알아보려면 **도구 상자** 하 고 **PropertyGrid** 재 호스트 된 워크플로 디자이너를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca22b-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca22b-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca22b-131">See also</span></span>
- [<span data-ttu-id="ca22b-132">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="ca22b-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="ca22b-133">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ca22b-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="ca22b-134">작업 3: 도구 상자 및 PropertyGrid 창 만들기</span><span class="sxs-lookup"><span data-stu-id="ca22b-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
