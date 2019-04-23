---
title: CorDebugUserState 열거형
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54b2af6e7a200db89bfd7335868a629d7a886fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141312"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="dfe32-102">CorDebugUserState 열거형</span><span class="sxs-lookup"><span data-stu-id="dfe32-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="dfe32-103">스레드의 사용자 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe32-104">구문</span><span class="sxs-lookup"><span data-stu-id="dfe32-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="dfe32-105">멤버</span><span class="sxs-lookup"><span data-stu-id="dfe32-105">Members</span></span>  
  
|<span data-ttu-id="dfe32-106">값</span><span class="sxs-lookup"><span data-stu-id="dfe32-106">Value</span></span>|<span data-ttu-id="dfe32-107">설명</span><span class="sxs-lookup"><span data-stu-id="dfe32-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="dfe32-108">스레드 종료를 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="dfe32-109">스레드 일시 중단을 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="dfe32-110">스레드는 백그라운드에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="dfe32-111">스레드 실행을 시작 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="dfe32-112">스레드가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="dfe32-113">스레드가 다른 스레드가 작업을 완료 되기를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="dfe32-114">스레드가 일시 중단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="dfe32-115">안전 하지 않은 지점에서 스레드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="dfe32-116">즉, 스레드는 실행 지점에서 가비지 수집을 차단할 수 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="dfe32-117">디버그 안전 하지 않은 지점에서 이벤트를 디스패치할 수 있습니다 하지만 안전 하지 않은 지점에서 스레드를 일시 중단 가능성이 하면 교착 상태가 스레드가 재개 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="dfe32-118">안전 하 고 안전 하지 않은 지점 시간 (JIT) 및 가비지 수집 구현에서 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="dfe32-119">스레드가는 스레드 풀의 경우</span><span class="sxs-lookup"><span data-stu-id="dfe32-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfe32-120">설명</span><span class="sxs-lookup"><span data-stu-id="dfe32-120">Remarks</span></span>  
 <span data-ttu-id="dfe32-121">스레드의 사용자 상태는 상태 스레드가 디버거 검사 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="dfe32-122">스레드가는 사용자 상태의 조합에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="dfe32-123">사용 된 [icordebugthread:: Getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) 스레드의 사용자 상태를 검색 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe32-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe32-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfe32-124">Requirements</span></span>  
 <span data-ttu-id="dfe32-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfe32-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe32-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfe32-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfe32-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfe32-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfe32-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe32-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe32-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfe32-129">See also</span></span>

- [<span data-ttu-id="dfe32-130">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="dfe32-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
