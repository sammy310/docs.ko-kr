---
title: ICorDebugStepper::SetRangeIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9b4ee64022374cb4e1950acceb3f32925b736bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478689"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="8e78d-102">ICorDebugStepper::SetRangeIL 메서드</span><span class="sxs-lookup"><span data-stu-id="8e78d-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="8e78d-103">지정 하는 값을 설정 하는지 여부를 호출 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 네이티브 코드를 기준으로 하거나 Microsoft 기준으로 값을 중간 언어 (MSIL) 코드 단계별 되는 메서드의 인수를 전달 합니다. 통해</span><span class="sxs-lookup"><span data-stu-id="8e78d-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e78d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e78d-104">Syntax</span></span>  
  
```  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e78d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e78d-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="8e78d-106">[in] 로 `true` MSIL 코드를 기준으로 범위는 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e78d-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="8e78d-107">로 `false` 네이티브 코드에 상대적인 범위는 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e78d-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="8e78d-108">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e78d-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e78d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e78d-109">Requirements</span></span>  
 <span data-ttu-id="8e78d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e78d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e78d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e78d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e78d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e78d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e78d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e78d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
