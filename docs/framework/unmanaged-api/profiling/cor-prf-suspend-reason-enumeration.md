---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21533b5173bcd91d0c944fbde4eafc9817de8315
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220060"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="935de-102">COR_PRF_SUSPEND_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="935de-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="935de-103">런타임이 일시 중단 되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="935de-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935de-104">구문</span><span class="sxs-lookup"><span data-stu-id="935de-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="935de-105">멤버</span><span class="sxs-lookup"><span data-stu-id="935de-105">Members</span></span>  
  
|<span data-ttu-id="935de-106">멤버</span><span class="sxs-lookup"><span data-stu-id="935de-106">Member</span></span>|<span data-ttu-id="935de-107">설명</span><span class="sxs-lookup"><span data-stu-id="935de-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="935de-108">런타임에 알 수 없는 이유로 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="935de-109">런타임은은 가비지 컬렉션 요청 서비스를 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="935de-110">가비지 컬렉션 관련 콜백이 사이 발생 합니다 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 및 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="935de-111">런타임에서 일시 중단 됩니다 있도록는 `AppDomain` 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="935de-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="935de-112">런타임에서 일시 중단 하는 동안를 확인 하는 스레드는에 `AppDomain` 즉 종료 되 고 다시 시작 될 때 중단 되도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="935de-113">가지 없습니다 `AppDomain`-이 일시 중단 하는 동안 특정 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="935de-114">런타임 코드 피칭 발생할 수 있도록 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="935de-115">코드 피칭 근거가-just-in-time (JIT) 컴파일러가 활성화 되 면 코드 피칭 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="935de-116">코드 피칭 콜백 간에 발생 합니다 `ICorProfilerCallback::RuntimeSuspendFinished` 및 `ICorProfilerCallback::RuntimeResumeStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="935de-117">**참고:**  CLR JIT는.NET Framework 버전 2.0의에서 함수 홍보 되므로 2.0에서이 값이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="935de-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="935de-118">종료할 수 있도록 런타임이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="935de-119">모든 스레드가 작업 완료를 일시 중단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="935de-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="935de-120">런타임은 프로세스의 디버깅에 대 한 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="935de-121">런타임은은 가비지 수집을 위해 준비 하려면 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="935de-122">런타임은은 JIT 다시 컴파일을 위해 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="935de-123">설명</span><span class="sxs-lookup"><span data-stu-id="935de-123">Remarks</span></span>  
 <span data-ttu-id="935de-124">비관리 코드에 있는 모든 런타임 스레드는이 시점에서 이러한도 일시 중단 됩니다 런타임을 다시 시작 될 때까지 런타임을 다시 입력 하려고 시도할 때까지 실행을 계속 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="935de-125">이 런타임에 입력 하는 새 스레드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="935de-126">모든 스레드가 런타임 내에서 인터럽트 가능한 코드에 있는 경우 즉시 일시 중단 또는 인터럽트 가능한 코드에 도달할 때 일시 중지 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="935de-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935de-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="935de-127">Requirements</span></span>  
 <span data-ttu-id="935de-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="935de-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935de-129">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="935de-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="935de-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="935de-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="935de-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="935de-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="935de-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="935de-132">See also</span></span>

- [<span data-ttu-id="935de-133">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="935de-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
