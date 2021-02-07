---
description: '자세히 알아보기: ICorDebugEval:: Abort 메서드'
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
ms.openlocfilehash: d61cb0d696a8a134d992bc8dbbfdb61103ef469f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694320"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="69e2a-103">ICorDebugEval::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="69e2a-103">ICorDebugEval::Abort Method</span></span>

<span data-ttu-id="69e2a-104">이 ICorDebugEval 개체가 현재 수행 하 고 있는 계산을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e2a-104">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="69e2a-105">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="69e2a-106">설명</span><span class="sxs-lookup"><span data-stu-id="69e2a-106">Remarks</span></span>  

 <span data-ttu-id="69e2a-107">계산이 중첩 되 고 가장 최근 계산이 아닌 경우 `Abort` 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e2a-107">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e2a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69e2a-108">Requirements</span></span>  

 <span data-ttu-id="69e2a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69e2a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e2a-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69e2a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69e2a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e2a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e2a-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e2a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
