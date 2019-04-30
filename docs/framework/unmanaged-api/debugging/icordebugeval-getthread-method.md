---
title: ICorDebugEval::GetThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cc5b6e7c6fe44080b35dc07f029ad311b88ca7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989055"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="d0276-102">ICorDebugEval::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="d0276-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="d0276-103">이 평가 실행 되거나 실행 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0276-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0276-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0276-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0276-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0276-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="d0276-106">[out] 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0276-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0276-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0276-107">Requirements</span></span>  
 <span data-ttu-id="d0276-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0276-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0276-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0276-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0276-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0276-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0276-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0276-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
