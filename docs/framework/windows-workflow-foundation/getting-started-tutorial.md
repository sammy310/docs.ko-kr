---
title: 시작 하기 Tutorial2
description: 이 문서에서는 응용 프로그램 Windows Workflow Foundation 프로그래밍을 소개 하는 일련의 자습서를 시작 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 148ba77231067bf5f8ff1d8b444b83d951ce8761
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419852"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="bea78-103">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="bea78-103">Getting Started Tutorial</span></span>
<span data-ttu-id="bea78-104">이 섹션에는 WF (프로그래밍 Windows Workflow Foundation) 응용 프로그램을 소개 하는 연습 항목 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="bea78-105">이 항목의 절차를 진행하면서 빌드하는 애플리케이션은 숫자 추측 게임입니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="bea78-106">자습서의 첫째 항목에서는 워크플로에 필요한 사용자 지정 활동을 만드는 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="bea78-107">둘째 항목에서는 이러한 활동을 기본 제공 워크플로 활동과 함께 어셈블하여 순서도 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="bea78-108">셋째 항목에서는 워크플로를 실행하기 위한 호스트 애플리케이션을 구성하고, 넷째 항목에서는 지속성을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="bea78-109">이 과정의 각 단계는 그 이전 단계를 기반으로 진행되므로 각 단계를 순서대로 완료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bea78-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bea78-110">In This Section</span></span>  
 [<span data-ttu-id="bea78-111">방법: 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="bea78-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="bea78-112"><xref:System.Activities.NativeActivity%601>에서 파생되는 사용자 지정 활동을 만드는 방법을 설명하고, 활동 디자이너를 사용하여 이 활동과 기본 제공 활동을 하나의 복합 활동으로 구성하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="bea78-113">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="bea78-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="bea78-114">기본 제공 활동과 이전 자습서의 사용자 지정 활동을 사용하여 순서도, 순차 및 상태 시스템 워크플로를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="bea78-115">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="bea78-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="bea78-116">호스트 환경에서 워크플로를 호출하는 방법, 워크플로 안팎으로 데이터를 전달하는 방법 및 책갈피를 다시 시작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="bea78-117">방법: 장기 실행 워크플로 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="bea78-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="bea78-118">워크플로 애플리케이션에 지속성을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="bea78-119">방법: 사용자 지정 추적 참가자 만들기</span><span class="sxs-lookup"><span data-stu-id="bea78-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="bea78-120">사용자 지정 추적 참가자와 추적 프로필을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="bea78-121">방법: 여러 버전의 워크플로를 함께 호스팅</span><span class="sxs-lookup"><span data-stu-id="bea78-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="bea78-122">`WorkflowIdentity`를 사용하여 여러 버전의 워크플로를 함께 호스트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="bea78-123">방법: 실행 중인 워크플로 인스턴스의 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="bea78-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="bea78-124">동적 업데이트를 사용하여 실행 중인 워크플로 인스턴스를 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bea78-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea78-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bea78-125">See also</span></span>

- [<span data-ttu-id="bea78-126">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bea78-126">Windows Workflow Foundation Programming</span></span>](programming.md)
