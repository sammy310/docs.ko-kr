---
description: '자세한 내용은 다음에 대해 자세히 알아보세요. ICorDebugEval2:: Dedeabort 메서드'
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
ms.openlocfilehash: 2835fd635da007b5ee3f0e642b77f3954945f168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693514"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="ded0d-103">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ded0d-103">ICorDebugEval2::RudeAbort Method</span></span>

<span data-ttu-id="ded0d-104">현재 수행 중인 계산을 중단 `ICorDebugEval2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded0d-104">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded0d-105">구문</span><span class="sxs-lookup"><span data-stu-id="ded0d-105">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ded0d-106">설명</span><span class="sxs-lookup"><span data-stu-id="ded0d-106">Remarks</span></span>  

 <span data-ttu-id="ded0d-107">`RudeAbort` 는 계산기가 보유 하 고 있는 잠금을 해제 하지 않으므로 디버깅 세션이 안전 하지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded0d-107">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="ded0d-108">매우 주의 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded0d-108">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ded0d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ded0d-109">Requirements</span></span>  

 <span data-ttu-id="ded0d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ded0d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded0d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ded0d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ded0d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ded0d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ded0d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded0d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
