---
title: 워크플로 호스팅 옵션
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 8ddb83f068eab8480bacc8b80bc5d44b7755fa59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293782"
---
# <a name="workflow-hosting-options"></a><span data-ttu-id="8c21c-102">워크플로 호스팅 옵션</span><span class="sxs-lookup"><span data-stu-id="8c21c-102">Workflow Hosting Options</span></span>

<span data-ttu-id="8c21c-103">대부분의 WF (Windows Workflow Foundation) 샘플에서는 콘솔 응용 프로그램에서 호스트 되는 워크플로를 사용 하지만 실제 워크플로에는 현실적인 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-103">Most of the Windows Workflow Foundation (WF) samples use workflows that are hosted in a console application, but this isn't a realistic scenario for real-world workflows.</span></span> <span data-ttu-id="8c21c-104">실제 비즈니스 응용 프로그램의 워크플로는 영구 프로세스에서 호스트 됩니다. 즉, 개발자가 작성 한 Windows 서비스 또는 IIS 7.0 또는 AppFabric과 같은 서버 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-104">Workflows in actual business applications will be hosted in persistent processes- either a Windows service authored by the developer, or a server application such as IIS 7.0 or AppFabric.</span></span> <span data-ttu-id="8c21c-105">이러한 방법에는 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-105">The differences between these approaches are as follows.</span></span>

## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a><span data-ttu-id="8c21c-106">IIS에서 Windows AppFabric을 사용하여 워크플로 호스팅</span><span class="sxs-lookup"><span data-stu-id="8c21c-106">Hosting workflows in IIS with Windows AppFabric</span></span>

<span data-ttu-id="8c21c-107">IIS와 AppFabric을 함께 사용하는 것은 기본적인 워크플로 호스팅 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-107">Using IIS with AppFabric is the preferred host for workflows.</span></span> <span data-ttu-id="8c21c-108">AppFabric을 사용하는 워크플로용 호스트 애플리케이션은 Windows Activation Service로, 이 애플리케이션에서는 IIS만을 통해 HTTP에 대한 종속성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-108">The host application for workflows using AppFabric is Windows Activation Service, which removes the dependency on HTTP over IIS alone.</span></span>

## <a name="hosting-workflows-in-iis-alone"></a><span data-ttu-id="8c21c-109">IIS만 사용하여 워크플로 호스팅</span><span class="sxs-lookup"><span data-stu-id="8c21c-109">Hosting workflows in IIS alone</span></span>

<span data-ttu-id="8c21c-110">실행 중인 응용 프로그램의 유지 관리를 용이 하 게 하는 AppFabric에서 사용할 수 있는 관리 및 모니터링 도구가 있으므로 IIS 7.0만 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-110">Using IIS 7.0 alone is not recommended, as there are management and monitoring tools available with AppFabric that facilitate maintenance of running applications.</span></span> <span data-ttu-id="8c21c-111">AppFabric으로 이동 하는 인프라 문제가 있는 경우에만 워크플로를 IIS 7.0에 단독으로 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-111">Workflows should only be hosted in IIS 7.0 alone if there are infrastructure concerns with moving to AppFabric.</span></span>

> [!WARNING]
> <span data-ttu-id="8c21c-112">IIS 7.0는 다양 한 이유로 정기적으로 응용 프로그램 풀을 재활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-112">IIS 7.0 recycles application pools periodically for various reasons.</span></span> <span data-ttu-id="8c21c-113">애플리케이션 풀이 재활용될 때 IIS는 이전 풀에서 메시지 수락을 중지하고 새 요청을 수락하는 새 애플리케이션 풀을 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-113">When an application pool is recycled, IIS stops accepting messages to the old pool, and instantiates a new application pool to accept new requests.</span></span> <span data-ttu-id="8c21c-114">응답이 전송 된 후 워크플로가 계속 작동 하는 경우 IIS 7.0은 수행 중인 작업을 인식 하지 못하므로 호스팅 응용 프로그램 풀을 재활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-114">If a workflow continues working after sending a response, IIS 7.0 will not be aware of the work being done, and may recycle the hosting application pool.</span></span> <span data-ttu-id="8c21c-115">이 경우 워크플로가 중단 되 고 추적 서비스는 빈 이유 필드와 함께 [1004-WorkflowInstanceAborted](1004-workflowinstanceaborted.md) 메시지를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-115">If this happens, the workflow will abort, and tracking services will record a [1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md) message with an empty Reason field.</span></span>
>
> <span data-ttu-id="8c21c-116">지속성이 사용되는 경우 호스트는 마지막 지속성 지점에서 중단된 인스턴스를 명시적으로 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-116">If persistence is used, the host must explicitly restart aborted instances from the last persistence point.</span></span>
>
> <span data-ttu-id="8c21c-117">AppFabric이 사용되는 경우 지속성이 사용되면 최종적으로 워크플로 관리 서비스가 마지막으로 성공한 지속성 지점에서 워크플로를 재개하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-117">If AppFabric is used, the workflow management service will eventually resume the workflow from the last successful persistence point if persistence is used.</span></span> <span data-ttu-id="8c21c-118">지속성이 사용되지 않고 워크플로가 요청/응답 패턴을 벗어나 작업을 수행하는 경우에는 워크플로 중단 시 데이터가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-118">If no persistence is used, and the workflow performs operations outside a Request/Response pattern, data will be lost when the workflow aborts.</span></span>

## <a name="hosting-a-workflow-in-a-custom-windows-service"></a><span data-ttu-id="8c21c-119">사용자 지정 Windows 서비스에서 워크플로 호스팅</span><span class="sxs-lookup"><span data-stu-id="8c21c-119">Hosting a workflow in a custom Windows Service</span></span>

<span data-ttu-id="8c21c-120">사용자 지정 워크플로를 호스트하기 위한 사용자 지정 워크플로 서비스를 만들려면 개발자가 AppFabric에서 기본적으로 제공되는 많은 기능을 복제해야 하지만 이 경우 사용자 지정 기능을 보다 유연하게 사용할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-120">Creating a custom workflow service to host the workflow will require the developer to duplicate a lot of the functionality provided out-of-box by AppFabric, but will allow for more flexibility with custom functionality.</span></span> <span data-ttu-id="8c21c-121">이 옵션은 AppFabric을 사용할 수 없는 것이 분명한 경우에만 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c21c-121">This option should only be considered if AppFabric proves to not be an option.</span></span>
