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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 682d6684b6c86485530b9e5283d843f3b2eb7e46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995997"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="e614d-102">ICorDebugEval::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="e614d-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="e614d-103">ICorDebugEval 개체가이 현재 수행 하는 계산을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e614d-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e614d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e614d-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e614d-105">설명</span><span class="sxs-lookup"><span data-stu-id="e614d-105">Remarks</span></span>  
 <span data-ttu-id="e614d-106">평가 중첩 되어 있고 가장 최근의 것 없는 경우는 `Abort` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e614d-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e614d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e614d-107">Requirements</span></span>  
 <span data-ttu-id="e614d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e614d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e614d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e614d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e614d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e614d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e614d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e614d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
