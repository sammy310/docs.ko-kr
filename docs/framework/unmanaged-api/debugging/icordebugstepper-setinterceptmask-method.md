---
title: ICorDebugStepper::SetInterceptMask 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a9d287e6520f1fc7826d85dfbcd8e9a6da22f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481070"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="bbaa0-102">ICorDebugStepper::SetInterceptMask 메서드</span><span class="sxs-lookup"><span data-stu-id="bbaa0-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="bbaa0-103">한 단계씩 코드 형식을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbaa0-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbaa0-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbaa0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbaa0-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="bbaa0-106">[in] 코드의 형식을 지정 하는 CorDebugIntercept 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbaa0-107">설명</span><span class="sxs-lookup"><span data-stu-id="bbaa0-107">Remarks</span></span>  
 <span data-ttu-id="bbaa0-108">인터셉터에 대 한 비트가 설정 된 경우 스텝 퍼는 코드를 차단 하는 지정 된 형식이 발견 될 때 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="bbaa0-109">비트가 지워지면 가로채 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="bbaa0-110">합니다 `SetInterceptMask` 메서드에 있을 수 있습니다 사용 하 여 예측할 수 없는 상호 작용 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (사용자의 관점에서).</span><span class="sxs-lookup"><span data-stu-id="bbaa0-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="bbaa0-111">예를 들어 경우만 표시 됨 (즉, 비-내부) 클래스 초기화 코드의 부분 매핑 정보가 없으며 STOP_NO_MAPPING_INFO 설정 되어 있지 않습니다 (참조를 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 메서드 및 CorDebugUnmappedStop 열거형) 스텝 퍼 클래스 초기화 건너뛰기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="bbaa0-112">기본적으로 INTERCEPT_NONE 값만을 `CorDebugIntercept` 열거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbaa0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbaa0-113">Requirements</span></span>  
 <span data-ttu-id="bbaa0-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbaa0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbaa0-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbaa0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbaa0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbaa0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbaa0-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbaa0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
