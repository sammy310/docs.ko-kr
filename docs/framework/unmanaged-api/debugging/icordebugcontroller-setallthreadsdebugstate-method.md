---
title: ICorDebugController::SetAllThreadsDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: be7fce700756d7120e0853446b7b307ec77c2080
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783768"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="5bb4d-102">ICorDebugController::SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="5bb4d-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="5bb4d-103">프로세스에 있는 모든 관리 되는 스레드의 디버그 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bb4d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bb4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bb4d-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="5bb4d-106">진행 디버그할 스레드의 상태를 지정 하는 "CorDebugThreadState" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="5bb4d-107">진행 디버그 상태 설정에서 제외할 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="5bb4d-108">이 값이 null 이면 스레드가 제외 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bb4d-109">주의</span><span class="sxs-lookup"><span data-stu-id="5bb4d-109">Remarks</span></span>  
 <span data-ttu-id="5bb4d-110">`SetAllThreadsDebugState` 메서드는 [Enumeratethreads 메서드](icordebugcontroller-enumeratethreads-method.md)를 통해 표시 되지 않는 스레드에 영향을 줄 수 있으므로 `SetAllThreadsDebugState` 메서드를 사용 하 여 일시 중단 된 스레드는 `SetAllThreadsDebugState` 메서드를 사용 하 여 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb4d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bb4d-111">Requirements</span></span>  
 <span data-ttu-id="5bb4d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bb4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bb4d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bb4d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bb4d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bb4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bb4d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bb4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb4d-116">참조</span><span class="sxs-lookup"><span data-stu-id="5bb4d-116">See also</span></span>
