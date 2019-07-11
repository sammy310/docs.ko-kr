---
title: ICorDebugEval2::RudeAbort 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754344"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="6a5a4-102">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="6a5a4-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="6a5a4-103">계산 중단이 `ICorDebugEval2` 현재 수행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5a4-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a5a4-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6a5a4-105">설명</span><span class="sxs-lookup"><span data-stu-id="6a5a4-105">Remarks</span></span>  
 <span data-ttu-id="6a5a4-106">`RudeAbort` 디버깅 세션을 안전 하지 않은 상태로 둡니다 계산기가 보유 하 고 있는 잠금을 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5a4-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="6a5a4-107">주의이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5a4-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5a4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a5a4-108">Requirements</span></span>  
 <span data-ttu-id="6a5a4-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a5a4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5a4-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a5a4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a5a4-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a5a4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a5a4-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a5a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
