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
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379278"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="c28e6-102">ICorDebugThread::CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="c28e6-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="c28e6-103">이 ICorDebugThread의 기능을 수집 하 고 노출 하는 ICorDebugEval 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c28e6-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c28e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c28e6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c28e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c28e6-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="c28e6-106">제한이 `ICorDebugEval`이 스레드의 기능을 수집 하 고 노출 하는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c28e6-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c28e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="c28e6-107">Remarks</span></span>  
 <span data-ttu-id="c28e6-108">계산 개체는 계산을 수행 하기 전에 스레드에 새 체인을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="c28e6-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="c28e6-109">그러면 계산이 완료 될 때까지 현재 스레드에서 수행 중인 계산이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c28e6-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c28e6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c28e6-110">Requirements</span></span>  
 <span data-ttu-id="c28e6-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c28e6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c28e6-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c28e6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c28e6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c28e6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c28e6-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c28e6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
