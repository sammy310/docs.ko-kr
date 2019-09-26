---
title: '방법: 사용자 지정 작업 디자이너 만들기'
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 3c326508744f2aa2b34f5ee574cc9ec1e2863cf6
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306353"
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="ef9da-102">방법: 사용자 지정 작업 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="ef9da-102">How to: Create a Custom Activity Designer</span></span>

<span data-ttu-id="ef9da-103">사용자 지정 활동 디자이너는 일반적으로 디자이너를 함께 디자인 화면에 끌어 놓을 수 있는 다른 활동을 사용하여 연결된 활동을 구성할 수 있도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-103">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="ef9da-104">이 기능을 사용 하려면 사용자 지정 활동 디자이너가 임의의 활동을 배치할 수 있는 "끌어 놓기 영역"을 제공 하 고, 디자인 화면에서 요소의 결과 컬렉션을 관리 하는 방법도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-104">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="ef9da-105">이 항목에서는 이러한 끌어 놓기 영역이 포함된 사용자 지정 활동 디자이너를 만드는 방법과 디자이너 요소 컬렉션을 관리하는 데 필요한 편집 기능을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-105">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>

<span data-ttu-id="ef9da-106">사용자 지정 활동 디자이너는 일반적으로 특정 디자이너가 없는 활동의 기본 활동 디자이너 형식인 <xref:System.Activities.Presentation.ActivityDesigner>에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-106">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="ef9da-107">이 형식은 속성 표와 상호 작용하고, 색, 아이콘 등과 같은 기본 기능을 구성하는 디자인 타임 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-107">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>

<span data-ttu-id="ef9da-108"><xref:System.Activities.Presentation.ActivityDesigner>는 <xref:System.Activities.Presentation.WorkflowItemPresenter> 및 <xref:System.Activities.Presentation.WorkflowItemsPresenter>라는 두 도우미 컨트롤을 사용하여 사용자 지정 활동 디자이너를 쉽게 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-108"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="ef9da-109">또한 자식 요소 끌어서 놓기, 삭제, 선택, 추가 등과 같은 일반적인 기능을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-109">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="ef9da-110">는 내부에서 단일 자식 UI 요소를 <xref:System.Activities.Presentation.WorkflowItemsPresenter> 허용하고,"끌어놓기영역"을제공하는반면,는자식요소순서지정,이동,삭제및추가와같은추가기능을포함하여여러UI요소를지원할수있습니다.<xref:System.Activities.Presentation.WorkflowItemPresenter></span><span class="sxs-lookup"><span data-stu-id="ef9da-110">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>

<span data-ttu-id="ef9da-111">사용자 지정 활동 디자이너의 구현에서 강조 표시 해야 하는 스토리의 다른 주요 부분은 디자이너에서 편집 중인 항목의 메모리에 저장 된 인스턴스에 대 한 WPF 데이터 바인딩을 사용 하 여 시각적 편집을 바인딩하는 방법과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-111">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using WPF data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="ef9da-112">이 방법은 변경 내용 알림을 활성화하고 해당 상태의 변경 내용과 비슷한 이벤트를 추적하는 모델 항목 트리에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-112">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>

<span data-ttu-id="ef9da-113">이 항목에서는 두 가지 절차에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-113">This topic outlines two procedures.</span></span>

1. <span data-ttu-id="ef9da-114">첫 번째 절차는 <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 다른 활동을 받는 끌어 놓기 영역을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명하며,</span><span class="sxs-lookup"><span data-stu-id="ef9da-114">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="ef9da-115">이 절차는 [사용자 지정 복합 디자이너-워크플로 항목 프레 젠 터](./samples/custom-composite-designers-workflow-item-presenter.md) 샘플을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-115">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>

