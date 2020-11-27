---
title: Pick 활동 사용
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: df8570a61c7bfbfacc00b0896156135ecf2a0c32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267471"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="54215-102">Pick 활동 사용</span><span class="sxs-lookup"><span data-stu-id="54215-102">Using the Pick Activity</span></span>

<span data-ttu-id="54215-103">이 샘플에서는 <xref:System.Activities.Statements.Pick> 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54215-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="54215-104"><xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 모델링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="54215-105">이는 `switch` 문의 분기 중 하나에서만 실행되는 C# `switch` 문과 비슷한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="54215-106">그러나 값을 기준으로 분기가 실행되는 `switch` 문과 달리 <xref:System.Activities.Statements.Pick> 활동은 활동의 완료 방식을 기준으로 분기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="54215-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="54215-107">이 샘플에서는 지정된 시간 내에 사용자의 이름을 입력하라는 메시지를 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="54215-108">이 샘플의 <xref:System.Activities.Statements.Pick> 활동에는 사용자가 이름을 5초 안에 입력했는지 여부를 기준으로 실행되는 두 개의 분기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="54215-109">사용자가 이름을 5초 안에 입력하면 사용자 지정 `ReadLine` 활동이 포함된 첫째 분기가 실행되고, 사용자가 이름을 5초 안에 입력하지 않으면 <xref:System.Activities.Statements.Delay> 활동이 포함된 둘째 분기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="54215-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="54215-110">사용자가 콘솔에 이름을 입력하고 나면 해당 이름이 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="54215-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="54215-111">이름을 5초 안에 입력하지 않으면 작업 제한 시간이 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="54215-112">데모</span><span class="sxs-lookup"><span data-stu-id="54215-112">Demonstrates</span></span>

 <span data-ttu-id="54215-113"><xref:System.Activities.Statements.Pick> 활동</span><span class="sxs-lookup"><span data-stu-id="54215-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="54215-114">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="54215-114">Discussion</span></span>

 <span data-ttu-id="54215-115">이 샘플에는 디자이너 워크플로와 코딩된 워크플로가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="54215-116">디자이너 워크플로 샘플의 디자이너 버전은 디자이너에서 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54215-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="54215-117">여기에 포함되는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-117">The following files are included:</span></span>

- <span data-ttu-id="54215-118">Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54215-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="54215-119">ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="54215-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="54215-120">Sequence1.xaml: Pick을 사용하는 디자이너를 통해 만들어진 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="54215-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="54215-121">코딩 된 워크플로 샘플의 코딩 된 버전은 디자이너에서 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54215-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="54215-122">여기에 포함되는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-122">The following files are included:</span></span>

- <span data-ttu-id="54215-123">Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54215-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="54215-124">ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="54215-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="54215-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="54215-125">To use this sample</span></span>

1. <span data-ttu-id="54215-126">Visual Studio 2010을 사용 하 여 선택 .sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="54215-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="54215-127">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="54215-128">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54215-129">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="54215-130">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="54215-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="54215-131">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="54215-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="54215-132">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54215-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
