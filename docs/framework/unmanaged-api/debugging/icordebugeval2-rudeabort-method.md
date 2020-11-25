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
ms.openlocfilehash: 478772925dfb7ca7389b5267433f9b06ace3d5a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729618"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="cd172-102">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="cd172-102">ICorDebugEval2::RudeAbort Method</span></span>

<span data-ttu-id="cd172-103">현재 수행 중인 계산을 중단 `ICorDebugEval2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd172-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd172-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd172-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd172-105">설명</span><span class="sxs-lookup"><span data-stu-id="cd172-105">Remarks</span></span>  

 <span data-ttu-id="cd172-106">`RudeAbort` 는 계산기가 보유 하 고 있는 잠금을 해제 하지 않으므로 디버깅 세션이 안전 하지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd172-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="cd172-107">매우 주의 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd172-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd172-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd172-108">Requirements</span></span>  

 <span data-ttu-id="cd172-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd172-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd172-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd172-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd172-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd172-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd172-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd172-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
