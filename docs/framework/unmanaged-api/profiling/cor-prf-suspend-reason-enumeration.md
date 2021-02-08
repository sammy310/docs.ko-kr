---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_SUSPEND_REASON'
title: COR_PRF_SUSPEND_REASON 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: 9e8b3dc98aa6b1a989088f5f4d0efb74d488d927
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789010"
---
# <a name="cor_prf_suspend_reason-enumeration"></a><span data-ttu-id="73e3d-103">COR_PRF_SUSPEND_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="73e3d-103">COR_PRF_SUSPEND_REASON Enumeration</span></span>

<span data-ttu-id="73e3d-104">런타임이 일시 중단 된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-104">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e3d-105">구문</span><span class="sxs-lookup"><span data-stu-id="73e3d-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="73e3d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="73e3d-106">Members</span></span>  
  
|<span data-ttu-id="73e3d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="73e3d-107">Member</span></span>|<span data-ttu-id="73e3d-108">설명</span><span class="sxs-lookup"><span data-stu-id="73e3d-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="73e3d-109">지정 되지 않은 이유로 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-109">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="73e3d-110">런타임은 가비지 수집 요청을 처리 하기 위해 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-110">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="73e3d-111">가비지 컬렉션 관련 콜백은 [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 및 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백 사이에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-111">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="73e3d-112">를 종료할 수 있도록 런타임이 일시 중단 됩니다 `AppDomain` .</span><span class="sxs-lookup"><span data-stu-id="73e3d-112">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="73e3d-113">런타임이 일시 중단 된 동안 런타임에서는 종료 되는 스레드를 확인 하 `AppDomain` 고 다시 시작할 때 abort로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-113">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="73e3d-114">`AppDomain`이 일시 중단 중에는 특정 콜백이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-114">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="73e3d-115">코드 피칭 발생할 수 있도록 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-115">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="73e3d-116">Code 피칭 ensues는 JIT (just-in-time) 컴파일러가 활성화 된 코드 피칭 사용 하는 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-116">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="73e3d-117">코드 피칭 콜백은 및 콜백 사이에서 발생 `ICorProfilerCallback::RuntimeSuspendFinished` `ICorProfilerCallback::RuntimeResumeStarted` 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-117">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="73e3d-118">**참고:**  CLR JIT는 .NET Framework 버전 2.0에서 함수를 피치 하지 않으므로 2.0에서는이 값이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-118">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="73e3d-119">런타임이 종료 될 수 있도록 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-119">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="73e3d-120">작업을 완료 하려면 모든 스레드를 일시 중단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-120">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="73e3d-121">In-process 디버깅에 대해 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-121">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="73e3d-122">가비지 수집을 준비 하기 위해 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-122">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="73e3d-123">JIT 재컴파일에 대해 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-123">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73e3d-124">설명</span><span class="sxs-lookup"><span data-stu-id="73e3d-124">Remarks</span></span>  

 <span data-ttu-id="73e3d-125">비관리 코드에 있는 모든 런타임 스레드는 런타임을 다시 시작할 때까지 계속 실행 되도록 허용 되며, 런타임이 다시 시작 될 때까지 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-125">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="73e3d-126">이는 런타임에 입력 하는 새 스레드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-126">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="73e3d-127">런타임 내의 모든 스레드는 중단 될 수 있는 코드에 있는 경우 즉시 일시 중단 되 고, 인터럽트 가능 코드에 도달 하면 일시 중단을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e3d-127">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e3d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73e3d-128">Requirements</span></span>  

 <span data-ttu-id="73e3d-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73e3d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e3d-130">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73e3d-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73e3d-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73e3d-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73e3d-132">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e3d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e3d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e3d-133">See also</span></span>

- [<span data-ttu-id="73e3d-134">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="73e3d-134">Profiling Enumerations</span></span>](profiling-enumerations.md)
