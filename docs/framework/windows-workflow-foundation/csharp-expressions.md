---
title: C# 식
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: b0e5d7f2fbb1f7b84c6d8f0110bd111165f0ea52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239629"
---
# <a name="c-expressions"></a><span data-ttu-id="e9599-102">C# 식</span><span class="sxs-lookup"><span data-stu-id="e9599-102">C# Expressions</span></span>

<span data-ttu-id="e9599-103">.NET Framework 4.5부터 c # 식은 WF (Windows Workflow Foundation)에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-103">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="e9599-104">.NET Framework 4.5를 대상으로 하는 Visual Studio 2012에서 만든 새 c # 워크플로 프로젝트는 c # 식을 사용 하 고 Visual Basic 워크플로 프로젝트는 Visual Basic 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-104">New C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="e9599-105">Visual Basic 식을 사용 하는 기존 .NET Framework 4 워크플로 프로젝트는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 프로젝트 언어와 관계 없이로 마이그레이션할 수 있으며 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-105">Existing .NET Framework 4 workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="e9599-106">이 항목에서는 [!INCLUDE[wf1](../../../includes/wf1-md.md)]의 C# 식에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="e9599-107">워크플로에서 C# 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="e9599-108">Workflow Designer에서 C# 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

  - [<span data-ttu-id="e9599-109">이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="e9599-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="e9599-110">코드 워크플로에서 C# 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="e9599-111">XAML 워크플로에서 C# 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

  - [<span data-ttu-id="e9599-112">컴파일된 XAML</span><span class="sxs-lookup"><span data-stu-id="e9599-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

  - [<span data-ttu-id="e9599-113">느슨한 Xaml</span><span class="sxs-lookup"><span data-stu-id="e9599-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="e9599-114">XAMLX 워크플로 서비스에서 C# 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="using-c-expressions-in-the-workflow-designer"></a><a name="WFDesigner"></a> <span data-ttu-id="e9599-115">워크플로 디자이너에서 c # 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-115">Using C# expressions in the Workflow Designer</span></span>

<span data-ttu-id="e9599-116">.NET Framework 4.5부터 c # 식은 WF (Windows Workflow Foundation)에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-116">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="e9599-117">.NET Framework 4.5를 대상으로 하는 Visual Studio 2012에서 만든 c # 워크플로 프로젝트는 c # 식을 사용 하는 반면 Visual Basic 워크플로 프로젝트는 Visual Basic 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-117">C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="e9599-118">원하는 c # 식을 지정 하려면 **c # 식 입력** 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="e9599-119">이 레이블은 디자이너에서 활동이 선택된 경우 속성 창에 표시되거나 워크플로 디자이너의 활동에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="e9599-120">다음 예제에서는 `WriteLine`의 `Sequence` 내에 두 개의 `NoPersistScope` 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

![자동으로 만들어진 시퀀스 활동을 보여 주는 스크린샷](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> <span data-ttu-id="e9599-122">C # 식은 Visual Studio 에서만 지원 되며 다시 호스트 된 workflow designer에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="e9599-123">다시 호스트 된 디자이너에서 지원 되는 새로운 WF45 기능에 대 한 자세한 내용은 [rehosted 워크플로 디자이너의 새로운 Workflow Foundation 4.5 기능 지원](wf-features-in-the-rehosted-workflow-designer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9599-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="backwards-compatibility"></a><a name="BackwardCompat"></a> <span data-ttu-id="e9599-124">이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="e9599-124">Backwards compatibility</span></span>

<span data-ttu-id="e9599-125">로 마이그레이션된 기존 .NET Framework 4 c # 워크플로 프로젝트의 Visual Basic 식이 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-125">Visual Basic expressions in existing .NET Framework 4 C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="e9599-126">워크플로 디자이너에서 Visual Basic 식을 볼 때 Visual Basic 식이 유효한 c # 구문이 아니면 기존 Visual Basic 식의 텍스트가 **Value** 로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="e9599-127">Visual Basic 식이 유효한 C# 구문인 경우에는 해당 식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="e9599-128">Visual Basic 식을 C#으로 업데이트하려면 워크플로 디자이너에서 식을 편집하고 해당하는 C#식을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="e9599-129">Visual Basic 식을 반드시 C#으로 업데이트할 필요는 없지만, Workflow Designer에서 식을 업데이트한 후에는 식이 C#으로 변환되며 이를 Visual Basic으로 되돌릴 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="using-c-expressions-in-code-workflows"></a><a name="CodeWorkflows"></a> <span data-ttu-id="e9599-130">코드 워크플로에서 c # 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-130">Using C# expressions in code workflows</span></span>

<span data-ttu-id="e9599-131">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 코드 기반 워크플로에서는 C# 식이 지원되지만 워크플로를 호출하려면 먼저 <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>을 사용하여 C# 식을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9599-132">워크플로 작성자는 `CSharpValue`를 사용하여 식의 r-value를 나타내고 `CSharpReference`를 사용하여 식의 l-value를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="e9599-133">다음 예제에서는 `Assign` 활동에 포함된 `WriteLine` 활동과 `Sequence` 활동으로 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="e9599-134">`CSharpReference`의 `To` 인수에는 `Assign`가 지정되어 식의 l-value를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="e9599-135">`CSharpValue`의 `Value` 인수와 `Assign`의 `Text` 인수에는 `WriteLine`가 지정되어 이 두 식의 r-value를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

<span data-ttu-id="e9599-136">워크플로가 생성된 후에는 `CompileExpressions` 도우미 메서드를 호출하여 C# 식을 컴파일한 다음 워크플로를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="e9599-137">다음 예제는 `CompileExpressions` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-137">The following example is the `CompileExpressions` method.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
> <span data-ttu-id="e9599-138">C # 식이 컴파일되지 않은 경우 다음과 <xref:System.NotSupportedException> 유사한 메시지를 사용 하 여 워크플로를 호출할 때이 throw 됩니다. `Expression Activity type 'CSharpValue` 1 '를 실행 하려면 컴파일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="e9599-139">워크플로가 컴파일 되었는지 확인 하세요. '</span><span class="sxs-lookup"><span data-stu-id="e9599-139">Please ensure that the workflow has been compiled.\`</span></span>

<span data-ttu-id="e9599-140">사용자 지정 코드 기반 워크플로에서 `DynamicActivity`를 사용하는 경우에는 다음 코드 예제와 같이 `CompileExpressions` 메서드를 일부 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

<span data-ttu-id="e9599-141">동적 활동에서 C# 식을 컴파일하는 `CompileExpressions` 오버로드에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="e9599-142">`CompileExpressions`에 대한 매개 변수는 `DynamicActivity`입니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="e9599-143">형식 이름 및 네임스페이스는 `DynamicActivity.Name` 속성을 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="e9599-144">`TextExpressionCompilerSettings.ForImplementation`이 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="e9599-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` 대신 `CompiledExpressionInvoker.SetCompiledExpressionRoot`이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

<span data-ttu-id="e9599-146">코드에서 식 사용에 대 한 자세한 내용은 [명령 코드를 사용 하 여 워크플로, 활동 및 식 작성](authoring-workflows-activities-and-expressions-using-imperative-code.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9599-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="using-c-expressions-in-xaml-workflows"></a><a name="XamlWorkflows"></a> <span data-ttu-id="e9599-147">XAML 워크플로에서 c # 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-147">Using C# expressions in XAML workflows</span></span>

<span data-ttu-id="e9599-148">XAML 워크플로에서는 C# 식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="e9599-149">컴파일된 XAML 워크플로는 형식으로 컴파일되고, 느슨한 XAML 워크플로는 런타임에 의해 로드된 후 워크플로가 실행될 때 활동 트리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="e9599-150">컴파일된 XAML</span><span class="sxs-lookup"><span data-stu-id="e9599-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="e9599-151">느슨한 Xaml</span><span class="sxs-lookup"><span data-stu-id="e9599-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="compiled-xaml"></a><a name="CompiledXaml"></a> <span data-ttu-id="e9599-152">컴파일된 Xaml</span><span class="sxs-lookup"><span data-stu-id="e9599-152">Compiled Xaml</span></span>

<span data-ttu-id="e9599-153">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]를 대상으로 하는 C# 워크플로 프로젝트의 일부로서 형식으로 컴파일되는 컴파일된 XAML 워크플로에서는 C# 식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="e9599-154">컴파일된 XAML은 Visual Studio에서 워크플로를 제작 하는 기본 형식이 며 Visual Studio에서 만든 c # 워크플로 프로젝트는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] c # 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="loose-xaml"></a><a name="LooseXaml"></a> <span data-ttu-id="e9599-155">느슨한 Xaml</span><span class="sxs-lookup"><span data-stu-id="e9599-155">Loose Xaml</span></span>

<span data-ttu-id="e9599-156">느슨한 XAML 워크플로에서는 C# 식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="e9599-157">느슨한 XAML 워크플로를 로드 및 호출하는 워크플로 호스트 프로그램은 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]를 대상으로 하며, <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>는 `true`로 설정되어야 합니다(기본값 `false`).</span><span class="sxs-lookup"><span data-stu-id="e9599-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="e9599-158"><xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>를 `true`로 설정하려면 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> 속성을 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>로 설정하여 `true` 인스턴스를 만든 후 이를 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>에 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9599-159">`CompileExpressions`가로 설정 되어 있지 않으면 다음과 `true` <xref:System.NotSupportedException> 유사한 메시지와 함께이 throw 됩니다. `Expression Activity type 'CSharpValue` 1 ' 실행 하려면 컴파일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="e9599-160">워크플로가 컴파일 되었는지 확인 하세요. '</span><span class="sxs-lookup"><span data-stu-id="e9599-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="e9599-161">XAML 워크플로 작업에 대 한 자세한 내용은 [xaml로 워크플로 및 활동 직렬화](serializing-workflows-and-activities-to-and-from-xaml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9599-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="using-c-expressions-in-xamlx-workflow-services"></a><a name="WFServices"></a> <span data-ttu-id="e9599-162">.XAMLX workflow services에서 c # 식 사용</span><span class="sxs-lookup"><span data-stu-id="e9599-162">Using C# expressions in XAMLX workflow services</span></span>

<span data-ttu-id="e9599-163">XAMLX 워크플로 서비스에서는 C# 식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="e9599-164">워크플로 서비스가 IIS 또는 WAS에서 호스트되는 경우에는 추가 단계가 필요하지 않지만, XAML 워크플로 서비스가 자체 호스트되는 경우 C# 식을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="e9599-165">자체 호스팅 .XAMLX 워크플로 서비스에서 c # 식을 컴파일하려면 먼저 .XAMLX 파일을에 로드 한 `WorkflowService` 다음 `Body` 의를 앞의 `WorkflowService` `CompileExpressions` [코드 워크플로에서 c # 식 사용](csharp-expressions.md#CodeWorkflows) 섹션에서 설명한 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="e9599-166">다음 예제에서는 XAMLX 워크플로 서비스를 로드하고 C# 식을 컴파일한 다음 워크플로 서비스를 열고 요청을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

<span data-ttu-id="e9599-167">C# 식이 컴파일되지 않은 경우 `Open` 작업이 성공하지만 워크플로 호출에는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="e9599-168">다음 `CompileExpressions` 메서드는 앞의 [코드 워크플로에서 c # 식 사용](csharp-expressions.md#CodeWorkflows) 섹션의 메서드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9599-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
