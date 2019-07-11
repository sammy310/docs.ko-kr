---
title: ICorDebugFrame::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd105a5cbdb857aaa902e60968ff1d94473259b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754247"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="eb585-102">ICorDebugFrame::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="eb585-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="eb585-103">디버거가이 ICorDebugFrame 기준으로 단계별 실행 작업을 수행할 수 있도록 스텝을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb585-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb585-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb585-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb585-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb585-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="eb585-106">[out] 디버거를 현재 프레임을 기준으로 단계별 실행 작업을 수행할 수 있도록 ICorDebugStepper 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb585-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb585-107">설명</span><span class="sxs-lookup"><span data-stu-id="eb585-107">Remarks</span></span>  
 <span data-ttu-id="eb585-108">프레임이 활성 상태인 경우에 스텝 퍼 개체를 해당 단계가 완료 되기 전에 프레임으로 반환 일반적으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb585-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb585-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb585-109">Requirements</span></span>  
 <span data-ttu-id="eb585-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb585-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb585-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb585-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb585-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb585-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb585-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb585-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
