---
description: '자세히 알아보기: ETaskType 열거형'
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
ms.openlocfilehash: 7cb241765b2ff3b4a3402221c6b3e2b7ff6305c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785408"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="0608f-103">ETaskType 열거형</span><span class="sxs-lookup"><span data-stu-id="0608f-103">ETaskType Enumeration</span></span>

<span data-ttu-id="0608f-104">[ICLRTask](iclrtask-interface.md) 또는 [IHostTask](ihosttask-interface.md) 인터페이스로 표시 되는 작업의 유형을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-104">Contains values that indicate the type of task that is represented by either an [ICLRTask](iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0608f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0608f-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0608f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="0608f-106">Members</span></span>  
  
|<span data-ttu-id="0608f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="0608f-107">Member</span></span>|<span data-ttu-id="0608f-108">설명</span><span class="sxs-lookup"><span data-stu-id="0608f-108">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="0608f-109">인터페이스는 응용 프로그램 도메인 언로드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-109">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="0608f-110">인터페이스는 디버거 도우미 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-110">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="0608f-111">인터페이스는 종료자 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-111">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="0608f-112">인터페이스는 가비지 수집 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-112">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="0608f-113">인터페이스는 게이트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-113">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="0608f-114">인터페이스는 i/o 스레드 작업 또는 완료 포트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-114">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="0608f-115">인터페이스는 타이머 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-115">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="0608f-116">인터페이스는 대기 스레드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-116">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="0608f-117">인터페이스는 작업자 스레드 태스크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-117">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="0608f-118">작업을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-118">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="0608f-119">인터페이스는 사용자 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0608f-119">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0608f-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0608f-120">Requirements</span></span>  

 <span data-ttu-id="0608f-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0608f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0608f-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0608f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0608f-123">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0608f-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0608f-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0608f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0608f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0608f-125">See also</span></span>

- [<span data-ttu-id="0608f-126">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="0608f-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
