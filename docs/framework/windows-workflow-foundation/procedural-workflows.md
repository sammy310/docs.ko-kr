---
title: 절차적 워크플로
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 15ff155fb057c4c10663d383a8942108c6e4375c
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348362"
---
# <a name="procedural-workflows"></a><span data-ttu-id="5a08a-102">절차적 워크플로</span><span class="sxs-lookup"><span data-stu-id="5a08a-102">Procedural Workflows</span></span>
<span data-ttu-id="5a08a-103">절차적 워크플로에서는 절차적 언어에서 사용되는 것과 비슷한 흐름 제어 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="5a08a-104">이러한 구조에는 `While` 및 `If`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="5a08a-105"><xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Sequence>와 같은 다른 흐름 제어 활동을 사용하여 이러한 워크플로를 자유롭게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="5a08a-106">실행 흐름 제어</span><span class="sxs-lookup"><span data-stu-id="5a08a-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="5a08a-107">워크플로 활동 라이브러리에는 절차적 언어에서 사용되는 대부분의 흐름 제어 메서드를 모델링하기 위한 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="5a08a-108">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-108">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="5a08a-109">흐름 제어 활동을 사용 하려면 끌어서 놓기까지 합니다 **활동** 디자이너 창 내의 복합 활동을 도구 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a08a-110">웹 팜에 호스트 워크플로 Windows Server appfabric 호스팅 기능을 사용 하는 경우 AppFabric 다른 AppFabric 서버 간 인스턴스를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-110">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="5a08a-111">이 경우 모든 노드 간에 리소스가 공유될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="5a08a-112">기본 NET 4 워크플로 활동 중 어떤 활동도 로컬 리소스에 액세스하는 작업을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="5a08a-113">AppFabric은 워크플로를 이동 불가능으로 표시하는 어떠한 메커니즘도 제공하지 않으므로 개발자는 워크플로가 이동할 때 실패할 수 있는 사용자 지정 활동을 만들지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a08a-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a08a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a08a-114">See also</span></span>

- [<span data-ttu-id="5a08a-115">순서도 워크플로</span><span class="sxs-lookup"><span data-stu-id="5a08a-115">Flowchart Workflows</span></span>](flowchart-workflows.md)
