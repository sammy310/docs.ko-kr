---
description: '자세히 알아보기: ICorDebugStepper 인터페이스'
title: ICorDebugStepper 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
ms.openlocfilehash: a16df9d25b4d87b0638448c1fdf8fec4759261d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803596"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="61cfa-103">ICorDebugStepper 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61cfa-103">ICorDebugStepper Interface</span></span>

<span data-ttu-id="61cfa-104">디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-104">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61cfa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-105">Methods</span></span>  
  
|<span data-ttu-id="61cfa-106">메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-106">Method</span></span>|<span data-ttu-id="61cfa-107">설명</span><span class="sxs-lookup"><span data-stu-id="61cfa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61cfa-108">Deactivate 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-108">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="61cfa-109">이 `ICorDebugStepper` 로 인해 마지막으로 수신한 단계 명령이 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-109">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="61cfa-110">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-110">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="61cfa-111">이가 현재 단계를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다 `ICorDebugStepper` .</span><span class="sxs-lookup"><span data-stu-id="61cfa-111">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="61cfa-112">SetInterceptMask 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-112">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="61cfa-113">단계별 코드의 형식을 지정 하는 CorDebugIntercept 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-113">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="61cfa-114">SetRangeIL 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-114">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="61cfa-115">[ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) 에 대 한 호출이 네이티브 코드를 기준으로 인수 값을 전달 하는지 또는 단계별로 진행 중인 메서드의 MSIL (Microsoft 중간 언어) 코드를 기준으로 인수 값을 전달 하는지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-115">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="61cfa-116">SetUnmappedStopMask 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-116">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="61cfa-117">실행이 중단 되는 매핑되지 않은 코드의 형식을 지정 하는 CorDebugUnmappedStop 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-117">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="61cfa-118">Step 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-118">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="61cfa-119">이 `ICorDebugStepper` 를 통해 포함 하는 스레드를 한 단계씩 실행 하 고 필요에 따라 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-119">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="61cfa-120">StepOut 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-120">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="61cfa-121">이 `ICorDebugStepper` 를 포함 하는 스레드를 한 단계씩 실행 하 고 현재 프레임에서 제어를 호출 프레임으로 반환할 때 완료 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-121">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="61cfa-122">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="61cfa-122">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="61cfa-123">이 `ICorDebugStepper` 를 통해 포함 하는 스레드를 한 단계씩 실행 하 고 지정 된 범위를 벗어난 코드에 도달 하면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-123">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61cfa-124">설명</span><span class="sxs-lookup"><span data-stu-id="61cfa-124">Remarks</span></span>  

 <span data-ttu-id="61cfa-125">`ICorDebugStepper`인터페이스는 다음과 같은 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-125">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="61cfa-126">실행 되는 단계 명령과 해당 명령의 완료 사이에 식별자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-126">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="61cfa-127">수행할 수 있는 모든 단계를 캡슐화 하는 중앙 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-127">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="61cfa-128">단계별 작업을 중간에 취소 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-128">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="61cfa-129">스레드 당 두 개 이상의 스텝 퍼가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-129">There can be more than one stepper per thread.</span></span> <span data-ttu-id="61cfa-130">예를 들어 함수를 프로시저 단위로 실행 하는 동안 중단점이 적중 될 수 있으며 사용자가 해당 함수 내에서 새로운 단계별 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-130">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="61cfa-131">이 상황을 처리 하는 방법을 결정 하는 것은 디버거를 통해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-131">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="61cfa-132">디버거가 원래 단계별 작업을 취소 하거나 두 작업을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-132">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="61cfa-133">`ICorDebugStepper`인터페이스는 두 옵션을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-133">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="61cfa-134">CLR (공용 언어 런타임)이 크로스 스레드 마샬링된 호출을 수행 하는 경우 스텝 퍼는 스레드 간에 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-134">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61cfa-135">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61cfa-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61cfa-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61cfa-136">Requirements</span></span>  

 <span data-ttu-id="61cfa-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61cfa-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61cfa-138">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61cfa-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61cfa-139">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61cfa-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61cfa-140">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61cfa-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cfa-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61cfa-141">See also</span></span>

- [<span data-ttu-id="61cfa-142">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61cfa-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
