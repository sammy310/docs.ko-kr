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
ms.openlocfilehash: e901c65824ee8d6949c79c7778944148c0d9eb28
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976059"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="d2fbb-102">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="d2fbb-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="d2fbb-103">현재 수행 중인 계산 `ICorDebugEval2` 을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fbb-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2fbb-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2fbb-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d2fbb-105">설명</span><span class="sxs-lookup"><span data-stu-id="d2fbb-105">Remarks</span></span>  
 <span data-ttu-id="d2fbb-106">`RudeAbort`는 계산기가 보유 하 고 있는 잠금을 해제 하지 않으므로 디버깅 세션이 안전 하지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2fbb-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="d2fbb-107">매우 주의 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2fbb-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2fbb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2fbb-108">Requirements</span></span>  
 <span data-ttu-id="d2fbb-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2fbb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2fbb-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2fbb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2fbb-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2fbb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2fbb-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2fbb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
