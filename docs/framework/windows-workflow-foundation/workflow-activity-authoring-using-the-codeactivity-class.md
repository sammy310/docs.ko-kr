---
description: '자세히 알아보기: CodeActivity 클래스를 사용 하 여 워크플로 활동 제작'
title: CodeActivity 클래스를 사용하여 워크플로 활동 제작
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 393b6c586a88e876484f6888441d5bb82b4c0dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754916"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="c2e28-103">CodeActivity 클래스를 사용하여 워크플로 활동 제작</span><span class="sxs-lookup"><span data-stu-id="c2e28-103">Workflow Activity Authoring Using the CodeActivity Class</span></span>

<span data-ttu-id="c2e28-104"><xref:System.Activities.CodeActivity>에서 상속하여 만들어진 활동은 <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 재정의하여 기본 명령형 동작을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-104">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="c2e28-105">CodeActivityContext 사용</span><span class="sxs-lookup"><span data-stu-id="c2e28-105">Using CodeActivityContext</span></span>

 <span data-ttu-id="c2e28-106"><xref:System.Activities.CodeActivity.Execute%2A> 형식의 `context` 매개 변수 멤버를 사용하여 <xref:System.Activities.CodeActivityContext> 메서드에서 워크플로 런타임 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-106">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="c2e28-107"><xref:System.Activities.CodeActivityContext>를 통해 사용할 수 있는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-107">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

- <span data-ttu-id="c2e28-108">변수와 인수의 값 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="c2e28-108">Getting and setting the values of variables and arguments.</span></span>

- <span data-ttu-id="c2e28-109"><xref:System.Activities.CodeActivityContext.Track%2A>을 사용하는 사용자 지정 추적 기능</span><span class="sxs-lookup"><span data-stu-id="c2e28-109">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="c2e28-110"><xref:System.Activities.CodeActivityContext.GetProperty%2A>을 사용하여 활동의 실행 속성에 액세스</span><span class="sxs-lookup"><span data-stu-id="c2e28-110">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="c2e28-111">CodeActivity에서 상속되는 사용자 지정 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c2e28-111">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="c2e28-112">Visual Studio 2010을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-112">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="c2e28-113">**파일**, **새로 만들기**, **프로젝트** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-113">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="c2e28-114">**프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-114">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="c2e28-115">**템플릿** 창에서 **활동 라이브러리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-115">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="c2e28-116">새 프로젝트의 이름을 HelloActivity로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-116">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="c2e28-117">HelloActivity 프로젝트에서 Activity1를 마우스 오른쪽 단추로 클릭 하 고 **삭제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-117">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="c2e28-118">HelloActivity 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 선택한 다음 **클래스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-118">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="c2e28-119">새 프로젝트의 이름을 HelloActivity.cs로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-119">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="c2e28-120">HelloActivity.cs 파일에서 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-120">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="c2e28-121">기본 클래스를 클래스 선언에 추가하여 새 클래스를 <xref:System.Activities.CodeActivity>에서 상속하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-121">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="c2e28-122"><xref:System.Activities.CodeActivity.Execute%2A> 메서드를 추가하여 클래스에 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-122">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="c2e28-123"><xref:System.Activities.CodeActivityContext>를 사용하여 추적 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2e28-123">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
