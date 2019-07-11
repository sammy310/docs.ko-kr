---
title: ICorDebugStepper::Step 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d0f601c4b454b55edc5fa25eb2ee33d491009b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760577"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="2b8c3-102">ICorDebugStepper::Step 메서드</span><span class="sxs-lookup"><span data-stu-id="2b8c3-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="2b8c3-103">단일 단계로 포함 스레드를 통해를 필요에 따라이 ICorDebugStepper 하면 한 단계씩 스레드 내에서 호출 된 함수를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b8c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b8c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b8c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b8c3-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="2b8c3-106">[in] 로 `true` 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="2b8c3-107">로 `false` 함수를 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b8c3-108">설명</span><span class="sxs-lookup"><span data-stu-id="2b8c3-108">Remarks</span></span>  
 <span data-ttu-id="2b8c3-109">공용 언어 런타임에서이 스텝 퍼이 프레임에서 다음 관리 되는 명령을 수행 단계 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="2b8c3-110">경우 `Step` 는 관리 코드에 없는 스텝에서 호출 되 면, 단계는 다음 관리 되는 코드 명령이 스레드에 의해 실행 될 때 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b8c3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b8c3-111">Requirements</span></span>  
 <span data-ttu-id="2b8c3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b8c3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8c3-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b8c3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b8c3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b8c3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b8c3-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b8c3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