2. <span data-ttu-id="ef9da-116">두 번째 절차는 <xref:System.Activities.Presentation.WorkflowItemsPresenter>를 사용하여 포함된 요소 컬렉션을 편집하는 데 필요한 기능을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명하며,</span><span class="sxs-lookup"><span data-stu-id="ef9da-116">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="ef9da-117">이 절차는 [사용자 지정 복합 디자이너-워크플로 항목 프레 젠 터](./samples/custom-composite-designers-workflow-items-presenter.md) 샘플을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-117">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="ef9da-118">WorkflowItemPresenter를 사용하여 끌어 놓기 영역이 있는 사용자 지정 활동 디자이너를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ef9da-118">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>

1. <span data-ttu-id="ef9da-119">Visual Studio 2010을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-119">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="ef9da-120">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트 ...** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-120">On the **File** menu, point to **New**, and then select **Project…**.</span></span>

     <span data-ttu-id="ef9da-121">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-121">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="ef9da-122">**설치 된 템플릿** 창의 선호 하는 언어 범주에서 **Windows** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-122">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>

4. <span data-ttu-id="ef9da-123">**템플릿** 창에서 **WPF 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-123">In the **Templates** pane, select **WPF Application**.</span></span>

5. <span data-ttu-id="ef9da-124">**이름** 상자에을 입력 `UsingWorkflowItemPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-124">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>

6. <span data-ttu-id="ef9da-125">**위치** 상자에 프로젝트를 저장할 디렉터리를 입력 하거나 **찾아보기** 를 클릭 하 여 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-125">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>

7. <span data-ttu-id="ef9da-126">**솔루션** 상자에서 기본값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-126">In the **Solution** box, accept the default value.</span></span>

8. <span data-ttu-id="ef9da-127">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-127">Click **OK**.</span></span>

9. <span data-ttu-id="ef9da-128">**솔루션 탐색기**에서 *mainwindows .xaml* 파일을 마우스 오른쪽 단추로 클릭 하 고 **삭제** 를 선택 하 고 **Microsoft Visual Studio** 대화 상자에서 **확인** 을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-128">Right-click the *MainWindows.xaml* file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialog box.</span></span>

10. <span data-ttu-id="ef9da-129">**솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목** ...을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-129">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="ef9da-130">**새 항목 추가** 대화 상자를 표시 하 고 왼쪽의 **설치 된 템플릿** 섹션에서 **WPF** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-130">to bring up the **Add New Item** dialog and select the **WPF** category from the **Installed Templates** section on the left.</span></span>

11. <span data-ttu-id="ef9da-131">**창 (WPF)** 템플릿을 선택 하 고 이름을 `RehostingWFDesigner`로 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-131">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>

12. <span data-ttu-id="ef9da-132">*Rehostingwfdesigner.xaml* 파일을 열고 다음 코드를 붙여 넣어 응용 프로그램의 UI를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-132">Open the *RehostingWFDesigner.xaml* file and paste the following code into it to define the UI for the application:</span></span>

    ```xaml
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"
            xmlns:sys="clr-namespace:System;assembly=mscorlib"
            Title="Window1" Height="600" Width="900">
        <Window.Resources>
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>
        </Window.Resources>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="2*"/>
                <ColumnDefinition Width="7*"/>
                <ColumnDefinition Width="3*"/>
            </Grid.ColumnDefinitions>
            <Border Grid.Column="0">
                <sapt:ToolboxControl Name="Toolbox">
                    <sapt:ToolboxCategory CategoryName="Basic">
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.Sequence
                            </sapt:ToolboxItemWrapper.ToolName>
                           </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.WriteLine
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.If
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.While
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                    </sapt:ToolboxCategory>
                </sapt:ToolboxControl>
            </Border>
            <Border Grid.Column="1" Name="DesignerBorder"/>
            <Border Grid.Column="2" Name="PropertyBorder"/>
        </Grid>
    </Window>
    ```

13. <span data-ttu-id="ef9da-133">활동 유형에 활동 디자이너를 연결하려면 메타데이터 저장소에 해당 활동 디자이너를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-133">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="ef9da-134">이렇게 하려면 `RegisterMetadata` 메서드를 `RehostingWFDesigner` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-134">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="ef9da-135">`RegisterMetadata` 메서드의 범위 내에 <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> 개체를 만들고 <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> 메서드를 호출하여 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-135">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="ef9da-136"><xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> 메서드를 호출하여 <xref:System.Activities.Presentation.Metadata.AttributeTable>을 메타데이터 저장소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-136">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="ef9da-137">다음 코드에는 디자이너의 재호스팅 논리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-137">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="ef9da-138">이 코드는 메타데이터를 등록하고 `SimpleNativeActivity`를 도구 상자에 넣고 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-138">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="ef9da-139">이 코드를 *RehostingWFDesigner.xaml.cs* 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-139">Put this code into the *RehostingWFDesigner.xaml.cs* file.</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Presentation.Toolbox;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespace UsingWorkflowItemPresenter
    {
        // Interaction logic for RehostingWFDesigner.xaml
        public partial class RehostingWFDesigner
        {
            public RehostingWFDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. <span data-ttu-id="ef9da-140">솔루션 탐색기에서 참조 디렉터리를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** ...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-140">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="ef9da-141">**참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-141">to bring up the **Add Reference** dialog.</span></span>

15. <span data-ttu-id="ef9da-142">**.Net** 탭을 클릭 하 고 이름이 system.string 인 **어셈블리를 찾아**선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-142">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>

16. <span data-ttu-id="ef9da-143">같은 절차를 사용하여 다음 어셈블리에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-143">Using the same procedure, add references to the following assemblies:</span></span>

    1. <span data-ttu-id="ef9da-144">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="ef9da-144">System.Data.DataSetExtensions.dll</span></span>

    2. <span data-ttu-id="ef9da-145">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="ef9da-145">System.Activities.Presentation.dll</span></span>

    3. <span data-ttu-id="ef9da-146">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ef9da-146">System.ServiceModel.Activities.dll</span></span>

17. <span data-ttu-id="ef9da-147">*App.xaml* 파일을 열고 startupuri의 값을 "rehostingwfdesigner.xaml"로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-147">Open the *App.xaml* file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>

18. <span data-ttu-id="ef9da-148">**솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목** ...을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-148">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="ef9da-149">**새 항목 추가** 대화 상자를 표시 하 고 왼쪽의 **설치 된 템플릿** 섹션에서 **워크플로** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-149">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

19. <span data-ttu-id="ef9da-150">**Activity Designer** 템플릿을 선택 하 고 이름을 `SimpleNativeDesigner`로 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-150">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>

20. <span data-ttu-id="ef9da-151">*SimpleNativeDesigner* 파일을 열고 다음 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-151">Open the *SimpleNativeDesigner.xaml* file and paste the following code into it.</span></span> <span data-ttu-id="ef9da-152">이 코드에서는 <xref:System.Activities.Presentation.ActivityDesigner>를 루트 요소로 사용하고 복합 활동 디자이너에서 자식 형식을 표시할 수 있도록 바인딩을 사용하여 <xref:System.Activities.Presentation.WorkflowItemPresenter>를 디자이너에 통합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-152">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef9da-153"><xref:System.Activities.Presentation.ActivityDesigner>의 스키마를 사용하면 사용자 지정 활동 디자이너 정의에 자식 요소를 하나만 추가할 수 있지만, `StackPanel`, `Grid` 또는 다른 복합 UI 요소 중에서 선택하여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-153">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <StackPanel>
                    <TextBlock>This is the collapsed view</TextBlock>
                </StackPanel>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock>Custom Text</TextBlock>
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                            HintText="Please drop an activity here" />
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
        </Grid>
    </sap:ActivityDesigner>
    ```

