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
ms.openlocfilehash: 6ae0fec0f8de2bbe3862f9f70ed9cf3d32af34c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894208"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="a1238-102">ICorDebugChain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1238-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="a1238-103">실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1238-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-104">Methods</span></span>  
  
|<span data-ttu-id="a1238-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-105">Method</span></span>|<span data-ttu-id="a1238-106">설명</span><span class="sxs-lookup"><span data-stu-id="a1238-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1238-107">EnumerateFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="a1238-108">최신 프레임에서 시작 하 여 체인의 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="a1238-109">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="a1238-110">체인의 활성 (가장 최근) 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="a1238-111">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="a1238-112">이 체인에 의해 호출 된 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="a1238-113">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="a1238-114">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="a1238-115">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="a1238-116">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-116">Not implemented.</span></span>|  
|[<span data-ttu-id="a1238-117">GetNext 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="a1238-118">스레드에 대 한 다음 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a1238-119">GetPrevious 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="a1238-120">스레드에 대 한 이전 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a1238-121">GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="a1238-122">이 호출 체인의 genesis 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="a1238-123">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="a1238-124">이 체인의 활성 부분에 대 한 레지스터 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="a1238-125">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="a1238-126">이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="a1238-127">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="a1238-128">이 호출 체인이 속한 실제 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="a1238-129">IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="a1238-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="a1238-130">이 체인이 관리 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1238-131">설명</span><span class="sxs-lookup"><span data-stu-id="a1238-131">Remarks</span></span>  
 <span data-ttu-id="a1238-132">체인의 스택 프레임은 연속 된 스택 공간을 차지 하 고 동일한 스레드와 컨텍스트를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="a1238-133">체인은 관리 코드 체인 또는 비관리 코드 체인을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="a1238-134">빈 `ICorDebugChain` 인스턴스는 관리 되지 않는 코드 체인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1238-135">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1238-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1238-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1238-136">Requirements</span></span>  
 <span data-ttu-id="a1238-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1238-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1238-138">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1238-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1238-139">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1238-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1238-140">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1238-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1238-141">참조</span><span class="sxs-lookup"><span data-stu-id="a1238-141">See also</span></span>

- [<span data-ttu-id="a1238-142">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1238-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
