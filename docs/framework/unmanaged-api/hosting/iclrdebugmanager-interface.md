---
title: ICLRDebugManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
ms.openlocfilehash: 717a3d12528a34eafbd918c29d8e13bb87097d82
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615780"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="4c3e6-102">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c3e6-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="4c3e6-103">호스트에서 작업 집합을 식별자와 이름에 연결할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c3e6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-104">Methods</span></span>  
  
|<span data-ttu-id="4c3e6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-105">Method</span></span>|<span data-ttu-id="4c3e6-106">설명</span><span class="sxs-lookup"><span data-stu-id="4c3e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c3e6-107">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-107">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="4c3e6-108">작업을 식별자와 연결 하기 위해 호스트와 디버거 간에 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4c3e6-109">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-109">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="4c3e6-110">작업 목록과 식별자 및 이름 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4c3e6-111">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-111">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="4c3e6-112">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="4c3e6-113">IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-113">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="4c3e6-114">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="4c3e6-115">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="4c3e6-116">[ICLRTask](iclrtask-interface.md) 인스턴스 목록을 식별자 및 이름과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-116">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4c3e6-117">SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-117">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="4c3e6-118">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="4c3e6-119">SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="4c3e6-119">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="4c3e6-120">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="4c3e6-121">이 정책은 줄 번호와 파일에 대 한 정보가 호출 스택에 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c3e6-122">설명</span><span class="sxs-lookup"><span data-stu-id="4c3e6-122">Remarks</span></span>  
 <span data-ttu-id="4c3e6-123">디버깅 시나리오에서 호스트는 자체 프로그래밍 논리에 따라 작업을 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="4c3e6-124">예를 들어, 그룹화를 통해 개발자는 프로세스에서 실행 되는 모든 작업을 확인 하는 대신 개발자의 Api에 필요한 작업만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="4c3e6-125">`ICLRDebugManager`호스트에서 이러한 종류의 그룹화를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c3e6-126">, 및의 세 가지 `ICLRDebugManager` 메서드 `BeginConnection` `SetConnectionTasks` `EndConnection` 는 서로 종속 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="4c3e6-127">이러한 작업은 예상 대로 작동 하기 위해 지정 된 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="4c3e6-128">호스트에서 그룹화에 할당 하는 그룹화 및 식별자와 이름에는 CLR (공용 언어 런타임)에 대 한 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="4c3e6-129">CLR은 단순히 디버거로 정보를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c3e6-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c3e6-130">Requirements</span></span>  
 <span data-ttu-id="4c3e6-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c3e6-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4c3e6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c3e6-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c3e6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c3e6-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c3e6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3e6-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c3e6-135">See also</span></span>

- [<span data-ttu-id="4c3e6-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c3e6-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