21. <span data-ttu-id="ef9da-154">**솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목** ...을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-154">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="ef9da-155">**새 항목 추가** 대화 상자를 표시 하 고 왼쪽의 **설치 된 템플릿** 섹션에서 **워크플로** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-155">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

22. <span data-ttu-id="ef9da-156">**코드 활동** 템플릿을 선택 하 고 이름을 `SimpleNativeActivity`로 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-156">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>

23. <span data-ttu-id="ef9da-157">SimpleNativeActivity.cs 파일 `SimpleNativeActivity` 에 다음 코드를 입력 하 여 클래스 를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-157">Implement the `SimpleNativeActivity` class by entering the following code into the *SimpleNativeActivity.cs* file:</span></span>

    ```csharp
    using System.Activities;

    namespace UsingWorkflowItemPresenter
    {
        public sealed class SimpleNativeActivity : NativeActivity
        {
            // this property contains an activity that will be scheduled in the execute method
            // the WorkflowItemPresenter in the designer is bound to this to enable editing
            // of the value
            public Activity Body { get; set; }

            protected override void CacheMetadata(NativeActivityMetadata metadata)
            {
               metadata.AddChild(Body);
               base.CacheMetadata(metadata);

            }

            protected override void Execute(NativeActivityContext context)
            {
                context.ScheduleActivity(Body);
            }
        }
    }
    ```

