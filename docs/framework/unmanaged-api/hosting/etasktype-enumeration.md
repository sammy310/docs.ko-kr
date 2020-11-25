---
title: ETaskType 열거형
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: 332488fee4c982fdbaecceeaa2a6a3876f1602a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733700"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="d262b-102">ETaskType 열거형</span><span class="sxs-lookup"><span data-stu-id="d262b-102">ETaskType Enumeration</span></span>

<span data-ttu-id="d262b-103">[ICLRTask](iclrtask-interface.md) 또는 [IHostTask](ihosttask-interface.md) 인터페이스로 표시 되는 작업의 유형을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d262b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d262b-104">Syntax</span></span>  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="d262b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d262b-105">Members</span></span>  
  
|<span data-ttu-id="d262b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d262b-106">Member</span></span>|<span data-ttu-id="d262b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d262b-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="d262b-108">인터페이스는 응용 프로그램 도메인 언로드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="d262b-109">인터페이스는 디버거 도우미 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="d262b-110">인터페이스는 종료자 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="d262b-111">인터페이스는 가비지 수집 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="d262b-112">인터페이스는 게이트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="d262b-113">인터페이스는 i/o 스레드 작업 또는 완료 포트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="d262b-114">인터페이스는 타이머 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="d262b-115">인터페이스는 대기 스레드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="d262b-116">인터페이스는 작업자 스레드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="d262b-117">작업을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="d262b-118">인터페이스는 사용자 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d262b-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d262b-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d262b-119">Requirements</span></span>  

 <span data-ttu-id="d262b-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d262b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d262b-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d262b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d262b-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d262b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d262b-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d262b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d262b-124">참조</span><span class="sxs-lookup"><span data-stu-id="d262b-124">See also</span></span>

- [<span data-ttu-id="d262b-125">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="d262b-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
