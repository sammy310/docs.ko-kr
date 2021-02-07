---
description: '다음에 대 한 자세한 정보: CorDebugUserState 열거형'
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
ms.openlocfilehash: c556e7943751fb8e159e3e0d0b9a71baf1f6b5b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661742"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="6811f-103">CorDebugUserState 열거형</span><span class="sxs-lookup"><span data-stu-id="6811f-103">CorDebugUserState Enumeration</span></span>

<span data-ttu-id="6811f-104">스레드의 사용자 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-104">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6811f-105">구문</span><span class="sxs-lookup"><span data-stu-id="6811f-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6811f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="6811f-106">Members</span></span>  
  
|<span data-ttu-id="6811f-107">값</span><span class="sxs-lookup"><span data-stu-id="6811f-107">Value</span></span>|<span data-ttu-id="6811f-108">설명</span><span class="sxs-lookup"><span data-stu-id="6811f-108">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="6811f-109">스레드의 종료를 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-109">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="6811f-110">스레드의 일시 중단이 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-110">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="6811f-111">스레드가 백그라운드에서 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-111">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="6811f-112">스레드가 실행을 시작 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-112">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="6811f-113">스레드가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-113">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="6811f-114">스레드가 다른 스레드가 작업을 완료할 때까지 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-114">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="6811f-115">스레드가 일시 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-115">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="6811f-116">스레드가 안전 하지 않은 지점에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-116">The thread is at an unsafe point.</span></span> <span data-ttu-id="6811f-117">즉, 스레드는 가비지 수집을 차단할 수 있는 실행 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-117">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="6811f-118">안전 하지 않은 지점에서 디버그 이벤트를 디스패치할 수도 있지만 안전 하지 않은 지점에서 스레드를 일시 중단 하면 스레드가 다시 시작 될 때까지 교착 상태가 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-118">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="6811f-119">안전 하 고 안전 하지 않은 지점은 JIT (just-in-time) 및 가비지 수집 구현에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-119">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="6811f-120">스레드가 스레드 풀에서 가져온 경우</span><span class="sxs-lookup"><span data-stu-id="6811f-120">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6811f-121">설명</span><span class="sxs-lookup"><span data-stu-id="6811f-121">Remarks</span></span>  

 <span data-ttu-id="6811f-122">스레드의 사용자 상태는 디버거에서 해당 스레드를 검사할 때 스레드에 포함 된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-122">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="6811f-123">스레드에는 사용자 상태의 조합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-123">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="6811f-124">[ICorDebugThread:: GetUserState](icordebugthread-getuserstate-method.md) 메서드를 사용 하 여 스레드의 사용자 상태를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6811f-124">Use the [ICorDebugThread::GetUserState](icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6811f-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6811f-125">Requirements</span></span>  

 <span data-ttu-id="6811f-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6811f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6811f-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6811f-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6811f-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6811f-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6811f-129">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6811f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6811f-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6811f-130">See also</span></span>

- [<span data-ttu-id="6811f-131">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6811f-131">Debugging Enumerations</span></span>](debugging-enumerations.md)