24. <span data-ttu-id="ef9da-158">**빌드** 메뉴에서 **솔루션 빌드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-158">Select **Build Solution** from the **Build** menu.</span></span>

25. <span data-ttu-id="ef9da-159">**디버그** 메뉴에서 **디버깅 하지 않고 시작** 을 선택 하 여 다시 호스트 된 사용자 지정 디자인 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-159">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="ef9da-160">WorkflowItemsPresenter를 사용하여 사용자 지정 활동 디자이너를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ef9da-160">To create a custom activity designer using WorkflowItemsPresenter</span></span>

1. <span data-ttu-id="ef9da-161">두 번째 사용자 지정 활동 디자이너에 대 한 프로시저는 첫 번째를 수정 하 고 첫 번째는 두 번째 응용 프로그램 `UsingWorkflowItemsPresenter`의 이름을 지정 하는 것과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-161">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="ef9da-162">또한 이 애플리케이션은 새 사용자 지정 활동을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-162">Also this application does not define a new custom activity.</span></span>

2. <span data-ttu-id="ef9da-163">주요 차이점은 *CustomParallelDesigner* 및 *RehostingWFDesigner.xaml.cs* 파일에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-163">Key differences are contained in the *CustomParallelDesigner.xaml* and *RehostingWFDesigner.xaml.cs* files.</span></span> <span data-ttu-id="ef9da-164">다음은 UI를 정의 하는 *CustomParallelDesigner* 파일의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-164">Here is the code from the *CustomParallelDesigner.xaml* file that defines the UI:</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <TextBlock>This is the Collapsed View</TextBlock>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"
                                        Items="{Binding Path=ModelItem.Branches}">
                        <sap:WorkflowItemsPresenter.SpacerTemplate>
                            <DataTemplate>
                                <Ellipse Width="10" Height="10" Fill="Black"/>
                            </DataTemplate>
                        </sap:WorkflowItemsPresenter.SpacerTemplate>
                        <sap:WorkflowItemsPresenter.ItemsPanel>
                            <ItemsPanelTemplate>
                                <StackPanel Orientation="Horizontal"/>
                            </ItemsPanelTemplate>
                        </sap:WorkflowItemsPresenter.ItemsPanel>
                    </sap:WorkflowItemsPresenter>
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
        </Grid>
    </sap:ActivityDesigner>
    ```

3. <span data-ttu-id="ef9da-165">재호스팅 논리를 제공 하는 *RehostingWFDesigner.xaml.cs* 파일의 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9da-165">Here is the code from the *RehostingWFDesigner.xaml.cs* file that provides the rehosting logic:</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespaceUsingWorkflowItemsPresenter
    {
        public partial class RehostingWfDesigner : Window
        {
            public RehostingWfDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="ef9da-166">참조</span><span class="sxs-lookup"><span data-stu-id="ef9da-166">See also</span></span>

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [<span data-ttu-id="ef9da-167">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ef9da-167">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
