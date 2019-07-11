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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760561"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="dee3d-102">ICorDebugStepper::StepOut 메서드</span><span class="sxs-lookup"><span data-stu-id="dee3d-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="dee3d-103">현재 프레임 호출 프레임으로 컨트롤을 반환 하는 경우 완료 하 고 포함 스레드를 통해 단일 단계로이 ICorDebugStepper 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="dee3d-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="dee3d-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dee3d-105">설명</span><span class="sxs-lookup"><span data-stu-id="dee3d-105">Remarks</span></span>  
 <span data-ttu-id="dee3d-106">`StepOut` 호출 프레임에 현재 프레임에서 정상적으로 반환 된 후 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dee3d-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="dee3d-107">경우 `StepOut` 때 호출 된 경우 비관리 코드에서 호출 하는 관리 코드의 현재 프레임을 반환 하는 경우 단계 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dee3d-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="dee3d-108">.NET framework 버전 2.0에서 사용 하지 마십시오 `StepOut` 실패 하기 때문에 플래그가 설정 된 STOP_UNMANAGED를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="dee3d-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="dee3d-109">(사용 하 여 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 단계별 실행에 대 한 플래그를 설정 합니다.) Interop 디버거 나가야 합니다 네이티브 코드 자체입니다.</span><span class="sxs-lookup"><span data-stu-id="dee3d-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dee3d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dee3d-110">Requirements</span></span>  
 <span data-ttu-id="dee3d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dee3d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dee3d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dee3d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dee3d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dee3d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dee3d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee3d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
