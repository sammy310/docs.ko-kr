---
title: ICorDebugStepper::StepOut 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 6c1d7db8aacaf81d47abd4a9cd972b44f56a3bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137517"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="50d81-102">ICorDebugStepper::StepOut 메서드</span><span class="sxs-lookup"><span data-stu-id="50d81-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="50d81-103">이 ICorDebugStepper이 포함 하는 스레드를 한 단계씩 실행 하 고 현재 프레임에서 제어를 호출 프레임으로 반환할 때 완료 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d81-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50d81-104">구문</span><span class="sxs-lookup"><span data-stu-id="50d81-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="50d81-105">주의</span><span class="sxs-lookup"><span data-stu-id="50d81-105">Remarks</span></span>  
 <span data-ttu-id="50d81-106">현재 프레임에서 호출 프레임으로 정상적으로 반환 된 후 `StepOut` 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d81-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="50d81-107">비관리 코드에서 `StepOut`가 호출 되 면 현재 프레임이 해당를 호출한 관리 코드로 반환 될 때 단계가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d81-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="50d81-108">.NET Framework 버전 2.0에서는 STOP_UNMANAGED 플래그가 설정 된 `StepOut`를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50d81-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="50d81-109">( [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 를 사용 하 여 단계별 실행 플래그를 설정 합니다.) Interop 디버거는 네이티브 코드 자체를 프로시저 단위로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d81-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50d81-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50d81-110">Requirements</span></span>  
 <span data-ttu-id="50d81-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50d81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50d81-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50d81-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50d81-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50d81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50d81-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50d81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
