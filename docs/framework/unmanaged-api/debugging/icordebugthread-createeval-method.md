---
title: ICorDebugThread::CreateEval 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480665"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="a6b9f-102">ICorDebugThread::CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="a6b9f-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="a6b9f-103">수집 하 고이 ICorDebugThread 기능의 노출 ICorDebugEval 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6b9f-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6b9f-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b9f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6b9f-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="a6b9f-106">[out] 주소에 대 한 포인터는 `ICorDebugEval` 수집 하 고이 스레드에 대 한 기능을 노출 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b9f-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6b9f-107">설명</span><span class="sxs-lookup"><span data-stu-id="a6b9f-107">Remarks</span></span>  
 <span data-ttu-id="a6b9f-108">평가 개체는 해당 계산을 수행 하기 전에 스레드의 새 체인을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b9f-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="a6b9f-109">이 현재 수행 중인 스레드에서 계산이 완료 될 때까지 계산을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b9f-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6b9f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6b9f-110">Requirements</span></span>  
 <span data-ttu-id="a6b9f-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6b9f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b9f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6b9f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6b9f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6b9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6b9f-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
