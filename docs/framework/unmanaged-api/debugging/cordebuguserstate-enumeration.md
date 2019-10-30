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
ms.openlocfilehash: d0394d511197c8d0aaa366ce7b791216a3d226bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120198"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="a9011-102">CorDebugUserState 열거형</span><span class="sxs-lookup"><span data-stu-id="a9011-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="a9011-103">스레드의 사용자 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9011-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9011-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="a9011-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a9011-105">Members</span></span>  
  
|<span data-ttu-id="a9011-106">값</span><span class="sxs-lookup"><span data-stu-id="a9011-106">Value</span></span>|<span data-ttu-id="a9011-107">설명</span><span class="sxs-lookup"><span data-stu-id="a9011-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="a9011-108">스레드의 종료를 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="a9011-109">스레드의 일시 중단이 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="a9011-110">스레드가 백그라운드에서 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="a9011-111">스레드가 실행을 시작 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="a9011-112">스레드가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="a9011-113">스레드가 다른 스레드가 작업을 완료할 때까지 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="a9011-114">스레드가 일시 중단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="a9011-115">스레드가 안전 하지 않은 지점에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="a9011-116">즉, 스레드는 가비지 수집을 차단할 수 있는 실행 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="a9011-117">안전 하지 않은 지점에서 디버그 이벤트를 디스패치할 수도 있지만 안전 하지 않은 지점에서 스레드를 일시 중단 하면 스레드가 다시 시작 될 때까지 교착 상태가 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="a9011-118">안전 하 고 안전 하지 않은 지점은 JIT (just-in-time) 및 가비지 수집 구현에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="a9011-119">스레드가 스레드 풀에서 가져온 경우</span><span class="sxs-lookup"><span data-stu-id="a9011-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9011-120">주의</span><span class="sxs-lookup"><span data-stu-id="a9011-120">Remarks</span></span>  
 <span data-ttu-id="a9011-121">스레드의 사용자 상태는 디버거에서 해당 스레드를 검사할 때 스레드에 포함 된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="a9011-122">스레드에는 사용자 상태의 조합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="a9011-123">[ICorDebugThread:: GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) 메서드를 사용 하 여 스레드의 사용자 상태를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9011-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9011-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9011-124">Requirements</span></span>  
 <span data-ttu-id="a9011-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9011-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9011-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9011-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9011-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9011-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9011-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9011-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9011-129">참조</span><span class="sxs-lookup"><span data-stu-id="a9011-129">See also</span></span>

- [<span data-ttu-id="a9011-130">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="a9011-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
