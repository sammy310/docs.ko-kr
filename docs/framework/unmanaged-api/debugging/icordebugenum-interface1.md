---
description: '자세히 알아보기: ICorDebugEnum 인터페이스'
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
ms.openlocfilehash: 20d2bb14bddcaf40802567ec78a8e318ac1db380
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694476"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="4f2f8-103">ICorDebugEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f2f8-103">ICorDebugEnum Interface</span></span>

<span data-ttu-id="4f2f8-104">디버깅 응용 프로그램에서 사용 하는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-104">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f2f8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-105">Methods</span></span>  
  
|<span data-ttu-id="4f2f8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-106">Method</span></span>|<span data-ttu-id="4f2f8-107">설명</span><span class="sxs-lookup"><span data-stu-id="4f2f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f2f8-108">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-108">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="4f2f8-109">이 `ICorDebugEnum` 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-109">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="4f2f8-110">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-110">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="4f2f8-111">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-111">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="4f2f8-112">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-112">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="4f2f8-113">커서를 열거형의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-113">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="4f2f8-114">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="4f2f8-114">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="4f2f8-115">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-115">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f2f8-116">설명</span><span class="sxs-lookup"><span data-stu-id="4f2f8-116">Remarks</span></span>  

 <span data-ttu-id="4f2f8-117">다음 열거자는에서 파생 됩니다 `ICorDebugEnum` .</span><span class="sxs-lookup"><span data-stu-id="4f2f8-117">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="4f2f8-118">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-118">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-119">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-119">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="4f2f8-120">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-120">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="4f2f8-121">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-121">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-122">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-122">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-123">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-123">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-124">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-124">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="4f2f8-125">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-125">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="4f2f8-126">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-126">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="4f2f8-127">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-127">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="4f2f8-128">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-128">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="4f2f8-129">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-129">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="4f2f8-130">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-130">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="4f2f8-131">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-131">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-132">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-132">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-133">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-133">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-134">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-134">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-135">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-135">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-136">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-136">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="4f2f8-137">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-137">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="4f2f8-138">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="4f2f8-138">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="4f2f8-139">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-139">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f2f8-140">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f2f8-140">Requirements</span></span>  

 <span data-ttu-id="4f2f8-141">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f2f8-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f2f8-142">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f2f8-142">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f2f8-143">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f2f8-143">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f2f8-144">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f2f8-144">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2f8-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f2f8-145">See also</span></span>

- [<span data-ttu-id="4f2f8-146">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f2f8-146">Debugging Interfaces</span></span>](debugging-interfaces.md)
