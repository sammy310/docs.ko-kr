---
description: '자세히 알아보기: 속성 표 확장성'
title: 속성 표 확장성-WF 샘플
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: 784705146974ffca5cd2e6c21dba722598544771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741811"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="82326-103">속성 표 확장성</span><span class="sxs-lookup"><span data-stu-id="82326-103">Property grid extensibility</span></span>

<span data-ttu-id="82326-104">개발자는 디자이너 내에서 지정된 활동을 선택할 경우 표시되는 속성 표를 사용자 지정할 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="82326-104">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="82326-105">이를 통해 다양한 편집 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-105">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="82326-106">이 샘플에서는 이러한 작업을 수행하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82326-106">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="82326-107">데모</span><span class="sxs-lookup"><span data-stu-id="82326-107">Demonstrates</span></span>

<span data-ttu-id="82326-108">Workflow Designer 속성 표 확장성</span><span class="sxs-lookup"><span data-stu-id="82326-108">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82326-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82326-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="82326-110">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="82326-111">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82326-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-112">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="82326-113">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="82326-113">Discussion</span></span>

<span data-ttu-id="82326-114">개발자는 속성 표 편집기의 인라인 모양을 사용자 지정하거나 고급 편집 화면용으로 표시되는 대화 상자를 제공하여 속성 표를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-114">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="82326-115">이 샘플에 나오는 편집기는 인라인 편집기와 대화 상자 편집기, 이렇게 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-115">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="82326-116">인라인 편집기</span><span class="sxs-lookup"><span data-stu-id="82326-116">Inline editor</span></span>

<span data-ttu-id="82326-117">인라인 편집기 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82326-117">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="82326-118"><xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>에서 파생되는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82326-118">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="82326-119">생성자에서 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> 값은 WPF (Windows Presentation Foundation) 데이터 템플릿을 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-119">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="82326-120">이 값은 XAML 템플릿에 바인딩할 수 있지만 이 샘플에서는 코드를 사용하여 데이터 바인딩을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-120">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="82326-121">데이터 템플릿에는 속성 표에서 렌더링된 항목의 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>에 대한 데이터 컨텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-121">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="82326-122">CustomInlineEditor.cs에 있는 다음 코드에서는 이 컨텍스트가 `Value` 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-122">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- <span data-ttu-id="82326-123">활동과 디자이너는 같은 어셈블리에 있기 때문에 활동 디자이너 특성은 SimpleCodeActivity.cs의 다음 예제와 같이 활동 자체의 정적 생성자에서 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-123">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="82326-124">대화 상자 편집기</span><span class="sxs-lookup"><span data-stu-id="82326-124">Dialog editor</span></span>

<span data-ttu-id="82326-125">대화 상자 편집기 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82326-125">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="82326-126"><xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>에서 파생되는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82326-126">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="82326-127"><xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A>WPF 데이터 템플릿을 사용 하 여 생성자의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-127">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a WPF data template.</span></span> <span data-ttu-id="82326-128">이 값을 XAML로 만들 수 있지만 이 샘플에서는 코드로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82326-128">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="82326-129">데이터 템플릿에는 속성 표에서 렌더링된 항목의 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>에 대한 데이터 컨텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-129">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="82326-130">다음 코드에서는 이 컨텍스트가 `Value` 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-130">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="82326-131">FilePickerEditor.cs에 대화 상자를 발생시키는 단추를 제공하도록 <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton>를 포함하는 것도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-131">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. <span data-ttu-id="82326-132">대화 상자 표시를 처리하도록 디자이너 형식의 <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-132">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="82326-133">이 샘플에서는 기본 <xref:System.Windows.Forms.FileDialog>가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-133">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. <span data-ttu-id="82326-134">활동과 디자이너는 같은 어셈블리에 있기 때문에 활동 디자이너 특성은 SimpleCodeActivity.cs의 다음 예제와 같이 활동 자체의 정적 생성자에서 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="82326-134">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82326-135">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="82326-135">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="82326-136">솔루션을 빌드한 다음 Workflow1.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="82326-136">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="82326-137">**SimpleCodeActivity** 을 도구 상자에서 디자이너 캔버스로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-137">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="82326-138">**SimpleCodeActivity** 를 클릭 한 다음 슬라이더 컨트롤과 파일 선택 컨트롤이 있는 속성 표를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="82326-138">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82326-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82326-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="82326-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="82326-141">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="82326-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82326-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82326-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
