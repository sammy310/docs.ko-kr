---
title: 동적 활동을 사용하여 런타임에 활동 만들기
description: DynamicActivity는 public 생성자를 사용 하는 구체적이 고 봉인 된 클래스입니다. 활동 DOM을 사용 하 여 런타임에 활동 기능을 어셈블하는 클래스를 사용 합니다.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: b65d7e385690b77d44c73e7a8a4ed38b04f30ea6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242099"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="6d12a-104">동적 활동을 사용하여 런타임에 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="6d12a-104">Creating an Activity at Runtime with DynamicActivity</span></span>

<span data-ttu-id="6d12a-105"><xref:System.Activities.DynamicActivity>는 public 생성자를 사용하는 구체적이고 봉인된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-105"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="6d12a-106"><xref:System.Activities.DynamicActivity>는 활동 DOM을 통해 런타임에 활동 기능을 어셈블하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-106"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="6d12a-107">DynamicActivity 기능</span><span class="sxs-lookup"><span data-stu-id="6d12a-107">DynamicActivity Features</span></span>  

 <span data-ttu-id="6d12a-108"><xref:System.Activities.DynamicActivity>는 실행 속성, 인수 및 변수에 대한 액세스 권한이 있지만 자식 활동 예약, 추적 등과 같은 런타임 서비스에 대한 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-108"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="6d12a-109">워크플로 <xref:System.Activities.Argument> 개체를 사용하여 최상위 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-109">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="6d12a-110">명령적 코드에서는 새로운 형식의 CLR 속성을 사용하여 이러한 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-110">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="6d12a-111">XAML에서는 `x:Class` 및 `x:Member` 태그를 사용하여 이러한 인수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-111">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="6d12a-112"><xref:System.Activities.DynamicActivity>를 사용하여 구성된 활동은 <xref:System.ComponentModel.ICustomTypeDescriptor>를 사용하여 디자이너에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-112">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="6d12a-113">다음 절차에 설명된 것처럼 디자이너에서 만든 활동은 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>를 사용하여 동적으로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-113">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="6d12a-114">명령적 코드를 사용하여 런타임에 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6d12a-114">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="6d12a-115">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="6d12a-115">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="6d12a-116">**파일**, **새로 만들기**, **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-116">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6d12a-117">**프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-117">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6d12a-118">**템플릿** 창에서 **순차 워크플로 콘솔 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-118">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6d12a-119">새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-119">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="6d12a-120">HelloActivity 프로젝트에서 Workflow1.vb를 마우스 오른쪽 단추로 클릭 하 고 **삭제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-120">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="6d12a-121">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-121">Open Program.cs.</span></span> <span data-ttu-id="6d12a-122">다음 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-122">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="6d12a-123">`Main` 메서드의 내용을 다음 코드로 바꿉니다. 이 코드는 단일 <xref:System.Activities.Statements.Sequence> 활동을 포함하는 <xref:System.Activities.Statements.WriteLine> 활동을 만든 다음 새 동적 활동의 <xref:System.Activities.DynamicActivity.Implementation%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-123">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="6d12a-124">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-124">Execute the application.</span></span> <span data-ttu-id="6d12a-125">"Hello World!" 텍스트를 포함 하는 콘솔 창</span><span class="sxs-lookup"><span data-stu-id="6d12a-125">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6d12a-126">표시.</span><span class="sxs-lookup"><span data-stu-id="6d12a-126">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="6d12a-127">XAML을 사용하여 런타임에 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6d12a-127">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="6d12a-128">Visual Studio 2010을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-128">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="6d12a-129">**파일**, **새로 만들기**, **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-129">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6d12a-130">**프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-130">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6d12a-131">**템플릿** 창에서 **워크플로 콘솔 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-131">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6d12a-132">새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-132">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="6d12a-133">HelloActivity 프로젝트에서 Workflow1.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-133">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="6d12a-134">디자이너 아래쪽에 있는 **인수** 옵션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-134">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="6d12a-135">`In` 형식의 `TextToWrite`라는 새 `String` 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-135">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="6d12a-136">도구 상자의 **기본 형식** 섹션에서 **WriteLine** 활동을 디자이너 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-136">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="6d12a-137">`TextToWrite`활동의 **Text** 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-137">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="6d12a-138">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-138">Open Program.cs.</span></span> <span data-ttu-id="6d12a-139">다음 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-139">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="6d12a-140">`Main` 메서드의 콘텐츠를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-140">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="6d12a-141">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-141">Execute the application.</span></span> <span data-ttu-id="6d12a-142">"Hello World!" 텍스트를 포함 하는 콘솔 창</span><span class="sxs-lookup"><span data-stu-id="6d12a-142">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6d12a-143">이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-143">appears.</span></span>  
  
8. <span data-ttu-id="6d12a-144">**솔루션 탐색기** 에서 workflow1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-144">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="6d12a-145">활동 클래스가 `x:Class`를 사용하여 만들어지고 속성은 `x:Property`를 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d12a-145">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d12a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d12a-146">See also</span></span>

- [<span data-ttu-id="6d12a-147">명령 코드를 사용하여 워크플로, 활동 및 식 작성</span><span class="sxs-lookup"><span data-stu-id="6d12a-147">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
