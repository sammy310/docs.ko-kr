---
title: ICorDebugThread 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184706"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="18042-102">ICorDebugThread 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18042-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="18042-103">프로세스의 스레드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18042-103">Represents a thread in a process.</span></span> <span data-ttu-id="18042-104">`ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18042-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18042-105">메서드</span><span class="sxs-lookup"><span data-stu-id="18042-105">Methods</span></span>  
  
|<span data-ttu-id="18042-106">메서드</span><span class="sxs-lookup"><span data-stu-id="18042-106">Method</span></span>|<span data-ttu-id="18042-107">설명</span><span class="sxs-lookup"><span data-stu-id="18042-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18042-108">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="18042-109">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="18042-109">This method is not implemented.</span></span> <span data-ttu-id="18042-110">이 메서드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="18042-110">Do not use it.</span></span>|  
|[<span data-ttu-id="18042-111">CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="18042-112">이 작동 하는 ICorDebugEval 개체를 만듭니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-113">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="18042-114">이 활성 프레임을 단계별로 있도록 ICorDebugStepper 개체를 만듭니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-115">EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="18042-116">이 스택 체인을 모두 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-117">GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="18042-118">이 활성 ICorDebugChain 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-119">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="18042-120">이 활성 ICorDebugFrame 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-121">GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="18042-122">이 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 현재 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="18042-123">GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="18042-124">현재 관리 코드에 의해 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18042-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="18042-125">GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="18042-126">이 현재 디버그 상태를 설명 하는 CorDebugThreadState 값을 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-127">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="18042-128">현재 핸들의 활성 부분을 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-129">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="18042-130">이 활성 부분의 작업은 현재 운영 체제 식별자를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-131">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="18042-132">공용 언어 런타임 (CLR) 스레드에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18042-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="18042-133">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="18042-134">이 프로세스에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 일부를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="18042-135">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="18042-136">와 연결 된 등록 집합에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-137">GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="18042-138">현재 상태를 설명 하는 CorDebugUserState 값의 비트 조합을 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="18042-139">SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="18042-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="18042-140">설정의 조합 `CorDebugThreadState` 이 디버깅 상태를 설명 하는 값 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="18042-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18042-141">설명</span><span class="sxs-lookup"><span data-stu-id="18042-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18042-142">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18042-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18042-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18042-143">Requirements</span></span>  
 <span data-ttu-id="18042-144">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18042-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18042-145">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18042-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18042-146">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18042-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18042-147">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18042-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18042-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="18042-148">See also</span></span>

- [<span data-ttu-id="18042-149">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18042-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
