---
description: '자세한 정보: 회사 구매 프로세스'
title: 기업 구매 프로세스
ms.date: 03/30/2017
ms.assetid: a5e57336-4290-41ea-936d-435593d97055
ms.openlocfilehash: c26b1f46f29b7a6ec06acf5d19381b5c8f460433
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787866"
---
# <a name="corporate-purchase-process"></a><span data-ttu-id="7fbef-103">기업 구매 프로세스</span><span class="sxs-lookup"><span data-stu-id="7fbef-103">Corporate Purchase Process</span></span>

<span data-ttu-id="7fbef-104">이 샘플에서는 최상의 제안을 자동으로 선택하는 구매 프로세스를 기반으로 매우 기본적인 RFP(제안 요청서)를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-104">This sample shows how to create a very basic Request for Proposals (RFP) based purchase process with automatic best proposal selection.</span></span> <span data-ttu-id="7fbef-105">여기에서는 <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601> 및 <xref:System.Activities.Statements.ForEach%601>과 사용자 지정 활동을 결합하여 이 프로세스를 나타내는 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-105">It combines <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601>, and <xref:System.Activities.Statements.ForEach%601> and a custom activity to create a workflow that represents the process.</span></span>

 <span data-ttu-id="7fbef-106">이 샘플에는 다른 참여자 (원래 요청자 또는 특정 공급 업체)로 프로세스와 상호 작용할 수 있도록 하는 ASP.NET 클라이언트 응용 프로그램이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-106">This sample contains an ASP.NET client application that allows interacting with the process as different participants (as the original requester or a particular vendor).</span></span>

## <a name="requirements"></a><span data-ttu-id="7fbef-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fbef-107">Requirements</span></span>

- <span data-ttu-id="7fbef-108">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="7fbef-108">Visual Studio 2012.</span></span>

