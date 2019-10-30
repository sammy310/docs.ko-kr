---
title: ICorDebugEval::Abort 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 78402e5e099815fe309618e692285de91b8b29f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124234"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="fc9d8-102">ICorDebugEval::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="fc9d8-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="fc9d8-103">이 ICorDebugEval 개체가 현재 수행 하 고 있는 계산을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc9d8-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc9d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc9d8-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fc9d8-105">주의</span><span class="sxs-lookup"><span data-stu-id="fc9d8-105">Remarks</span></span>  
 <span data-ttu-id="fc9d8-106">계산이 중첩 되 고 가장 최근 계산이 아닌 경우 `Abort` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc9d8-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc9d8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc9d8-107">Requirements</span></span>  
 <span data-ttu-id="fc9d8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc9d8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc9d8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc9d8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc9d8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc9d8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc9d8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc9d8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
