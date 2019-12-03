---
title: 디자이너에서 XAML 파일에 추가 하는 뷰 상태 제거-WF
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: f431275140e821aa5ec4d2235322f06be87d5ee2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715615"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="77183-102">디자이너에서 XAML 파일에 추가 하는 뷰 상태 제거</span><span class="sxs-lookup"><span data-stu-id="77183-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="77183-103">이 샘플에서는 <xref:System.Xaml.XamlWriter>에서 파생되며 XAML 파일에서 뷰 상태를 제거하는 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77183-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> <span data-ttu-id="77183-104">Windows 워크플로 디자이너는 뷰 상태 라고 하는 XAML 문서에 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="77183-104">Windows Workflow Designer writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="77183-105">뷰 상태는 런타임에 필요하지 않으며 디자인 타임에 필요한 레이아웃 위치 등과 같은 정보를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="77183-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> <span data-ttu-id="77183-106">워크플로 디자이너이 정보를 XAML 문서를 편집할 때 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-106">Workflow Designer inserts this information into the XAML document as it is edited.</span></span> <span data-ttu-id="77183-107">워크플로 디자이너는 `mc:Ignorable` 특성을 사용 하 여 뷰 상태를 XAML 파일에 쓰며,이 정보는 런타임에서 XAML 파일을 로드할 때 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-107">Workflow Designer writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="77183-108">이 샘플에서는 XAML 노드를 처리하는 동안 이와 같은 뷰 상태 정보를 제거하는 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77183-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="77183-109">토론</span><span class="sxs-lookup"><span data-stu-id="77183-109">Discussion</span></span>

<span data-ttu-id="77183-110">이 샘플에서는 사용자 지정 작성기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77183-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="77183-111">사용자 지정 XAML 작성기를 빌드하려면 <xref:System.Xaml.XamlWriter>에서 상속되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77183-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="77183-112">XAML 작성기가 중첩 되는 경우가 많기 때문에 "내부" XAML 작성기를 추적 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="77183-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="77183-113">이러한 "내부 ' 작성기는 XAML 작성기의 나머지 스택에 대 한 참조로 간주할 수 있습니다 .이를 통해 여러 진입점을 사용 하 여 작업을 수행 하 고 나머지 스택에 처리를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="77183-114">이 샘플에서는 특히 주목해야 할 항목이 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="77183-115">그 중 하나는 기록할 항목이 디자이너 네임스페이스에 속한 것인지 여부를 확인하는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="77183-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="77183-116">이렇게 하면 워크플로의 디자이너 네임스페이스에서 다른 형식을 사용하지 않도록 방지하는 효과도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

<span data-ttu-id="77183-117">또한 이렇게 하면 노드 스트림을 통과하는 동안 사용되는 XAML 멤버의 스택이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="77183-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="77183-118">이 샘플의 나머지 부분은 주로 `WriteStartMember` 메서드에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="77183-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

<span data-ttu-id="77183-119">이후의 메서드에서는 해당 메서드가 여전히 뷰 상태 컨테이너에 포함되어 있는지 여부를 확인하고, 메서드가 뷰 상태 컨테이너에 포함되어 있으면 노드를 작성기 스택에 전달하지 않고 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="77183-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

<span data-ttu-id="77183-120">사용자 지정 XAML 작성기를 사용하려면 이를 XAML 작성기 스택에 함께 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="77183-121">다음 코드에서는 이를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77183-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="77183-122">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="77183-122">To use this sample</span></span>

1. <span data-ttu-id="77183-123">Visual Studio 2010을 사용 하 여 ViewStateCleaningWriter 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77183-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="77183-124">명령 프롬프트를 열고 ViewStageCleaningWriter.exe가 빌드된 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="77183-125">Workflow1.xaml 파일에 대해 ViewStateCleaningWriter.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="77183-126">실행 파일의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="77183-127">그러면 XAML 파일이 \[출력 파일에 출력 되 고 모든 뷰 상태 정보가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77183-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="77183-128"><xref:System.Activities.Statements.Sequence> 워크플로의 경우 여러 개의 가상화 힌트도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="77183-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="77183-129">따라서 다음 번 로드 시 디자이너를 통해 레이아웃이 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="77183-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="77183-130"><xref:System.Activities.Statements.Flowchart>에 대해 이 샘플을 사용하면 위치 및 선 라우팅 정보가 모두 제거되며, 이를 다음 번에 디자이너로 다시 로드하면 모든 활동이 화면 왼쪽에 쌓입니다.</span><span class="sxs-lookup"><span data-stu-id="77183-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="77183-131">이 샘플과 함께 사용할 샘플 XAML 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="77183-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="77183-132">Visual Studio 2010을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77183-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="77183-133">새 워크플로 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77183-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="77183-134">몇 가지 활동을 끌어 캔버스에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="77183-135">워크플로 XAML 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="77183-136">XAML 파일을 조사하여 속성에 연결된 뷰 상태가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77183-137">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="77183-138">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="77183-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="77183-139">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="77183-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="77183-140">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77183-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
