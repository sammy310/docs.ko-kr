---
description: '자세히 알아보기: ICorDebugThread 인터페이스'
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
ms.openlocfilehash: 7e16fa2a82a004a5c85d60a278cdd14df6ab2300
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658830"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="0c92f-103">ICorDebugThread 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c92f-103">ICorDebugThread Interface</span></span>

<span data-ttu-id="0c92f-104">프로세스의 스레드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c92f-104">Represents a thread in a process.</span></span> <span data-ttu-id="0c92f-105">`ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c92f-105">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c92f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-106">Methods</span></span>  
  
|<span data-ttu-id="0c92f-107">메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-107">Method</span></span>|<span data-ttu-id="0c92f-108">설명</span><span class="sxs-lookup"><span data-stu-id="0c92f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c92f-109">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-109">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="0c92f-110">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="0c92f-110">This method is not implemented.</span></span> <span data-ttu-id="0c92f-111">이 메서드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="0c92f-111">Do not use it.</span></span>|  
|[<span data-ttu-id="0c92f-112">CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-112">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="0c92f-113">이에 대해 작동 하는 ICorDebugEval 개체를 만듭니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-113">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-114">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-114">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="0c92f-115">이에서 활성 프레임을 단계별로 실행할 수 있도록 하는 ICorDebugStepper 개체를 만듭니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-115">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-116">EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-116">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="0c92f-117">이의 모든 스택 체인을 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-117">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-118">GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-118">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="0c92f-119">이에 대 한 활성 ICorDebugChain 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-119">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-120">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-120">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="0c92f-121">이에 대 한 활성 ICorDebugFrame 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-121">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-122">GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-122">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="0c92f-123">현재 실행 중인 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-123">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="0c92f-124">GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-124">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="0c92f-125">관리 코드에서 현재 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c92f-125">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="0c92f-126">GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-126">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="0c92f-127">이의 현재 디버그 상태를 설명 하는 CorDebugThreadState 값을 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-127">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-128">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-128">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="0c92f-129">이의 활성 부분에 대 한 현재 핸들을 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-129">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-130">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-130">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="0c92f-131">이의 활성 부분에 대 한 현재 운영 체제 식별자를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-131">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-132">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-132">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="0c92f-133">CLR (공용 언어 런타임) 스레드에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c92f-133">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="0c92f-134">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-134">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="0c92f-135">파트를 구성 하는 프로세스에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-135">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="0c92f-136">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-136">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="0c92f-137">이와 연결 된 레지스터 집합에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-137">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-138">GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-138">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="0c92f-139">이의 현재 상태를 설명 하는 CorDebugUserState 값의 비트 조합을 가져옵니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-139">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="0c92f-140">SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="0c92f-140">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="0c92f-141">`CorDebugThreadState`이의 디버깅 상태를 설명 하는 값의 비트 조합을 설정 합니다 `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="0c92f-141">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c92f-142">설명</span><span class="sxs-lookup"><span data-stu-id="0c92f-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c92f-143">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c92f-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c92f-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c92f-144">Requirements</span></span>  

 <span data-ttu-id="0c92f-145">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c92f-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c92f-146">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c92f-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c92f-147">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c92f-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c92f-148">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c92f-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c92f-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c92f-149">See also</span></span>

- [<span data-ttu-id="0c92f-150">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c92f-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
