---
description: '자세히 알아보기: CorDebugThreadState 열거형'
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
ms.openlocfilehash: 0cf83ee31547e49ccc7d09e0ab4ee85548688b36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661808"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="701a4-103">CorDebugThreadState 열거형</span><span class="sxs-lookup"><span data-stu-id="701a4-103">CorDebugThreadState Enumeration</span></span>

<span data-ttu-id="701a4-104">디버깅을 위한 스레드 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-104">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701a4-105">구문</span><span class="sxs-lookup"><span data-stu-id="701a4-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="701a4-106">구성원</span><span class="sxs-lookup"><span data-stu-id="701a4-106">Members</span></span>  
  
|<span data-ttu-id="701a4-107">멤버</span><span class="sxs-lookup"><span data-stu-id="701a4-107">Member</span></span>|<span data-ttu-id="701a4-108">설명</span><span class="sxs-lookup"><span data-stu-id="701a4-108">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="701a4-109">디버그 이벤트가 발생 하지 않는 한 스레드는 자유롭게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-109">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="701a4-110">스레드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-110">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="701a4-111">설명</span><span class="sxs-lookup"><span data-stu-id="701a4-111">Remarks</span></span>  

 <span data-ttu-id="701a4-112">디버거는 열거형을 사용 하 여 `CorDebugThreadState` 스레드의 실행을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-112">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="701a4-113">[ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) 또는 [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) 메서드를 사용 하 여 스레드 상태를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-113">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="701a4-114">[호스팅 API](../hosting/index.md) 에 제공 된 콜백에서 메시지 펌프를 사용할 수 있으므로 중단 된 상태가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="701a4-114">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701a4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="701a4-115">Requirements</span></span>  

 <span data-ttu-id="701a4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="701a4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="701a4-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="701a4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="701a4-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="701a4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="701a4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="701a4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701a4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="701a4-120">See also</span></span>

- [<span data-ttu-id="701a4-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="701a4-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
