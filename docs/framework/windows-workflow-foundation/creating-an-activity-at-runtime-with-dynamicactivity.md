---
title: 동적 활동을 사용하여 런타임에 활동 만들기
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 871108fd09e9127b3f9e06174f05a47c7fd7682c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182988"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="4ebf2-102">동적 활동을 사용하여 런타임에 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="4ebf2-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="4ebf2-103"><xref:System.Activities.DynamicActivity>는 public 생성자를 사용하는 구체적이고 봉인된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="4ebf2-104"><xref:System.Activities.DynamicActivity>는 활동 DOM을 통해 런타임에 활동 기능을 어셈블하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="4ebf2-105">DynamicActivity 기능</span><span class="sxs-lookup"><span data-stu-id="4ebf2-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="4ebf2-106"><xref:System.Activities.DynamicActivity>는 실행 속성, 인수 및 변수에 대한 액세스 권한이 있지만 자식 활동 예약, 추적 등과 같은 런타임 서비스에 대한 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="4ebf2-107">워크플로 <xref:System.Activities.Argument> 개체를 사용하여 최상위 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="4ebf2-108">명령적 코드에서는 새로운 형식의 CLR 속성을 사용하여 이러한 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="4ebf2-109">XAML에서는 `x:Class` 및 `x:Member` 태그를 사용하여 이러한 인수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="4ebf2-110"><xref:System.Activities.DynamicActivity>를 사용하여 구성된 활동은 <xref:System.ComponentModel.ICustomTypeDescriptor>를 사용하여 디자이너에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="4ebf2-111">다음 절차에 설명된 것처럼 디자이너에서 만든 활동은 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>를 사용하여 동적으로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="4ebf2-112">명령적 코드를 사용하여 런타임에 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4ebf2-112">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="4ebf2-113">오픈 비주얼 스튜디오 2010.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-113">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="4ebf2-114">**파일,** **새로,** **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="4ebf2-115">**프로젝트 유형** 창에서 **시각적 C#에서** **워크플로 4.0을** 선택하고 **v2010** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="4ebf2-116">템플릿 창에서 **순차 적 워크플로 콘솔 응용 프로그램을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ebf2-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="4ebf2-117">새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-117">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="4ebf2-118">HelloActivity 프로젝트에서 Workflow1.xaml을 마우스 오른쪽 단추로 클릭하고 **삭제를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="4ebf2-119">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-119">Open Program.cs.</span></span> <span data-ttu-id="4ebf2-120">다음 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-120">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="4ebf2-121">`Main` 메서드의 내용을 다음 코드로 바꿉니다. 이 코드는 단일 <xref:System.Activities.Statements.Sequence> 활동을 포함하는 <xref:System.Activities.Statements.WriteLine> 활동을 만든 다음 새 동적 활동의 <xref:System.Activities.DynamicActivity.Implementation%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
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
  
6. <span data-ttu-id="4ebf2-122">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-122">Execute the application.</span></span> <span data-ttu-id="4ebf2-123">"Hello World!" 텍스트가 있는 콘솔 창입니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="4ebf2-124">표시.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="4ebf2-125">XAML을 사용하여 런타임에 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4ebf2-125">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="4ebf2-126">오픈 비주얼 스튜디오 2010.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-126">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="4ebf2-127">**파일,** **새로,** **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="4ebf2-128">**프로젝트 유형** 창에서 **시각적 C#에서** **워크플로 4.0을** 선택하고 **v2010** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="4ebf2-129">템플릿 창에서 **워크플로 콘솔 응용 프로그램을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ebf2-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="4ebf2-130">새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-130">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="4ebf2-131">HelloActivity 프로젝트에서 Workflow1.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="4ebf2-132">디자이너 하단의 인수 옵션을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ebf2-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="4ebf2-133">`In` 형식의 `TextToWrite`라는 새 `String` 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="4ebf2-134">도구 상자의 **기본** 섹션에서 디자이너 표면으로 **WriteLine** 활동을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="4ebf2-135">활동의 Text `TextToWrite` 속성에 **Text** 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="4ebf2-136">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-136">Open Program.cs.</span></span> <span data-ttu-id="4ebf2-137">다음 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-137">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="4ebf2-138">`Main` 메서드의 내용을 다음 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="4ebf2-139">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-139">Execute the application.</span></span> <span data-ttu-id="4ebf2-140">"Hello World!" 텍스트가 있는 콘솔 창입니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="4ebf2-141">이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-141">appears.</span></span>  
  
8. <span data-ttu-id="4ebf2-142">**솔루션 탐색기에서** Workflow1.xaml 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="4ebf2-143">활동 클래스가 `x:Class`를 사용하여 만들어지고 속성은 `x:Property`를 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4ebf2-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebf2-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ebf2-144">See also</span></span>

- [<span data-ttu-id="4ebf2-145">명령형 코드를 사용하여 워크플로, 활동 및 식 작성</span><span class="sxs-lookup"><span data-stu-id="4ebf2-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
