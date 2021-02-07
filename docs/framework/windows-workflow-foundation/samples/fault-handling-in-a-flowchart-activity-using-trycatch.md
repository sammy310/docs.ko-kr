---
description: '자세히 알아보기: TryCatch를 사용 하 여 Flowchart 활동의 오류 처리'
title: Flowchart 활동에서 TryCatch를 사용하여 오류 처리
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 9ab323117e5b26696a07624117e8acc8c0beacff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755348"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="18ac6-103">Flowchart 활동에서 TryCatch를 사용하여 오류 처리</span><span class="sxs-lookup"><span data-stu-id="18ac6-103">Fault Handling in a Flowchart Activity Using TryCatch</span></span>

<span data-ttu-id="18ac6-104">이 샘플에서는 복잡한 제어 흐름 활동 내에서 <xref:System.Activities.Statements.TryCatch> 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-104">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

<span data-ttu-id="18ac6-105">이 샘플에서는 승격 코드에 해당하는 식을 기반으로 할인율을 계산하는 <xref:System.Activities.Statements.Flowchart> 활동에 승격 코드와 자식 수를 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-105">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="18ac6-106">이 샘플에는 샘플의 명령적 코드 및 워크플로 디자이너 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-106">The sample includes imperative code and workflow designer versions of the sample.</span></span>

<span data-ttu-id="18ac6-107">다음 표에서는 `CreateFlowchartWithFaults` 활동의 변수에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-107">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="18ac6-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18ac6-108">Parameters</span></span>|<span data-ttu-id="18ac6-109">설명</span><span class="sxs-lookup"><span data-stu-id="18ac6-109">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="18ac6-110">promoCode</span><span class="sxs-lookup"><span data-stu-id="18ac6-110">promoCode</span></span>|<span data-ttu-id="18ac6-111">승격 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-111">The promotion code.</span></span> <span data-ttu-id="18ac6-112">유형: String</span><span class="sxs-lookup"><span data-stu-id="18ac6-112">Type: String</span></span><br /><br /> <span data-ttu-id="18ac6-113">가능한 값은 다음과 같으며 괄호 안에 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-113">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="18ac6-114">-단일 (단일)</span><span class="sxs-lookup"><span data-stu-id="18ac6-114">-   Single (Single)</span></span><br /><span data-ttu-id="18ac6-115">-MNK (자녀가 없는 결혼)</span><span class="sxs-lookup"><span data-stu-id="18ac6-115">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="18ac6-116">-MWK (어린이와 결혼)</span><span class="sxs-lookup"><span data-stu-id="18ac6-116">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="18ac6-117">numKids</span><span class="sxs-lookup"><span data-stu-id="18ac6-117">numKids</span></span>|<span data-ttu-id="18ac6-118">자식 수입니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-118">The number of children.</span></span> <span data-ttu-id="18ac6-119">형식: int</span><span class="sxs-lookup"><span data-stu-id="18ac6-119">Type: int</span></span>|

<span data-ttu-id="18ac6-120">`CreateFlowchartWithFaults` 활동은 <xref:System.Activities.Statements.FlowSwitch%601> 인수로 전환하고 다음 수식을 사용하여 할인율을 계산하는 `promoCode` 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-120">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="18ac6-121">`promoCode`의 값</span><span class="sxs-lookup"><span data-stu-id="18ac6-121">Value of `promoCode`</span></span>|<span data-ttu-id="18ac6-122">할인(%)</span><span class="sxs-lookup"><span data-stu-id="18ac6-122">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="18ac6-123">Single</span><span class="sxs-lookup"><span data-stu-id="18ac6-123">Single</span></span>|<span data-ttu-id="18ac6-124">10</span><span class="sxs-lookup"><span data-stu-id="18ac6-124">10</span></span>|
|<span data-ttu-id="18ac6-125">MNK</span><span class="sxs-lookup"><span data-stu-id="18ac6-125">MNK</span></span>|<span data-ttu-id="18ac6-126">15</span><span class="sxs-lookup"><span data-stu-id="18ac6-126">15</span></span>|
|<span data-ttu-id="18ac6-127">MWK</span><span class="sxs-lookup"><span data-stu-id="18ac6-127">MWK</span></span>|<span data-ttu-id="18ac6-128">15 + (1 – 1/ `numberOfKids` ) \* 10 **참고:**  잠재적으로이 계산은을 throw 할 수 있습니다 <xref:System.DivideByZeroException> .</span><span class="sxs-lookup"><span data-stu-id="18ac6-128">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="18ac6-129">할인율 계산은 <xref:System.Activities.Statements.TryCatch> 예외를 catch하고 할인율을 0으로 설정하는 <xref:System.DivideByZeroException> 활동에 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-129">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="18ac6-130">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="18ac6-130">To use this sample</span></span>

1. <span data-ttu-id="18ac6-131">Visual Studio 2010을 사용 하 여 FlowchartWithFaultHandling 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-131">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2. <span data-ttu-id="18ac6-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-132">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="18ac6-133">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-133">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18ac6-134">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="18ac6-135">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="18ac6-135">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="18ac6-136">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="18ac6-137">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ac6-137">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a><span data-ttu-id="18ac6-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18ac6-138">See also</span></span>

- [<span data-ttu-id="18ac6-139">순서도 워크플로</span><span class="sxs-lookup"><span data-stu-id="18ac6-139">Flowchart Workflows</span></span>](../flowchart-workflows.md)
- [<span data-ttu-id="18ac6-140">예외</span><span class="sxs-lookup"><span data-stu-id="18ac6-140">Exceptions</span></span>](../exceptions.md)