- [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="7fbef-109">.</span><span class="sxs-lookup"><span data-stu-id="7fbef-109">.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7fbef-110">데모</span><span class="sxs-lookup"><span data-stu-id="7fbef-110">Demonstrates</span></span>

- <span data-ttu-id="7fbef-111">사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="7fbef-111">Custom activities.</span></span>

- <span data-ttu-id="7fbef-112">활동의 컴퍼지션</span><span class="sxs-lookup"><span data-stu-id="7fbef-112">Composition of activities.</span></span>

- <span data-ttu-id="7fbef-113">책갈피</span><span class="sxs-lookup"><span data-stu-id="7fbef-113">Bookmarks.</span></span>

- <span data-ttu-id="7fbef-114">지속성</span><span class="sxs-lookup"><span data-stu-id="7fbef-114">Persistence.</span></span>

- <span data-ttu-id="7fbef-115">스키마화된 지속성</span><span class="sxs-lookup"><span data-stu-id="7fbef-115">Schematized persistence.</span></span>

- <span data-ttu-id="7fbef-116">추적(Tracing)</span><span class="sxs-lookup"><span data-stu-id="7fbef-116">Tracing.</span></span>

- <span data-ttu-id="7fbef-117">추적(Tracking)</span><span class="sxs-lookup"><span data-stu-id="7fbef-117">Tracking.</span></span>

- <span data-ttu-id="7fbef-118">[!INCLUDE[wf1](../../../../includes/wf1-md.md)]다른 클라이언트 (ASP.NET 웹 응용 프로그램 및 WinForms 응용 프로그램)에서 호스팅.</span><span class="sxs-lookup"><span data-stu-id="7fbef-118">Hosting [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in different clients (ASP.NET Web applications and WinForms applications).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fbef-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7fbef-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbef-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7fbef-121">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7fbef-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\PurchaseProcess`  
  
## <a name="description-of-the-process"></a><span data-ttu-id="7fbef-123">프로세스 설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-123">Description of the Process</span></span>  

 <span data-ttu-id="7fbef-124">이 샘플에서는 일반 회사를 위한 공급 업체의 제안을 수집 하는 WF (Windows Workflow Foundation) 프로그램의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-124">This sample shows an implementation of a Windows Workflow Foundation (WF) program to gather proposals from vendors for a generic company.</span></span>  
  
1. <span data-ttu-id="7fbef-125">X라는 회사의 직원이 RFP(제안 요청서)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-125">An employee of Company X creates a Request for Proposal (RFP).</span></span>  
  
    1. <span data-ttu-id="7fbef-126">이 직원이 RFP 제목과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-126">The employee types in the RFP title and description.</span></span>  
  
    2. <span data-ttu-id="7fbef-127">직원은 제안을 제출 하기 위해 초대 하려는 공급 업체를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-127">The employee selects the vendors that they want to invite to submit proposals.</span></span>  
  
2. <span data-ttu-id="7fbef-128">직원이 제안서를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-128">The employee submits the proposal.</span></span>  
  
    1. <span data-ttu-id="7fbef-129">워크플로의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-129">An instance of the workflow is created.</span></span>  
  
    2. <span data-ttu-id="7fbef-130">모든 공급업체에서 제안서를 제출할 때까지 워크플로가 대기 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-130">The workflow is waiting for all vendors to submit their proposals.</span></span>  
  
3. <span data-ttu-id="7fbef-131">제안서를 모두 받고 나면 접수된 모든 제안서를 하나씩 돌아가며 워크플로를 실행하고 최상의 제안서 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-131">After all proposals are received, the workflow iterates through all the received proposals and selects the best one.</span></span>  
  
    1. <span data-ttu-id="7fbef-132">각 공급업체에는 저마다의 평판이 있습니다. 이 샘플에서는 평판 목록을 VendorRepository.cs에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-132">Each vendor has a reputation (this sample stores the reputation list in VendorRepository.cs).</span></span>  
  
    2. <span data-ttu-id="7fbef-133">제안서의 최종 금액은 (공급업체가 제시한 금액) \* (공급업체에 대해 기록된 평판) / 100으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-133">The total value of the proposal is determined by (The value typed in by the vendor) \* (The vendor's recorded reputation) / 100.</span></span>  
  
4. <span data-ttu-id="7fbef-134">맨 처음 요청자는 제출된 제안서를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-134">The original requester can see all the submitted proposals.</span></span> <span data-ttu-id="7fbef-135">최상의 제안이 보고서의 특정 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-135">The best proposal is presented in a special section in the report.</span></span>  
  
## <a name="process-definition"></a><span data-ttu-id="7fbef-136">프로세스 정의</span><span class="sxs-lookup"><span data-stu-id="7fbef-136">Process Definition</span></span>  

 <span data-ttu-id="7fbef-137">이 샘플의 핵심 논리에는 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 사용됩니다. 이 활동에서는 책갈피를 만드는 사용자 지정 활동을 사용하여 각 공급업체의 제안서를 기다린 다음 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 공급업체 제안서를 RFP로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-137">The core logic of the sample uses a <xref:System.Activities.Statements.ParallelForEach%601> activity that waits for the offers from each vendor (using a custom activity that creates a bookmark), and registers the vendor proposal as an RFP (using an <xref:System.Activities.Statements.InvokeMethod> activity).</span></span>  
  
 <span data-ttu-id="7fbef-138">그런 다음 이 샘플에서는 접수 후 `RfpRepository`에 저장된 모든 제안서를 하나씩 돌아가며 <xref:System.Activities.Statements.Assign> 활동과 <xref:System.Activities.Expressions> 활동을 사용하여 조정 값을 계산합니다. 지금까지 나온 최상의 제안보다 더 나은 조정 값이 발견되면 <xref:System.Activities.Statements.If> 및 <xref:System.Activities.Statements.Assign> 활동을 사용하여 새 값을 최상의 제안으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-138">The sample then iterates through all of the received proposals stored in the `RfpRepository`, calculating the adjusted value (using an <xref:System.Activities.Statements.Assign> activity and <xref:System.Activities.Expressions> activities), and if the adjusted value is better than the previous best offer, assigns the new value as the best offer (using <xref:System.Activities.Statements.If> and <xref:System.Activities.Statements.Assign> activities).</span></span>  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="7fbef-139">이 샘플의 프로젝트</span><span class="sxs-lookup"><span data-stu-id="7fbef-139">Projects in this Sample</span></span>  

 <span data-ttu-id="7fbef-140">이 샘플에는 다음 프로젝트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-140">This sample contains the following projects.</span></span>  
  
|<span data-ttu-id="7fbef-141">프로젝트</span><span class="sxs-lookup"><span data-stu-id="7fbef-141">Project</span></span>|<span data-ttu-id="7fbef-142">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7fbef-143">일반</span><span class="sxs-lookup"><span data-stu-id="7fbef-143">Common</span></span>|<span data-ttu-id="7fbef-144">프로세스 내에 사용되는 엔터티 개체(제안 요청서, 공급업체 및 공급업체 제안서)입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-144">The entity objects used within the process (Request for Proposal, Vendor, and Vendor Proposal).</span></span>|  
|<span data-ttu-id="7fbef-145">WfDefinition</span><span class="sxs-lookup"><span data-stu-id="7fbef-145">WfDefinition</span></span>|<span data-ttu-id="7fbef-146">구매 프로세스 워크플로의 인스턴스를 만들고 사용하기 위해 클라이언트 애플리케이션에 사용되는 프로세스([!INCLUDE[wf1](../../../../includes/wf1-md.md)] 프로그램)와 호스트(`PurchaseProcessHost`)에 대한 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-146">The definition of the process (as a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] program) and host (`PurchaseProcessHost`) used by client applications for creating and using instances of the purchase process workflow.</span></span>|  
|<span data-ttu-id="7fbef-147">WebClient</span><span class="sxs-lookup"><span data-stu-id="7fbef-147">WebClient</span></span>|<span data-ttu-id="7fbef-148">사용자가 구매 프로세스의 인스턴스를 만들고 참여할 수 있게 해 주는 ASP.NET client 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-148">An ASP.NET client application that allows the users to create and participate in instances of the purchase process.</span></span> <span data-ttu-id="7fbef-149">이 응용 프로그램에서는 워크플로 엔진과 상호 작용하기 위해 사용자 지정하여 만든 호스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-149">It uses a custom-created host to interact with the workflow engine.</span></span>|  
|<span data-ttu-id="7fbef-150">WinFormsClient</span><span class="sxs-lookup"><span data-stu-id="7fbef-150">WinFormsClient</span></span>|<span data-ttu-id="7fbef-151">사용자가 구매 프로세스의 인스턴스를 만들고 여기에 참가할 수 있도록 하는 Windows Forms 클라이언트 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-151">A Windows Forms client application that allows the users to create and participate in instances of the purchase process.</span></span> <span data-ttu-id="7fbef-152">이 응용 프로그램에서는 워크플로 엔진과 상호 작용하기 위해 사용자 지정하여 만든 호스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-152">It uses a custom-created host to interact with the workflow engine.</span></span>|  
  
### <a name="wfdefinition"></a><span data-ttu-id="7fbef-153">WfDefinition</span><span class="sxs-lookup"><span data-stu-id="7fbef-153">WfDefinition</span></span>  

 <span data-ttu-id="7fbef-154">다음 표에는 WfDefinition 프로젝트의 주요 파일에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-154">The following table contains a description of the most important files in the WfDefinition project.</span></span>  
  
|<span data-ttu-id="7fbef-155">파일</span><span class="sxs-lookup"><span data-stu-id="7fbef-155">File</span></span>|<span data-ttu-id="7fbef-156">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-156">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7fbef-157">IPurchaseProcessHost.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-157">IPurchaseProcessHost.cs</span></span>|<span data-ttu-id="7fbef-158">워크플로의 호스트에 대한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-158">Interface for the host of the workflow.</span></span>|  
|<span data-ttu-id="7fbef-159">PurchaseProcessHost.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-159">PurchaseProcessHost.cs</span></span>|<span data-ttu-id="7fbef-160">워크플로에 대한 호스트의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-160">Implementation of a host for the workflow.</span></span> <span data-ttu-id="7fbef-161">이 호스트는 워크플로 런타임에 대한 세부 사항을 추상화하며, 모든 클라이언트 애플리케이션에서 `PurchaseProcess` 워크플로 인스턴스를 로드 및 실행하고 상호 작용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-161">The host abstracts the details of the workflow runtime and is used in all the client applications to load, run, and interact with `PurchaseProcess` workflow instances.</span></span>|  
|<span data-ttu-id="7fbef-162">PurchaseProcessWorkflow.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-162">PurchaseProcessWorkflow.cs</span></span>|<span data-ttu-id="7fbef-163">구매 프로세스 워크플로에 대한 정의가 포함된 활동이며, <xref:System.Activities.Activity>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-163">An activity that contains the definition of the Purchase Process workflow (derives from <xref:System.Activities.Activity>).</span></span><br /><br /> <span data-ttu-id="7fbef-164"><xref:System.Activities.Activity>에서 파생되는 활동은 기존의 사용자 지정 활동과 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 활동 라이브러리에서 가져온 활동을 어셈블하여 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-164">Activities that derive from <xref:System.Activities.Activity> compose functionality by assembling existing custom activities and activities from the [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] activity library.</span></span> <span data-ttu-id="7fbef-165">이 활동을 어셈블하는 것은 사용자 지정 기능을 만드는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-165">Assembling these activities is the most basic way to create custom functionality.</span></span>|  
|<span data-ttu-id="7fbef-166">WaitForVendorProposal.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-166">WaitForVendorProposal.cs</span></span>|<span data-ttu-id="7fbef-167">이 사용자 지정 활동은 <xref:System.Activities.NativeActivity>에서 파생되며, 명명된 책갈피를 만듭니다. 이 책갈피는 나중에 제안서를 제출하는 공급업체가 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-167">This custom activity derives from <xref:System.Activities.NativeActivity> and creates a named bookmark that must be resumed later by a vendor when submitting the proposal.</span></span><br /><br /> <span data-ttu-id="7fbef-168"><xref:System.Activities.NativeActivity>에서 파생되는 활동과 같이 <xref:System.Activities.CodeActivity>에서 파생되는 활동은 <xref:System.Activities.NativeActivity.Execute%2A>를 재정의하여 명령형 기능을 만들지만, <xref:System.Activities.ActivityContext> 메서드에 전달되는 `Execute`를 통해 워크플로 런타임의 모든 기능에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-168">Activities that derive from <xref:System.Activities.NativeActivity>, like those that derive from <xref:System.Activities.CodeActivity>, create imperative functionality by overriding <xref:System.Activities.NativeActivity.Execute%2A>, but also have access to all of the functionality of the workflow runtime through the <xref:System.Activities.ActivityContext> that gets passed into the `Execute` method.</span></span> <span data-ttu-id="7fbef-169">이 컨텍스트는 자식 활동 예약 및 취소를 지원 하 고, 영구 영역 (런타임이 원자성 트랜잭션과 같이 워크플로 데이터를 유지 하지 않는 실행 블록)을 설정 하 고, <xref:System.Activities.Bookmark> 개체 (일시 중지 된 워크플로를 다시 시작 하기 위한 핸들)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-169">This context has support for scheduling and canceling child activities, setting up no-persist zones (execution blocks during which the runtime does not persist the workflow's data, such as within atomic transactions), and <xref:System.Activities.Bookmark> objects (handles for resuming paused workflows).</span></span>|  
|<span data-ttu-id="7fbef-170">TrackingParticipant.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-170">TrackingParticipant.cs</span></span>|<span data-ttu-id="7fbef-171">모든 추적 이벤트를 받아 텍스트 파일로 저장하는 <xref:System.Activities.Tracking.TrackingParticipant>입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-171">A <xref:System.Activities.Tracking.TrackingParticipant> that receives all tracking events and saves them to a text file.</span></span><br /><br /> <span data-ttu-id="7fbef-172">추적 참가자가 워크플로 인스턴스에 확장으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-172">Tracking participants are added to workflow instance as Extensions.</span></span>|  
|<span data-ttu-id="7fbef-173">XmlWorkflowInstanceStore.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-173">XmlWorkflowInstanceStore.cs</span></span>|<span data-ttu-id="7fbef-174">워크플로 애플리케이션을 XML 파일에 저장하는 사용자 지정 <xref:System.Runtime.DurableInstancing.InstanceStore>입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-174">A custom <xref:System.Runtime.DurableInstancing.InstanceStore> that saves workflow applications to XML files.</span></span>|  
|<span data-ttu-id="7fbef-175">XmlPersistenceParticipant.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-175">XmlPersistenceParticipant.cs</span></span>|<span data-ttu-id="7fbef-176">제안 요청의 인스턴스를 XML 파일에 저장하는 사용자 지정 <xref:System.Activities.Persistence.PersistenceParticipant>입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-176">A custom <xref:System.Activities.Persistence.PersistenceParticipant> that saves an instance of request for proposal to an XML file.</span></span>|  
|<span data-ttu-id="7fbef-177">AsyncResult.cs / CompletedAsyncResult.cs</span><span class="sxs-lookup"><span data-stu-id="7fbef-177">AsyncResult.cs / CompletedAsyncResult.cs</span></span>|<span data-ttu-id="7fbef-178">지속성 구성 요소의 비동기 패턴을 구현하기 위한 도우미 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-178">Helper classes for implementing the asynchronous pattern in the persistence components.</span></span>|  
  
### <a name="common"></a><span data-ttu-id="7fbef-179">일반</span><span class="sxs-lookup"><span data-stu-id="7fbef-179">Common</span></span>  

 <span data-ttu-id="7fbef-180">다음 표에는 Common 프로젝트의 주요 클래스에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-180">The following table contains a description of the most important classes in the Common project.</span></span>  
  
|<span data-ttu-id="7fbef-181">인스턴스</span><span class="sxs-lookup"><span data-stu-id="7fbef-181">Class</span></span>|<span data-ttu-id="7fbef-182">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7fbef-183">Vendor</span><span class="sxs-lookup"><span data-stu-id="7fbef-183">Vendor</span></span>|<span data-ttu-id="7fbef-184">제안 요청서에 제안을 제출하는 공급업체입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-184">A vendor that submits proposals in a Request for Proposals.</span></span>|  
|<span data-ttu-id="7fbef-185">RequestForProposal</span><span class="sxs-lookup"><span data-stu-id="7fbef-185">RequestForProposal</span></span>|<span data-ttu-id="7fbef-186">RFP(제안 요청서)는 특정 상품이나 서비스에 대한 제안서를 제출하도록 공급업체에 요청하는 초대장입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-186">A request for proposals (RFP) is an invitation for vendors to submit proposals on a specific commodity or service.</span></span>|  
|<span data-ttu-id="7fbef-187">VendorProposal</span><span class="sxs-lookup"><span data-stu-id="7fbef-187">VendorProposal</span></span>|<span data-ttu-id="7fbef-188">공급업체가 구체적인 RFP에 대해 제출한 제안서입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-188">A proposal submitted by a vendor to a concrete RFP.</span></span>|  
|<span data-ttu-id="7fbef-189">VendorRepository</span><span class="sxs-lookup"><span data-stu-id="7fbef-189">VendorRepository</span></span>|<span data-ttu-id="7fbef-190">공급업체의 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-190">The repository of Vendors.</span></span> <span data-ttu-id="7fbef-191">이 구현에는 공급업체 인스턴스의 메모리 내 컬렉션과 해당 인스턴스를 노출하기 위한 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-191">This implementation contains an in-memory collection of instances of Vendor and methods for exposing those instances.</span></span>|  
|<span data-ttu-id="7fbef-192">RfpRepository</span><span class="sxs-lookup"><span data-stu-id="7fbef-192">RfpRepository</span></span>|<span data-ttu-id="7fbef-193">제안 요청서의 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-193">The repository of Requests for Proposals.</span></span> <span data-ttu-id="7fbef-194">이 구현에는 스키마화된 지속성에 의해 생성된 제안 요청서의 XML 파일을 쿼리하기 위한 Linq to XML 사용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-194">This implementation contains uses Linq to XML to query the XML file of Requests for Proposal generated by the schematized persistence.</span></span> |  
|<span data-ttu-id="7fbef-195">IOHelper</span><span class="sxs-lookup"><span data-stu-id="7fbef-195">IOHelper</span></span>|<span data-ttu-id="7fbef-196">이 클래스는 모든 I/O 관련 문제(폴더, 경로 등)를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-196">This class handles all I/O-related issues (folders, paths, and so on.)</span></span>|  
  
### <a name="web-client"></a><span data-ttu-id="7fbef-197">웹 클라이언트</span><span class="sxs-lookup"><span data-stu-id="7fbef-197">Web Client</span></span>  

 <span data-ttu-id="7fbef-198">다음 표에는 WebClient 프로젝트의 주요 웹 페이지에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-198">The following table contains a description of the most important Web pages in the Web Client project.</span></span>  
  
|<span data-ttu-id="7fbef-199">파일</span><span class="sxs-lookup"><span data-stu-id="7fbef-199">File</span></span>|<span data-ttu-id="7fbef-200">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-200">Description</span></span>|  
|-|-|  
|<span data-ttu-id="7fbef-201">CreateRfp.aspx</span><span class="sxs-lookup"><span data-stu-id="7fbef-201">CreateRfp.aspx</span></span>|<span data-ttu-id="7fbef-202">새 제안 요청서를 만들고 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-202">Creates and submits a new Request for Proposals.</span></span>|  
|<span data-ttu-id="7fbef-203">Default.aspx</span><span class="sxs-lookup"><span data-stu-id="7fbef-203">Default.aspx</span></span>|<span data-ttu-id="7fbef-204">활성화된 제안 요청서와 완료된 제안 요청서를 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-204">Shows all active and completed Requests for Proposals.</span></span>|  
|<span data-ttu-id="7fbef-205">GetVendorProposal.aspx</span><span class="sxs-lookup"><span data-stu-id="7fbef-205">GetVendorProposal.aspx</span></span>|<span data-ttu-id="7fbef-206">구체적인 제안 요청서에 대해 공급업체의 제안서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-206">Gets a proposal from a vendor in a concrete Request for Proposals.</span></span> <span data-ttu-id="7fbef-207">이 페이지는 공급업체에서만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-207">This page is used only by vendors.</span></span>|  
|<span data-ttu-id="7fbef-208">ShowRfp.aspx</span><span class="sxs-lookup"><span data-stu-id="7fbef-208">ShowRfp.aspx</span></span>|<span data-ttu-id="7fbef-209">제안 요청서에 대한 모든 정보(접수된 제안서, 날짜, 금액 및 기타 정보)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-209">Show all the information about a Request for Proposals (received proposals, dates, values, and other information).</span></span> <span data-ttu-id="7fbef-210">이 페이지는 제안 요청서의 작성자만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-210">This page is only used by the creator of the Request for Proposal.</span></span>|  
  
### <a name="winforms-client"></a><span data-ttu-id="7fbef-211">WinFormsClient</span><span class="sxs-lookup"><span data-stu-id="7fbef-211">WinForms Client</span></span>  

 <span data-ttu-id="7fbef-212">다음 표에는 WinFormsClient 프로젝트의 주요 폼에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-212">The following table contains a description of the most important forms in the Win Forms project.</span></span>  
  
|<span data-ttu-id="7fbef-213">Form</span><span class="sxs-lookup"><span data-stu-id="7fbef-213">Form</span></span>|<span data-ttu-id="7fbef-214">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-214">Description</span></span>|  
|-|-|  
|<span data-ttu-id="7fbef-215">NewRfp</span><span class="sxs-lookup"><span data-stu-id="7fbef-215">NewRfp</span></span>|<span data-ttu-id="7fbef-216">새 제안 요청서를 만들고 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-216">Creates and submits a new Request for Proposals.</span></span>|  
|<span data-ttu-id="7fbef-217">ShowProposals</span><span class="sxs-lookup"><span data-stu-id="7fbef-217">ShowProposals</span></span>|<span data-ttu-id="7fbef-218">활성화된 제안 요청서와 완료된 제안 요청서를 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-218">Show all active and finished Requests for Proposals.</span></span> <span data-ttu-id="7fbef-219">**참고:**  제안에 대 한 요청을 만들거나 수정한 후 해당 화면에 변경 내용을 표시 하려면 UI에서 **새로 고침** 단추를 클릭 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-219">**Note:**  You may need to click the **Refresh** button in the UI to see changes in that screen after you create or modify a Request for Proposal.</span></span>|  
|<span data-ttu-id="7fbef-220">SubmitProposal</span><span class="sxs-lookup"><span data-stu-id="7fbef-220">SubmitProposal</span></span>|<span data-ttu-id="7fbef-221">구체적인 제안 요청서에 대해 공급업체의 제안서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-221">Get a proposal from a vendor in a concrete Request for Proposals.</span></span> <span data-ttu-id="7fbef-222">이 창은 공급업체에서만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-222">This window is used only by vendors.</span></span>|  
|<span data-ttu-id="7fbef-223">ViewRfp</span><span class="sxs-lookup"><span data-stu-id="7fbef-223">ViewRfp</span></span>|<span data-ttu-id="7fbef-224">제안 요청서에 대한 모든 정보(접수된 제안서, 날짜, 금액 및 기타 정보)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-224">Show all the information about a Request for Proposals (received proposals, dates, values, and other information).</span></span> <span data-ttu-id="7fbef-225">이 창은 제안 요청서의 작성자만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-225">This window  is only used by the creator of the Request for Proposals.</span></span>|  
  
### <a name="persistence-files"></a><span data-ttu-id="7fbef-226">지속성 파일</span><span class="sxs-lookup"><span data-stu-id="7fbef-226">Persistence Files</span></span>  

 <span data-ttu-id="7fbef-227">다음 표에는 지속성 공급자(`XmlPersistenceProvider`)가 생성하는 파일이 나와 있습니다. 이 파일은 <xref:System.IO.Path.GetTempPath%2A>를 사용하여 현재 시스템의 임시 폴더 경로에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-227">The following table shows the files generated by the persistence provider (`XmlPersistenceProvider`) are located in the path of the current system's temporary folder (using <xref:System.IO.Path.GetTempPath%2A>).</span></span> <span data-ttu-id="7fbef-228">추적 파일은 현재 실행 경로에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-228">The tracing file is created in the current execution path.</span></span>  
  
|<span data-ttu-id="7fbef-229">파일 이름</span><span class="sxs-lookup"><span data-stu-id="7fbef-229">File Name</span></span>|<span data-ttu-id="7fbef-230">설명</span><span class="sxs-lookup"><span data-stu-id="7fbef-230">Description</span></span>|<span data-ttu-id="7fbef-231">경로</span><span class="sxs-lookup"><span data-stu-id="7fbef-231">Path</span></span>|  
|-|-|-|  
|<span data-ttu-id="7fbef-232">rfps.xml</span><span class="sxs-lookup"><span data-stu-id="7fbef-232">rfps.xml</span></span>|<span data-ttu-id="7fbef-233">활성화된 제안 요청서와 완료된 제안 요청서가 모두 포함된 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-233">The XML file with all the active and finished Requests for Proposals.</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="7fbef-234">[instanceid]</span><span class="sxs-lookup"><span data-stu-id="7fbef-234">[instanceid]</span></span>|<span data-ttu-id="7fbef-235">이 파일에는 워크플로 인스턴스에 대한 모든 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-235">This file contains all the information about a workflow instance.</span></span><br /><br /> <span data-ttu-id="7fbef-236">이 파일은 스키마화된 지속성 구현(XmlPersistenceProvider의 PersistenceParticipant)을 통해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-236">This file is generated by the schematized persistence implementation (PersistenceParticipant in XmlPersistenceProvider).</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="7fbef-237">[instanceId].tracking</span><span class="sxs-lookup"><span data-stu-id="7fbef-237">[instanceId].tracking</span></span>|<span data-ttu-id="7fbef-238">구체적인 인스턴스 내에서 발생하는 모든 이벤트가 포함된 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-238">A text file with all the events that occurred within a concrete instance.</span></span><br /><br /> <span data-ttu-id="7fbef-239">이 파일은 TrackingParticipant에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-239">This file is generated by TrackingParticipant.</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="7fbef-240">PurchaseProcess.Tracing.TraceLog.txt</span><span class="sxs-lookup"><span data-stu-id="7fbef-240">PurchaseProcess.Tracing.TraceLog.txt</span></span>|<span data-ttu-id="7fbef-241">App.config 또는 Web.config 파일의 구성 매개 변수를 기반으로 하여 워크플로를 통해 생성되는 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-241">The tracing file generated by the workflow based on the configuration parameters in the App.config or Web.config files.</span></span>|<span data-ttu-id="7fbef-242">현재 실행 경로</span><span class="sxs-lookup"><span data-stu-id="7fbef-242">Current execution path</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7fbef-243">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7fbef-243">To use this sample</span></span>  
  
1. <span data-ttu-id="7fbef-244">Visual Studio 2010을 사용 하 여 PurchaseProcess 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-244">Using Visual Studio 2010, open the PurchaseProcess.sln solution file.</span></span>  
  
2. <span data-ttu-id="7fbef-245">웹 클라이언트 프로젝트를 실행 하려면 **솔루션 탐색기** 열고 **웹 클라이언트** 프로젝트를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-245">To execute the Web Client project, open **Solution Explorer** and right-click the **Web Client** project.</span></span> <span data-ttu-id="7fbef-246">**시작 프로젝트로 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-246">Select **Set as Startup Project**.</span></span>  
  
3. <span data-ttu-id="7fbef-247">WinForms Client 프로젝트를 실행 하려면 **솔루션 탐색기** 을 열고 **WinForms client** 프로젝트를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-247">To execute the WinForms Client project, open **Solution Explorer** and right-click the **WinForms Client** project.</span></span> <span data-ttu-id="7fbef-248">**시작 프로젝트로 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-248">Select **Set as Startup Project**.</span></span>  
  
4. <span data-ttu-id="7fbef-249">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-249">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="7fbef-250">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-250">To run the solution, press CTRL+F5.</span></span>  
  
### <a name="web-client-options"></a><span data-ttu-id="7fbef-251">웹 클라이언트 옵션</span><span class="sxs-lookup"><span data-stu-id="7fbef-251">Web Client Options</span></span>  
  
- <span data-ttu-id="7fbef-252">**새 RFP 만들기**: 제안에 대 한 새 요청 (RFP)을 만들고 구매 프로세스 워크플로를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-252">**Create a new RFP**: Creates a new Request for Proposals (RFP) and starts a Purchase Process workflow.</span></span>  
  
- <span data-ttu-id="7fbef-253">**Refresh**: 주 창에서 활성 및 완료 된 rfp 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-253">**Refresh**: Refreshes the list of Active and Finished RFPs in the main window.</span></span>  
  
- <span data-ttu-id="7fbef-254">**보기**: 기존 RFP의 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-254">**View**: Shows the content of an existing RFP.</span></span> <span data-ttu-id="7fbef-255">RFP가 완료되지 않았거나 공급업체가 요청을 받은 경우 공급업체에서 제안서를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-255">Vendors can submit their proposals (if invited or the RFP is not finished).</span></span>  
  
- <span data-ttu-id="7fbef-256">다음으로 보기: active Rfp 표의 **보기 형식** 콤보 상자에서 원하는 참가자를 선택 하 여 사용자가 다른 id를 사용 하 여 RFP에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-256">View As: The user can access the RFP using different identities by selecting the desired participant in the **View as** combo box in the active RFPs grid.</span></span>  
  
### <a name="winforms-client-options"></a><span data-ttu-id="7fbef-257">WinForms 클라이언트 옵션</span><span class="sxs-lookup"><span data-stu-id="7fbef-257">WinForms Client Options</span></span>  
  
- <span data-ttu-id="7fbef-258">**CREATE RFP**: 제안 (RFP)에 대 한 새 요청을 만들고 구매 프로세스 워크플로를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-258">**Create RFP**: Creates a new Request for Proposals (RFP) and starts a Purchase Process workflow.</span></span>  
  
- <span data-ttu-id="7fbef-259">**Refresh**: 주 창에서 활성 및 완료 된 rfp 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-259">**Refresh**: Refreshes the list of Active and Finished RFPs in the main window.</span></span>  
  
- <span data-ttu-id="7fbef-260">**RFP 보기**: 기존 RFP의 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-260">**View RFP**: Shows the content of an existing RFP.</span></span> <span data-ttu-id="7fbef-261">RFP가 완료되지 않았거나 공급업체가 요청을 받은 경우 공급업체에서 제안서를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-261">Vendors can submit their proposals (if invited or the RFP is not finished)</span></span>  
  
- <span data-ttu-id="7fbef-262">**연결** 방법: 사용자는 active Rfp 표의 **보기 형식** 콤보 상자에서 원하는 참가자를 선택 하 여 다른 id를 사용 하 여 RFP에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbef-262">**Connect As**: The user can access the RFP using different identities by selecting the desired participant in the **View as** combo box in the active RFPs grid.</span></span>
