---
description: '자세히 알아보기: ICorDebugStepper:: StepRange 메서드'
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
ms.openlocfilehash: 868925ef301cca15b7887505e879f5fff02002e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717565"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="73975-103">ICorDebugStepper::StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="73975-103">ICorDebugStepper::StepRange Method</span></span>

<span data-ttu-id="73975-104">이 ICorDebugStepper는 포함 하는 스레드를 한 단계씩 실행 하 고 지정 된 범위를 벗어난 코드에 도달 하면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73975-104">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73975-105">구문</span><span class="sxs-lookup"><span data-stu-id="73975-105">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73975-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73975-106">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="73975-107">진행 `true` 스레드 내에서 호출 되는 함수를 한 단계씩 실행 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73975-107">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="73975-108">함수를 `false` 프로시저 단위로 실행 하려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73975-108">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="73975-109">진행 각각 범위를 지정 하는 COR_DEBUG_STEP_RANGE 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="73975-109">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="73975-110">[in] `ranges` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="73975-110">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73975-111">설명</span><span class="sxs-lookup"><span data-stu-id="73975-111">Remarks</span></span>  

 <span data-ttu-id="73975-112">`StepRange`메서드는 지정 된 범위를 벗어난 코드에 도달할 때까지 완료 되지 않는다는 점을 제외 하 고는 [ICorDebugStepper:: Step](icordebugstepper-step-method.md) 메서드와 유사 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="73975-112">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="73975-113">이는 한 번에 하나의 명령을 실행 하는 것 보다 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73975-113">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="73975-114">범위는 스텝 퍼 프레임의 시작 부분에서 오프셋 쌍의 목록으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73975-114">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="73975-115">범위는 메서드의 MSIL (Microsoft 중간 언어) 코드를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="73975-115">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="73975-116">[ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) 를 호출 `false` 하 여 메서드의 네이티브 코드를 기준으로 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73975-116">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73975-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73975-117">Requirements</span></span>  

 <span data-ttu-id="73975-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73975-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73975-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73975-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73975-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73975-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73975-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73975-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
