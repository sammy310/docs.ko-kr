---
title: ICorDebugEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085260"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="61789-102">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61789-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="61789-103">디버깅 응용 프로그램에서 사용 하는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61789-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61789-104">메서드</span><span class="sxs-lookup"><span data-stu-id="61789-104">Methods</span></span>  
  
|<span data-ttu-id="61789-105">메서드</span><span class="sxs-lookup"><span data-stu-id="61789-105">Method</span></span>|<span data-ttu-id="61789-106">설명</span><span class="sxs-lookup"><span data-stu-id="61789-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61789-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="61789-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="61789-108">이 `ICorDebugEnum` 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61789-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="61789-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="61789-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="61789-110">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61789-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="61789-111">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="61789-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="61789-112">커서를 열거형의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61789-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="61789-113">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="61789-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="61789-114">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61789-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61789-115">주의</span><span class="sxs-lookup"><span data-stu-id="61789-115">Remarks</span></span>  
 <span data-ttu-id="61789-116">다음 열거자는 `ICorDebugEnum`에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61789-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="61789-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="61789-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="61789-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="61789-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="61789-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="61789-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="61789-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="61789-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="61789-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="61789-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="61789-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="61789-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="61789-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="61789-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="61789-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="61789-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="61789-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="61789-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="61789-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="61789-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="61789-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="61789-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="61789-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="61789-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="61789-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="61789-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="61789-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="61789-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="61789-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="61789-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="61789-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="61789-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="61789-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="61789-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="61789-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="61789-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="61789-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="61789-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="61789-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="61789-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="61789-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="61789-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="61789-138">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61789-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61789-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61789-139">Requirements</span></span>  
 <span data-ttu-id="61789-140">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61789-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61789-141">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61789-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61789-142">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61789-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61789-143">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61789-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61789-144">참조</span><span class="sxs-lookup"><span data-stu-id="61789-144">See also</span></span>

- [<span data-ttu-id="61789-145">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61789-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
