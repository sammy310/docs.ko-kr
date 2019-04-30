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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969860"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="64e2c-102">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64e2c-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="64e2c-103">호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64e2c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-104">Methods</span></span>  
  
|<span data-ttu-id="64e2c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-105">Method</span></span>|<span data-ttu-id="64e2c-106">설명</span><span class="sxs-lookup"><span data-stu-id="64e2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64e2c-107">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="64e2c-108">작업 식별자 및 이름을 사용 하 여 연결 하려면 호스트와 디버거 간의 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="64e2c-109">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="64e2c-110">작업 목록 및 식별자 및 이름을 간의 연결을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="64e2c-111">GetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="64e2c-112">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="64e2c-113">IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="64e2c-114">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="64e2c-115">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="64e2c-116">연결 목록을 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 식별자 및 이름을 사용 하 여 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="64e2c-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="64e2c-117">SetDacl 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="64e2c-118">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="64e2c-119">SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="64e2c-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="64e2c-120">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="64e2c-121">정책은 호출 스택의 줄 번호 및 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64e2c-122">설명</span><span class="sxs-lookup"><span data-stu-id="64e2c-122">Remarks</span></span>  
 <span data-ttu-id="64e2c-123">디버깅 시나리오에서 호스트 자체 프로그래밍 논리에 따라 작업을 그룹화 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="64e2c-124">예를 들어, 그룹화를 개발자가 프로세스에서 실행 중인 작업을 확인 하는 대신 개발자가 Api에 필요한 작업만 표시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="64e2c-125">`ICLRDebugManager` 이 유형의 그룹화를 구현 하는 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64e2c-126">세 `ICLRDebugManager` 메서드를 `BeginConnection`를 `SetConnectionTasks` 및 `EndConnection`, 서로 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="64e2c-127">예상 대로 작동 하는 지정 된 순서로 호출 해야만 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="64e2c-128">그룹화 식별자 및 호스트를 그룹에 할당 하는 이름을 CLR (공용 언어 런타임)에 대 한 다음과 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="64e2c-129">CLR은 디버거를 따라 정보를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e2c-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e2c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64e2c-130">Requirements</span></span>  
 <span data-ttu-id="64e2c-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="64e2c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e2c-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64e2c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64e2c-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="64e2c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64e2c-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e2c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e2c-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="64e2c-135">See also</span></span>

- [<span data-ttu-id="64e2c-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64e2c-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
