---
title: ICorDebugChain 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969300"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="cd00a-102">ICorDebugChain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd00a-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="cd00a-103">실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd00a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-104">Methods</span></span>  
  
|<span data-ttu-id="cd00a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-105">Method</span></span>|<span data-ttu-id="cd00a-106">Description</span><span class="sxs-lookup"><span data-stu-id="cd00a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd00a-107">EnumerateFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="cd00a-108">최신 프레임에서 시작 하 여 체인의 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="cd00a-109">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="cd00a-110">체인의 활성 (가장 최근) 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="cd00a-111">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="cd00a-112">이 체인에 의해 호출 된 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="cd00a-113">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="cd00a-114">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="cd00a-115">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="cd00a-116">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-116">Not implemented.</span></span>|  
|[<span data-ttu-id="cd00a-117">GetNext 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="cd00a-118">스레드에 대 한 다음 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="cd00a-119">GetPrevious 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="cd00a-120">스레드에 대 한 이전 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="cd00a-121">GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="cd00a-122">이 호출 체인의 genesis 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="cd00a-123">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="cd00a-124">이 체인의 활성 부분에 대 한 레지스터 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="cd00a-125">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="cd00a-126">이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="cd00a-127">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="cd00a-128">이 호출 체인이 속한 실제 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="cd00a-129">IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="cd00a-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="cd00a-130">이 체인이 관리 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd00a-131">설명</span><span class="sxs-lookup"><span data-stu-id="cd00a-131">Remarks</span></span>  
 <span data-ttu-id="cd00a-132">체인의 스택 프레임은 연속 된 스택 공간을 차지 하 고 동일한 스레드와 컨텍스트를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="cd00a-133">체인은 관리 코드 체인 또는 비관리 코드 체인을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="cd00a-134">빈 `ICorDebugChain` 인스턴스는 관리 되지 않는 코드 체인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd00a-135">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd00a-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd00a-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd00a-136">Requirements</span></span>  
 <span data-ttu-id="cd00a-137">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd00a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd00a-138">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd00a-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd00a-139">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd00a-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd00a-140">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd00a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd00a-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd00a-141">See also</span></span>

- [<span data-ttu-id="cd00a-142">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd00a-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
