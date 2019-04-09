---
title: EMemoryCriticalLevel 열거형
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122293"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="a69e1-102">EMemoryCriticalLevel 열거형</span><span class="sxs-lookup"><span data-stu-id="a69e1-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="a69e1-103">특정 메모리 할당이 요청 되었으나 처리할 수 없는 경우 오류의 영향을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="a69e1-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="a69e1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a69e1-105">Members</span></span>  
  
|<span data-ttu-id="a69e1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a69e1-106">Member</span></span>|<span data-ttu-id="a69e1-107">설명</span><span class="sxs-lookup"><span data-stu-id="a69e1-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="a69e1-108">할당이 할당 요청한 도메인에서 관리 되는 코드를 실행 하는 것에 대 한 중요 한 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="a69e1-109">메모리를 할당할 수 없는 경우 CLR 도메인에 여전히 사용할 수 있는지를 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="a69e1-110">호스트에 할당할 수 없는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="a69e1-111">중단을 CLR에 지시할 수 있습니다 합니다 `AppDomain` 자동으로 계속에서 메서드를 호출 하 여 실행 되도록 허용 하거나 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="a69e1-112">할당 프로세스에서 관리 되는 코드의 실행에 중요 한 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="a69e1-113">이 값은 종료자를 실행 하는 경우 시작 하는 동안 및 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="a69e1-114">메모리를 할당할 수 없으면 CLR 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="a69e1-115">할당이 실패 하면 CLR은 효과적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="a69e1-116">CLR에 대 한 모든 후속 호출 HOST_E_CLRNOTAVAILABLE를 사용 하 여 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="a69e1-117">할당이 할당 요청한 작업을 실행 하는 중요 한 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="a69e1-118">메모리를 할당할 수 없으면 CLR 태스크가 실행 될 수 있도록 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="a69e1-119">CLR 장애가 발생 한 <xref:System.Threading.ThreadAbortException> 물리적 연산 시스템 스레드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a69e1-120">설명</span><span class="sxs-lookup"><span data-stu-id="a69e1-120">Remarks</span></span>  
 <span data-ttu-id="a69e1-121">에 정의 된 메모리 할당 메서드를 [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) 하 고 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인터페이스는이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="a69e1-122">오류의 심각도 따라 호스트 여부를 결정할 수 할당 요청이 즉시 실패 또는 처리할 수 있습니다 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a69e1-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a69e1-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a69e1-123">Requirements</span></span>  
 <span data-ttu-id="a69e1-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a69e1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a69e1-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a69e1-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a69e1-126">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a69e1-126">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a69e1-127">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a69e1-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a69e1-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="a69e1-128">See also</span></span>

- [<span data-ttu-id="a69e1-129">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a69e1-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="a69e1-130">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="a69e1-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
