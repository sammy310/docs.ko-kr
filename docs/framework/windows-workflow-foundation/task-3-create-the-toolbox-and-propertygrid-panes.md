---
title: '작업 3: 도구 상자 및 PropertyGrid 창 만들기'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 6339969c52a5c4eedfb0e89eebdc982ca3fe6686
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988706"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="216f9-102">작업 3: 도구 상자 및 PropertyGrid 창 만들기</span><span class="sxs-lookup"><span data-stu-id="216f9-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="216f9-103">이 작업에서는 **도구 상자** 및 **PropertyGrid** 창을 만든 후 다시 호스트 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]된에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="216f9-104">참조를 위해 MainWindow.xaml.cs 파일에 있어야 하는 코드는 [워크플로 디자이너 재호스팅](rehosting-the-workflow-designer.md) 의 3 가지 작업을 완료 한 후이 항목의 끝에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="216f9-105">도구 상자를 만들어 표에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="216f9-105">To create the Toolbox and add it to the grid</span></span>  
  
1. <span data-ttu-id="216f9-106">작업 2에 [설명 된 절차에 따라 얻은 HostingApplication 프로젝트를 엽니다. 워크플로 디자이너](task-2-host-the-workflow-designer.md)를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>  
  
2. <span data-ttu-id="216f9-107">**솔루션 탐색기** 창에서 mainwindow.xaml 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3. <span data-ttu-id="216f9-108">`MainWindow` <xref:System.Activities.Statements.Sequence>를만들고 **, 도구 상자**에 새 **도구 상자** 범주를 추가 하 고, `GetToolboxControl` 및활동형식을해당범주에할당하는메서드를클래스<xref:System.Activities.Statements.Assign>에추가합니다. <xref:System.Activities.Presentation.Toolbox.ToolboxControl></span><span class="sxs-lookup"><span data-stu-id="216f9-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4. <span data-ttu-id="216f9-109">모눈의 왼쪽 `AddToolbox` 열에 **도구 상자** 를 배치 하는 전용 메서드를 `MainWindow` 클래스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. <span data-ttu-id="216f9-110">다음 코드와 같이 `AddToolBox` 클래스 생성자에 `MainWindow()` 메서드에 대한 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. <span data-ttu-id="216f9-111">F5 키를 눌러 솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="216f9-112"><xref:System.Activities.Statements.Assign> 및 활동을포함하는도구상자가표시<xref:System.Activities.Statements.Sequence> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="216f9-113">PropertyGrid를 만들려면</span><span class="sxs-lookup"><span data-stu-id="216f9-113">To create the PropertyGrid</span></span>  
  
1. <span data-ttu-id="216f9-114">**솔루션 탐색기** 창에서 mainwindow.xaml 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2. <span data-ttu-id="216f9-115">클래스에 메서드를 추가 하 여 PropertyGrid 창을 표의 가장 오른쪽 열에 놓습니다. `AddPropertyInspector` `MainWindow`</span><span class="sxs-lookup"><span data-stu-id="216f9-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. <span data-ttu-id="216f9-116">다음 코드와 같이 `AddPropertyInspector` 클래스 생성자에 `MainWindow()` 메서드에 대한 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
    ```  
  
4. <span data-ttu-id="216f9-117">F5 키를 눌러 솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="216f9-118">**도구 상자**, 워크플로 디자인 캔버스 및 **PropertyGrid** 창이 모두 표시 되어야 하며, <xref:System.Activities.Statements.Assign> 활동 또는 <xref:System.Activities.Statements.Sequence> 활동을 디자인 캔버스로 끌 때 속성 표는 강조 표시 된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="216f9-119">예제</span><span class="sxs-lookup"><span data-stu-id="216f9-119">Example</span></span>  
 <span data-ttu-id="216f9-120">이제 MainWindow.xaml.cs 파일에 다음 코드가 들어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f9-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
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
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="216f9-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="216f9-121">See also</span></span>

- [<span data-ttu-id="216f9-122">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="216f9-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="216f9-123">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="216f9-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="216f9-124">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="216f9-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
