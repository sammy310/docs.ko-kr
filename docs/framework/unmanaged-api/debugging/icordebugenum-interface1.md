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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931979"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="b7805-102">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7805-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="b7805-103">디버깅 응용 프로그램에서 사용 하는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7805-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-104">Methods</span></span>  
  
|<span data-ttu-id="b7805-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-105">Method</span></span>|<span data-ttu-id="b7805-106">Description</span><span class="sxs-lookup"><span data-stu-id="b7805-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7805-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="b7805-108">이 복사본을 만들고 `ICorDebugEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="b7805-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="b7805-110">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="b7805-111">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="b7805-112">커서를 열거형의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="b7805-113">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="b7805-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="b7805-114">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7805-115">설명</span><span class="sxs-lookup"><span data-stu-id="b7805-115">Remarks</span></span>  
 <span data-ttu-id="b7805-116">다음 열거자는에서 `ICorDebugEnum`파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="b7805-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="b7805-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="b7805-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="b7805-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="b7805-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="b7805-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="b7805-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="b7805-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="b7805-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="b7805-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="b7805-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="b7805-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="b7805-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="b7805-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="b7805-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="b7805-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="b7805-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="b7805-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="b7805-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="b7805-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="b7805-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="b7805-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="b7805-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="b7805-138">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7805-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7805-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7805-139">Requirements</span></span>  
 <span data-ttu-id="b7805-140">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7805-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7805-141">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7805-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7805-142">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7805-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7805-143">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7805-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7805-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7805-144">See also</span></span>

- [<span data-ttu-id="b7805-145">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7805-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
