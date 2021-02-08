---
description: '자세한 정보: 워크플로 인스턴스 만들기 및 실행'
title: 워크플로 인스턴스 만들기 및 실행
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 2efd4a0017f450c21954e363af33be69c659624e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787853"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="18dfd-103">워크플로 인스턴스 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="18dfd-103">Creating and Running a Workflow Instance</span></span>

<span data-ttu-id="18dfd-104">이 샘플에서는 워크플로 인스턴스를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-104">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="18dfd-105">동기적 실행 방법과 비동기적 실행 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-105">It shows how to execute it synchronously and asynchronously.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="18dfd-106">데모</span><span class="sxs-lookup"><span data-stu-id="18dfd-106">Demonstrates</span></span>

<span data-ttu-id="18dfd-107"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="18dfd-107"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>

## <a name="discussion"></a><span data-ttu-id="18dfd-108">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="18dfd-108">Discussion</span></span>

<span data-ttu-id="18dfd-109">샘플의 첫 번째 부분에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-109">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="18dfd-110">이는 워크플로를 실행하는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-110">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="18dfd-111"><xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용할 경우 워크플로를 동기적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-111">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>

<span data-ttu-id="18dfd-112">샘플의 다음 부분에서는 <xref:System.Activities.WorkflowApplication> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-112">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="18dfd-113"><xref:System.Activities.WorkflowApplication> 클래스를 사용하면 실행 중인 워크플로와 상호 작용하고 워크플로를 비동기적으로 실행하는 등 각 인스턴스를 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-113"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18dfd-114">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="18dfd-115">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="18dfd-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="18dfd-116">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="18dfd-117">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dfd-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a><span data-ttu-id="18dfd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18dfd-118">See also</span></span>

- [<span data-ttu-id="18dfd-119">WorkflowInvoker 및 WorkflowApplication 사용</span><span class="sxs-lookup"><span data-stu-id="18dfd-119">Using WorkflowInvoker and WorkflowApplication</span></span>](../using-workflowinvoker-and-workflowapplication.md)
