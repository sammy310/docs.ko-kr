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
ms.openlocfilehash: 9792abb4ee38a45aae59eaf79f1f0499539bd2ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791760"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="c2ea7-102">ICorDebugStepper::SetInterceptMask 메서드</span><span class="sxs-lookup"><span data-stu-id="c2ea7-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="c2ea7-103">단계별 코드의 형식을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ea7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2ea7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2ea7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2ea7-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="c2ea7-106">진행 코드 형식을 지정 하는 CorDebugIntercept 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2ea7-107">주의</span><span class="sxs-lookup"><span data-stu-id="c2ea7-107">Remarks</span></span>  
 <span data-ttu-id="c2ea7-108">인터셉터의 비트가 설정 된 경우 지정 된 가로채기 코드 형식이 발견 되 면 스텝 퍼가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="c2ea7-109">비트를 지우면 가로채기 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="c2ea7-110">`SetInterceptMask` 메서드는 사용자의 관점에서 [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 와의 예기치 않은 상호 작용을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="c2ea7-111">예를 들어 클래스 초기화 코드의 유일 하 게 표시 되는 (즉, 비 내부) 부분에 매핑 정보가 없고 STOP_NO_MAPPING_INFO 설정 되지 않은 경우 ( [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 메서드 및 CorDebugUnmappedStop 열거형 참조) 스텝 퍼는 클래스 초기화를 프로시저 단위로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="c2ea7-112">기본적으로 `CorDebugIntercept` 열거형의 INTERCEPT_NONE 값만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2ea7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2ea7-113">Requirements</span></span>  
 <span data-ttu-id="c2ea7-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ea7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2ea7-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2ea7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2ea7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2ea7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2ea7-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2ea7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
