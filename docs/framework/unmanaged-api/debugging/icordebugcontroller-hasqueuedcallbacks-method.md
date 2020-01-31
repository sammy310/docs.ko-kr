---
title: ICorDebugController::HasQueuedCallbacks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: c33193bd64030852441c7ca60cee4a000b09156c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788919"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="60517-102">ICorDebugController::HasQueuedCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="60517-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="60517-103">지정 된 스레드에 대해 관리 되는 콜백이 현재 대기 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="60517-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60517-104">구문</span><span class="sxs-lookup"><span data-stu-id="60517-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60517-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60517-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="60517-106">진행 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="60517-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="60517-107">제한이 현재 지정 된 스레드에 대해 관리 되는 콜백이 현재 큐에 대기 중인 경우 `true` 되는 값에 대 한 포인터입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="60517-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="60517-108">`pThread` 매개 변수에 대해 null이 지정 된 경우 현재 스레드에 대해 대기 중인 관리 되는 콜백이 있으면 `HasQueuedCallbacks` `true` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60517-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60517-109">주의</span><span class="sxs-lookup"><span data-stu-id="60517-109">Remarks</span></span>  
 <span data-ttu-id="60517-110">콜백은 한 번에 하나씩 디스패치 될 때마다 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60517-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="60517-111">디버거는 동시에 발생 하는 여러 디버깅 이벤트를 보고 하려는 경우이 플래그를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60517-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="60517-112">디버깅 이벤트가 큐에 대기 되는 경우 이미 발생 했으므로 디버거가 디버기 상태를 확인할 수 있도록 전체 큐를 드레이닝 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60517-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="60517-113">`ICorDebugController::Continue`를 호출 하 여 큐를 드레이닝 합니다. 예를 들어, 큐에 스레드 *x*에 대 한 두 개의 디버깅 이벤트가 포함 되어 있고 디버거가 첫 번째 디버깅 이벤트 후에 스레드 *x* 를 일시 중단 한 다음 `ICorDebugController::Continue`를 호출 하는 경우 스레드가 일시 중단 된 경우에도 스레드 *x* 에 대 한 두 번째 디버깅 이벤트가 디스패치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60517-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60517-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60517-114">Requirements</span></span>  
 <span data-ttu-id="60517-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60517-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60517-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60517-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60517-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60517-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60517-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60517-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60517-119">참조</span><span class="sxs-lookup"><span data-stu-id="60517-119">See also</span></span>
