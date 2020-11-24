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
ms.openlocfilehash: 1c0037530ae4f40be5bef4da8f398afe5f2bbb91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688291"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="d9ee1-102">ICorDebugThread::CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="d9ee1-102">ICorDebugThread::CreateEval Method</span></span>

<span data-ttu-id="d9ee1-103">이 ICorDebugThread의 기능을 수집 하 고 노출 하는 ICorDebugEval 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ee1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9ee1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ee1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9ee1-105">Parameters</span></span>  

 `ppEval`  
 <span data-ttu-id="d9ee1-106">제한이 `ICorDebugEval` 이 스레드의 기능을 수집 하 고 노출 하는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9ee1-107">설명</span><span class="sxs-lookup"><span data-stu-id="d9ee1-107">Remarks</span></span>  

 <span data-ttu-id="d9ee1-108">계산 개체는 계산을 수행 하기 전에 스레드에 새 체인을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="d9ee1-109">그러면 계산이 완료 될 때까지 현재 스레드에서 수행 중인 계산이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ee1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9ee1-110">Requirements</span></span>  

 <span data-ttu-id="d9ee1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ee1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9ee1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9ee1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9ee1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9ee1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ee1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
