---
description: '자세히 알아보기: ICorDebugEval 인터페이스'
title: ICorDebugEval 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
ms.openlocfilehash: c6eda0f63b377399cad391346dc6bedfa860e4b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694112"
---
# <a name="icordebugeval-interface"></a><span data-ttu-id="8e745-103">ICorDebugEval 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e745-103">ICorDebugEval Interface</span></span>

<span data-ttu-id="8e745-104">디버깅 중인 코드의 컨텍스트 내에서 디버거가 코드를 실행할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-104">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e745-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-105">Methods</span></span>  
  
|<span data-ttu-id="8e745-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-106">Method</span></span>|<span data-ttu-id="8e745-107">설명</span><span class="sxs-lookup"><span data-stu-id="8e745-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e745-108">Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-108">Abort Method</span></span>](icordebugeval-abort-method.md)|<span data-ttu-id="8e745-109">이 개체가 현재 수행 하 고 있는 계산을 중단 `ICorDebugEval` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-109">Aborts the computation this `ICorDebugEval` object is currently performing.</span></span>|  
|[<span data-ttu-id="8e745-110">CallFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-110">CallFunction Method</span></span>](icordebugeval-callfunction-method.md)|<span data-ttu-id="8e745-111">지정 된 함수에 대 한 호출을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-111">Sets up a call to the specified function.</span></span> <span data-ttu-id="8e745-112">.NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-112">(Obsolete in the .NET Framework version 2.0; use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.)</span></span>|  
|[<span data-ttu-id="8e745-113">CreateValue 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-113">CreateValue Method</span></span>](icordebugeval-createvalue-method.md)|<span data-ttu-id="8e745-114">초기 값이 0 또는 null 인 지정 된 형식의 "ICorDebugValue" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-114">Gets an interface pointer to an "ICorDebugValue" object of the specified type, with an initial value of zero or null.</span></span> <span data-ttu-id="8e745-115">.NET Framework 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: CreateValueForType](icordebugeval2-createvaluefortype-method.md) 을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e745-115">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.)</span></span>|  
|[<span data-ttu-id="8e745-116">GetResult 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-116">GetResult Method</span></span>](icordebugeval-getresult-method.md)|<span data-ttu-id="8e745-117">`ICorDebugValue`계산 결과를 포함 하는에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-117">Gets an interface pointer to an `ICorDebugValue` that contains the results of the evaluation.</span></span>|  
|[<span data-ttu-id="8e745-118">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-118">GetThread Method</span></span>](icordebugeval-getthread-method.md)|<span data-ttu-id="8e745-119">이 평가가 실행 되거나 실행 되는 "ICorDebugThread"에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-119">Gets an interface pointer to the "ICorDebugThread" where this evaluation is executing or will execute.</span></span>|  
|[<span data-ttu-id="8e745-120">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-120">IsActive Method</span></span>](icordebugeval-isactive-method.md)|<span data-ttu-id="8e745-121">이 개체가 현재 실행 중인지 여부를 나타내는 값을 가져옵니다 `ICorDebugEval` .</span><span class="sxs-lookup"><span data-stu-id="8e745-121">Gets a value that indicates whether this `ICorDebugEval` object is currently executing.</span></span>|  
|[<span data-ttu-id="8e745-122">NewArray 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-122">NewArray Method</span></span>](icordebugeval-newarray-method.md)|<span data-ttu-id="8e745-123">지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-123">Allocates a new array of the specified element type and dimensions.</span></span> <span data-ttu-id="8e745-124">.NET Framework 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e745-124">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.)</span></span>|  
|[<span data-ttu-id="8e745-125">NewObject 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-125">NewObject Method</span></span>](icordebugeval-newobject-method.md)|<span data-ttu-id="8e745-126">새 개체 인스턴스를 할당 하 고 지정 된 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-126">Allocates a new object instance and calls the specified constructor method.</span></span> <span data-ttu-id="8e745-127">.NET Framework 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-127">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.)</span></span>|  
|[<span data-ttu-id="8e745-128">NewObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-128">NewObjectNoConstructor Method</span></span>](icordebugeval-newobjectnoconstructor-method.md)|<span data-ttu-id="8e745-129">생성자 메서드 호출을 시도 하지 않고 지정 된 형식의 새 개체 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-129">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span> <span data-ttu-id="8e745-130">.NET Framework 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-130">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.)</span></span>|  
|[<span data-ttu-id="8e745-131">NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="8e745-131">NewString Method</span></span>](icordebugeval-newstring-method.md)|<span data-ttu-id="8e745-132">지정 된 내용을 사용 하 여 새 문자열 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-132">Allocates a new string object with the specified contents.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e745-133">설명</span><span class="sxs-lookup"><span data-stu-id="8e745-133">Remarks</span></span>  

 <span data-ttu-id="8e745-134">`ICorDebugEval`개체는 평가를 수행 하는 데 사용 되는 특정 스레드의 컨텍스트에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-134">An `ICorDebugEval` object is created in the context of a specific thread that is used to perform the evaluations.</span></span> <span data-ttu-id="8e745-135">지정 된 평가에 사용 되는 모든 개체와 유형은 동일한 응용 프로그램 도메인 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-135">All objects and types used in a given evaluation must reside within the same application domain.</span></span> <span data-ttu-id="8e745-136">해당 응용 프로그램 도메인은 스레드의 현재 응용 프로그램 도메인과 같을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-136">That application domain need not be the same as the current application domain of the thread.</span></span> <span data-ttu-id="8e745-137">평가는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-137">Evaluations can be nested.</span></span>  
  
 <span data-ttu-id="8e745-138">디버거에서 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)를 호출 하 고 [ICorDebugManagedCallback:: EvalComplete](icordebugmanagedcallback-evalcomplete-method.md) callback을 받을 때까지 평가 작업이 완료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-138">The evaluation's operations do not complete until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md), and then receives an [ICorDebugManagedCallback::EvalComplete](icordebugmanagedcallback-evalcomplete-method.md) callback.</span></span> <span data-ttu-id="8e745-139">다른 스레드를 실행 하도록 허용 하지 않고 평가 기능을 사용 해야 하는 경우 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)를 호출하기 전에 [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) 또는 [ICorDebugController:: Stop](icordebugcontroller-stop-method.md)을 사용하여 스레드를 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-139">If you need to use the evaluation functionality without allowing other threads to run, suspend the threads by using either [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) or [ICorDebugController::Stop](icordebugcontroller-stop-method.md) before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
 <span data-ttu-id="8e745-140">평가가 진행 중일 때 사용자 코드가 실행 되기 때문에 클래스 로드 및 중단점을 포함 하 여 모든 디버그 이벤트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-140">Because user code is running when the evaluation is in progress, any debug events can occur, including class loads and breakpoints.</span></span> <span data-ttu-id="8e745-141">디버거에서는 이러한 이벤트에 대 한 콜백을 정상적으로 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-141">The debugger will receive callbacks, as normal, for these events.</span></span> <span data-ttu-id="8e745-142">평가 상태는 일반적인 프로그램 상태 검사의 일부로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-142">The state of the evaluation will be seen as part of the inspection of the normal program state.</span></span> <span data-ttu-id="8e745-143">스택 체인은 `CHAIN_FUNC_EVAL` 체인이 됩니다 ("CorDebugStepReason" 열거 및 [ICorDebugChain:: getreason](icordebugchain-getreason-method.md) 메서드 참조).</span><span class="sxs-lookup"><span data-stu-id="8e745-143">The stack chain will be a `CHAIN_FUNC_EVAL` chain (see the "CorDebugStepReason" enumeration and the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method).</span></span> <span data-ttu-id="8e745-144">전체 디버거 API는 정상적으로 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-144">The full debugger API will continue to operate as normal.</span></span>  
  
 <span data-ttu-id="8e745-145">교착 상태 또는 무한 반복 상황이 발생 하면 사용자 코드가 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-145">If a deadlocked or infinite looping situation arises, the user code may never complete.</span></span> <span data-ttu-id="8e745-146">이러한 경우 프로그램을 다시 시작 하기 전에 [ICorDebugEval:: Abort](icordebugeval-abort-method.md) 를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-146">In such a case, you must call [ICorDebugEval::Abort](icordebugeval-abort-method.md) before resuming the program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e745-147">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e745-147">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e745-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e745-148">Requirements</span></span>  

 <span data-ttu-id="8e745-149">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e745-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e745-150">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e745-150">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e745-151">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e745-151">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e745-152">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e745-152">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e745-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e745-153">See also</span></span>

- [<span data-ttu-id="8e745-154">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e745-154">Debugging Interfaces</span></span>](debugging-interfaces.md)
