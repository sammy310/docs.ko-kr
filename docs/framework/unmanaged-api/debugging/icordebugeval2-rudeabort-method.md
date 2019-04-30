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
ms.openlocfilehash: 0aabff090634f1ecdeec5636336ad1fb77b8b81c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988925"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="dbf05-102">ICorDebugEval2::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="dbf05-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="dbf05-103">계산 중단이 `ICorDebugEval2` 현재 수행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="dbf05-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf05-104">구문</span><span class="sxs-lookup"><span data-stu-id="dbf05-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dbf05-105">설명</span><span class="sxs-lookup"><span data-stu-id="dbf05-105">Remarks</span></span>  
 <span data-ttu-id="dbf05-106">`RudeAbort` 디버깅 세션을 안전 하지 않은 상태로 둡니다 계산기가 보유 하 고 있는 잠금을 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf05-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="dbf05-107">주의이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf05-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbf05-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbf05-108">Requirements</span></span>  
 <span data-ttu-id="dbf05-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbf05-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbf05-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbf05-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbf05-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbf05-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbf05-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf05-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
