---
title: WF의 상태 시스템 활동
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120915"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="50f57-102">WF의 상태 시스템 활동</span><span class="sxs-lookup"><span data-stu-id="50f57-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="50f57-103">상태 시스템 워크플로 만들기 위한 여러 시스템 제공 활동 및 활동 디자이너를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="50f57-104">익숙한 상태 시스템 패러다임을 사용하여 포함된 활동을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="50f57-105">상태 시스템의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="50f57-106">상태 시스템의 종료 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-106">Represents a terminating state in a state machine.</span></span> <xref:System.Activities.Core.Presentation.FinalState> <span data-ttu-id="50f57-107">activity designer가 때 사용 되는 만듭니다는 <xref:System.Activities.Statements.State> 종료 상태로 미리 구성 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-107">is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="50f57-108">자세한 내용은 [FinalState 활동 디자이너](/visualstudio/workflow-designer/finalstate-activity-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="50f57-109">두 상태 간 전환을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-109">Represents the transition between two states.</span></span> <span data-ttu-id="50f57-110">방법이 없는 **도구 상자** 에 대 한 항목 <xref:System.Activities.Statements.Transition>;를 두 상태 사이의 선을 끌어서 워크플로 디자이너에서 전환을 만들어집니다 또는 하나의 상태 다른 위로 가져갈 때 표시 되는 삼각형에 상태를 삭제 하 여 .</span><span class="sxs-lookup"><span data-stu-id="50f57-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="50f57-111">자세한 내용은 [전환 활동 디자이너](/visualstudio/workflow-designer/transition-activity-designer)합니다.</span><span class="sxs-lookup"><span data-stu-id="50f57-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50f57-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="50f57-112">See also</span></span>

- [<span data-ttu-id="50f57-113">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="50f57-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
