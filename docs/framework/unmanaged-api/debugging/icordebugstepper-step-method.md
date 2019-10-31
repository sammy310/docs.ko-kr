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
ms.openlocfilehash: 43f86e704e4a52a702b8f563e3c613806eb061b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137528"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="11473-102">ICorDebugStepper::Step 메서드</span><span class="sxs-lookup"><span data-stu-id="11473-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="11473-103">이 ICorDebugStepper는 해당 스레드를 포함 하는 스레드를 한 단계씩 실행 하 고, 필요에 따라 스레드 내에서 호출 되는 함수를 통해 단일 단계를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="11473-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11473-104">구문</span><span class="sxs-lookup"><span data-stu-id="11473-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11473-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11473-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="11473-106">진행 `true` 설정 하 여 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11473-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="11473-107">함수를 프로시저 단위로 실행 하려면 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11473-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11473-108">주의</span><span class="sxs-lookup"><span data-stu-id="11473-108">Remarks</span></span>  
 <span data-ttu-id="11473-109">공용 언어 런타임이이 스텝 퍼의 프레임에서 다음의 관리 되는 명령을 수행할 때 단계가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11473-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="11473-110">관리 코드에 없는 스텝 퍼에서 `Step`를 호출 하는 경우 스레드는 다음 관리 코드 명령이 실행 될 때 단계가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11473-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11473-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11473-111">Requirements</span></span>  
 <span data-ttu-id="11473-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11473-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11473-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11473-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11473-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11473-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11473-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11473-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
