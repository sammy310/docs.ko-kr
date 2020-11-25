---
title: CorDebugThreadState 열거형
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 5eee2aee5873fe512136bc5407e395acdc31af29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722611"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="e1a07-102">CorDebugThreadState 열거형</span><span class="sxs-lookup"><span data-stu-id="e1a07-102">CorDebugThreadState Enumeration</span></span>

<span data-ttu-id="e1a07-103">디버깅을 위한 스레드 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a07-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1a07-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="e1a07-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e1a07-105">Members</span></span>  
  
|<span data-ttu-id="e1a07-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1a07-106">Member</span></span>|<span data-ttu-id="e1a07-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1a07-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="e1a07-108">디버그 이벤트가 발생 하지 않는 한 스레드는 자유롭게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="e1a07-109">스레드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1a07-110">설명</span><span class="sxs-lookup"><span data-stu-id="e1a07-110">Remarks</span></span>  

 <span data-ttu-id="e1a07-111">디버거는 열거형을 사용 하 여 `CorDebugThreadState` 스레드의 실행을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="e1a07-112">[ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) 또는 [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) 메서드를 사용 하 여 스레드 상태를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="e1a07-113">[호스팅 API](../hosting/index.md) 에 제공 된 콜백에서 메시지 펌프를 사용할 수 있으므로 중단 된 상태가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a07-113">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a07-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1a07-114">Requirements</span></span>  

 <span data-ttu-id="e1a07-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a07-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a07-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1a07-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1a07-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a07-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a07-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a07-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a07-119">참조</span><span class="sxs-lookup"><span data-stu-id="e1a07-119">See also</span></span>

- [<span data-ttu-id="e1a07-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="e1a07-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
