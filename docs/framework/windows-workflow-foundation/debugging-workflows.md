---
description: '자세한 정보: 워크플로 디버깅'
title: 워크플로 디버깅
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 9de65e580d47395a9528f4672014ceb491b09230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742565"
---
# <a name="debugging-workflows"></a><span data-ttu-id="f0cf6-103">워크플로 디버깅</span><span class="sxs-lookup"><span data-stu-id="f0cf6-103">Debugging Workflows</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="f0cf6-104">는 개발 환경에서 실행 중인 워크플로를 디버깅하기 위한 여러 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-104">offers several options for debugging running workflows from the development environment.</span></span> <span data-ttu-id="f0cf6-105">디자이너, XAML 및 코드에서 워크플로를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-105">Workflows can be debugged in the designer, in XAML, and in code.</span></span>

## <a name="debugging-in-the-workflow-designer"></a><span data-ttu-id="f0cf6-106">워크플로 디자이너에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="f0cf6-106">Debugging in the Workflow Designer</span></span>

<span data-ttu-id="f0cf6-107">워크플로 디자이너에서 활동을 강조 표시 하 고 <kbd>F9</kbd> 키를 누르거나 활동의 상황에 맞는 메뉴를 사용 하 여 활동에 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-107">Breakpoints can be set on activities in the workflow designer by either highlighting the activity and pressing <kbd>F9</kbd> or by using the activity’s context menu.</span></span> <span data-ttu-id="f0cf6-108">그러면 워크플로 호스트가 디버그 모드에서 실행될 때 워크플로 실행이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-108">Execution of the workflow then breaks when the workflow host is run in debug mode.</span></span> <span data-ttu-id="f0cf6-109">다음 스크린샷에서는 워크플로 실행이 중단점에서 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-109">In the following screenshot, workflow execution is paused at a breakpoint.</span></span> <span data-ttu-id="f0cf6-110">자세한 내용은 [워크플로 디자이너를 사용 하 여 워크플로 디버깅](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-110">For more information, see [Debugging Workflows with the Workflow Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).</span></span>

## <a name="debugging-in-xaml"></a><span data-ttu-id="f0cf6-111">XAML에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="f0cf6-111">Debugging in XAML</span></span>

<span data-ttu-id="f0cf6-112">워크플로가 디자이너의 중단점에서 일시 중지된 경우 XAML에서 워크플로를 디버깅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-112">If a workflow has paused at a breakpoint in the designer, the workflow can also be debugged in XAML.</span></span> <span data-ttu-id="f0cf6-113">XAML에서 실행 지점을 보려면 워크플로 실행이 일시 중지 될 때 워크플로 디자이너에서 **Xaml 뷰** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-113">To view the point of execution in XAML, select **XAML View** in the workflow designer when workflow execution is paused.</span></span> <span data-ttu-id="f0cf6-114">솔루션 탐색기에서 디자이너에 워크플로를 다시 열어 디버깅을 다시 디자이너로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-114">Debugging can be switched back to the designer by re-opening the workflow in the designer from the solution explorer.</span></span> <span data-ttu-id="f0cf6-115">자세한 내용은 [방법: 워크플로 디자이너를 사용 하 여 XAML 디버그](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-115">For more information, see [How to: Debug XAML with the Workflow Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).</span></span>

## <a name="debugging-in-code"></a><span data-ttu-id="f0cf6-116">코드에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="f0cf6-116">Debugging in Code</span></span>

<span data-ttu-id="f0cf6-117">중단점을 설정 하려면 코드 창의 왼쪽 여백을 클릭 하거나 F9 키를 설정 하려는 줄의 커서와 함께 <kbd>F9</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-117">To set a breakpoint, click the left margin of the code pane, or press <kbd>F9</kbd> with the cursor at the line where you want to set it.</span></span>

## <a name="attaching-to-a-workflow-process"></a><span data-ttu-id="f0cf6-118">워크플로 프로세스에 연결</span><span class="sxs-lookup"><span data-stu-id="f0cf6-118">Attaching to a Workflow Process</span></span>

<span data-ttu-id="f0cf6-119">워크플로 디버깅은 Visual Studio 인프라를 사용하여 프로세스에 연결하는 방식도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-119">Workflow debugging also supports using Visual Studio’s infrastructure to attach to a process.</span></span> <span data-ttu-id="f0cf6-120">이렇게 하면 워크플로 작성자가 Internet Information Services(IIS) 7.0 등 다른 호스트 환경에서 실행되는 워크플로를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-120">This enables the workflow author to debug a workflow running in a different host environment such as Internet Information Services (IIS) 7.0.</span></span>

## <a name="remote-debugging"></a><span data-ttu-id="f0cf6-121">Remote Debugging</span><span class="sxs-lookup"><span data-stu-id="f0cf6-121">Remote Debugging</span></span>

<span data-ttu-id="f0cf6-122">WF (Windows Workflow Foundation) 원격 디버깅은 다른 Visual Studio 구성 요소에 대 한 원격 디버깅과 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-122">Windows Workflow Foundation (WF) remote debugging functions the same as remote debugging for other Visual Studio components.</span></span> <span data-ttu-id="f0cf6-123">원격 디버깅 사용에 대 한 자세한 내용은 [방법: 원격 디버깅 사용](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-123">For information on using remote debugging, see [How to: Enable Remote Debugging](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf6-124">워크플로 응용 프로그램에서 x86 아키텍처를 대상으로 하 고 64 비트 운영 체제를 실행 하는 컴퓨터에서 호스트 되는 경우 원격 컴퓨터에 Visual Studio가 설치 되어 있지 않거나 워크플로 응용 프로그램의 대상이 **모든 CPU** 로 변경 되지 않으면 원격 디버깅이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-124">If the workflow application targets the x86 architecture and is hosted on a computer running a 64 bit operating system, then remote debugging will not work unless Visual Studio is installed on the remote computer or the target for the workflow application is changed to **Any CPU**.</span></span>

## <a name="extending-the-workflow-debugging-service"></a><span data-ttu-id="f0cf6-125">워크플로 디버깅 서비스 확장</span><span class="sxs-lookup"><span data-stu-id="f0cf6-125">Extending the Workflow Debugging Service</span></span>

<span data-ttu-id="f0cf6-126">워크플로 디버거 서비스는 현재 공용이며 다시 호스트된 디자이너에서 모니터링, 시뮬레이션 및 디버깅과 같은 사용자 지정 애플리케이션을 만드는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-126">The workflow debugger service is now public and can be used to create custom applications such as monitoring, simulation, and debugging in a re-hosted designer.</span></span> <span data-ttu-id="f0cf6-127">자세한 내용은 문서를 참조 <xref:System.Activities.Presentation.Debug.DebuggerService> 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-127">For more information, see the <xref:System.Activities.Presentation.Debug.DebuggerService> article.</span></span>
