---
description: '자세히 알아보기: ICorDebugChain 인터페이스'
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
ms.openlocfilehash: 391c9a3e54d06d303728da5ab7f105bc8e2558ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661209"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="011aa-103">ICorDebugChain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="011aa-103">ICorDebugChain Interface</span></span>

<span data-ttu-id="011aa-104">실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-104">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="011aa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-105">Methods</span></span>  
  
|<span data-ttu-id="011aa-106">메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-106">Method</span></span>|<span data-ttu-id="011aa-107">설명</span><span class="sxs-lookup"><span data-stu-id="011aa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="011aa-108">EnumerateFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-108">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="011aa-109">최신 프레임에서 시작 하 여 체인의 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-109">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="011aa-110">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-110">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="011aa-111">체인의 활성 (가장 최근) 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-111">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="011aa-112">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-112">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="011aa-113">이 체인에 의해 호출 된 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-113">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="011aa-114">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-114">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="011aa-115">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-115">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="011aa-116">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-116">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="011aa-117">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-117">Not implemented.</span></span>|  
|[<span data-ttu-id="011aa-118">GetNext 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-118">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="011aa-119">스레드에 대 한 다음 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-119">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="011aa-120">GetPrevious 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-120">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="011aa-121">스레드에 대 한 이전 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-121">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="011aa-122">GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-122">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="011aa-123">이 호출 체인의 genesis 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-123">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="011aa-124">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-124">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="011aa-125">이 체인의 활성 부분에 대 한 레지스터 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-125">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="011aa-126">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-126">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="011aa-127">이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-127">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="011aa-128">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-128">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="011aa-129">이 호출 체인이 속한 실제 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-129">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="011aa-130">IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="011aa-130">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="011aa-131">이 체인이 관리 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-131">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="011aa-132">설명</span><span class="sxs-lookup"><span data-stu-id="011aa-132">Remarks</span></span>  

 <span data-ttu-id="011aa-133">체인의 스택 프레임은 연속 된 스택 공간을 차지 하 고 동일한 스레드와 컨텍스트를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-133">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="011aa-134">체인은 관리 코드 체인 또는 비관리 코드 체인을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-134">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="011aa-135">빈 `ICorDebugChain` 인스턴스는 관리 되지 않는 코드 체인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-135">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="011aa-136">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="011aa-136">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="011aa-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="011aa-137">Requirements</span></span>  

 <span data-ttu-id="011aa-138">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="011aa-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="011aa-139">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="011aa-139">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="011aa-140">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="011aa-140">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="011aa-141">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="011aa-141">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011aa-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="011aa-142">See also</span></span>

- [<span data-ttu-id="011aa-143">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="011aa-143">Debugging Interfaces</span></span>](debugging-interfaces.md)
