---
description: '자세히 알아보기: ICLRDebugManager 인터페이스'
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
ms.openlocfilehash: 4306e38b7c868561276d5b00e7730b6fcee46fd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746026"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="bc8c7-103">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc8c7-103">ICLRDebugManager Interface</span></span>

<span data-ttu-id="bc8c7-104">호스트에서 작업 집합을 식별자와 이름에 연결할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-104">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc8c7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-105">Methods</span></span>  
  
|<span data-ttu-id="bc8c7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-106">Method</span></span>|<span data-ttu-id="bc8c7-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc8c7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc8c7-108">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-108">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="bc8c7-109">작업을 식별자와 연결 하기 위해 호스트와 디버거 간에 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-109">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="bc8c7-110">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-110">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="bc8c7-111">작업 목록과 식별자 및 이름 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-111">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="bc8c7-112">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-112">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="bc8c7-113">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="bc8c7-113">This method is not implemented.</span></span>|  
|[<span data-ttu-id="bc8c7-114">IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-114">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="bc8c7-115">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-115">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="bc8c7-116">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-116">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="bc8c7-117">[ICLRTask](iclrtask-interface.md) 인스턴스 목록을 식별자 및 이름과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-117">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="bc8c7-118">SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-118">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="bc8c7-119">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="bc8c7-119">This method is not implemented.</span></span>|  
|[<span data-ttu-id="bc8c7-120">SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="bc8c7-120">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="bc8c7-121">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-121">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="bc8c7-122">이 정책은 줄 번호와 파일에 대 한 정보가 호출 스택에 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-122">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc8c7-123">설명</span><span class="sxs-lookup"><span data-stu-id="bc8c7-123">Remarks</span></span>  

 <span data-ttu-id="bc8c7-124">디버깅 시나리오에서 호스트는 자체 프로그래밍 논리에 따라 작업을 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-124">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="bc8c7-125">예를 들어, 그룹화를 통해 개발자는 프로세스에서 실행 되는 모든 작업을 확인 하는 대신 개발자의 Api에 필요한 작업만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-125">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="bc8c7-126">`ICLRDebugManager` 호스트에서 이러한 종류의 그룹화를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-126">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bc8c7-127">, 및의 세 가지 `ICLRDebugManager` 메서드 `BeginConnection` `SetConnectionTasks` `EndConnection` 는 서로 종속 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-127">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="bc8c7-128">이러한 작업은 예상 대로 작동 하기 위해 지정 된 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-128">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="bc8c7-129">호스트에서 그룹화에 할당 하는 그룹화 및 식별자와 이름에는 CLR (공용 언어 런타임)에 대 한 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-129">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="bc8c7-130">CLR은 단순히 디버거로 정보를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-130">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc8c7-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc8c7-131">Requirements</span></span>  

 <span data-ttu-id="bc8c7-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc8c7-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bc8c7-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc8c7-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc8c7-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc8c7-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc8c7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8c7-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc8c7-136">See also</span></span>

- [<span data-ttu-id="bc8c7-137">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc8c7-137">Hosting Interfaces</span></span>](hosting-interfaces.md)
