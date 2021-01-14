---
title: '방법: 워크플로 만들기'
description: 이 단원의 세 가지 옵션 중 하나를 완료 하 여이 Workflow Foundation 자습서의 일부로 워크플로를 만듭니다.
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: ea9fd023ba15ae23a10f5b8cf6f82c49ca9af6c8
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190444"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="f857a-103">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="f857a-103">How to: Create a Workflow</span></span>

<span data-ttu-id="f857a-104">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="f857a-105">이 단원의 항목에서는 활동과 같은 기본 제공 활동과 <xref:System.Activities.Statements.Flowchart> 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용 하는 워크플로를 만드는 과정을 단계별로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="f857a-106">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="f857a-107">자습서를 완료하려면 이 단원의 한 항목만 필요합니다. 원하는 스타일을 선택하고 해당 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="f857a-108">하지만 원할 경우 모든 항목을 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f857a-109">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="f857a-110">이 항목을 완료 하려면 먼저 [방법: 작업 만들기](how-to-create-an-activity.md)를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f857a-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f857a-111">In This Section</span></span>  

 [<span data-ttu-id="f857a-112">방법: 순차 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="f857a-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="f857a-113"><xref:System.Activities.Statements.Sequence> 활동을 사용하여 순차 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="f857a-114">방법: 순서도 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="f857a-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="f857a-115"><xref:System.Activities.Statements.Flowchart> 활동을 사용하여 순서도 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="f857a-116">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="f857a-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="f857a-117"><xref:System.Activities.Statements.StateMachine> 활동을 사용하여 상태 시스템 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f857a-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f857a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f857a-118">See also</span></span>

- [<span data-ttu-id="f857a-119">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f857a-119">Windows Workflow Foundation Programming</span></span>](programming.md)
