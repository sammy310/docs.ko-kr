---
title: ICorDebugStepper::StepRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ace501bf5de741ea110fe4d3bb4bc44843bf8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760530"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="ed62a-102">ICorDebugStepper::StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="ed62a-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="ed62a-103">이 ICorDebugStepper 단일 단계로 포함 스레드를 통해 반환 하는 마지막 지정 된 범위를 벗어난 코드에 도달 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed62a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed62a-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed62a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed62a-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="ed62a-106">[in] 로 `true` 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="ed62a-107">로 `false` 함수를 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="ed62a-108">[in] 범위를 지정 하는 각 COR_DEBUG_STEP_RANGE 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="ed62a-109">[in] `ranges` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed62a-110">설명</span><span class="sxs-lookup"><span data-stu-id="ed62a-110">Remarks</span></span>  
 <span data-ttu-id="ed62a-111">`StepRange` 메서드처럼 작동 합니다 [icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) 메서드를 제외 하 고 지정 된 범위를 벗어난 코드까지 완료 되지 않으면에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="ed62a-112">이 한 번에 하나의 명령을 단계별로 실행 하는 보다 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="ed62a-113">스텝 퍼의 프레임의 시작 부분에서 오프셋된 쌍의 목록으로 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="ed62a-114">범위는 메서드의 Microsoft MSIL (intermediate language) 코드 기준입니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="ed62a-115">호출 [icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) 사용 하 여 `false` 메서드의 네이티브 코드를 기준으로 범위를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed62a-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed62a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed62a-116">Requirements</span></span>  
 <span data-ttu-id="ed62a-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed62a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed62a-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed62a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed62a-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed62a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed62a-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed62a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
