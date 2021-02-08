---
description: '자세히 알아보기: EMemoryCriticalLevel 열거형'
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
ms.openlocfilehash: 88965a29164de1ec7b01c2fcc8f51415127e69fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785434"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="bfe6f-103">EMemoryCriticalLevel 열거형</span><span class="sxs-lookup"><span data-stu-id="bfe6f-103">EMemoryCriticalLevel Enumeration</span></span>

<span data-ttu-id="bfe6f-104">특정 메모리 할당이 요청 되었지만 충족 될 수 없는 경우 실패의 영향을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-104">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe6f-105">구문</span><span class="sxs-lookup"><span data-stu-id="bfe6f-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="bfe6f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="bfe6f-106">Members</span></span>  
  
|<span data-ttu-id="bfe6f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="bfe6f-107">Member</span></span>|<span data-ttu-id="bfe6f-108">설명</span><span class="sxs-lookup"><span data-stu-id="bfe6f-108">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="bfe6f-109">할당을 요청한 도메인에서 관리 코드를 실행 하는 데 할당이 중요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-109">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="bfe6f-110">메모리를 할당할 수 없는 경우에는 CLR에서 도메인을 계속 사용할 수 있음을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-110">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="bfe6f-111">호스트는 할당을 충족 시킬 수 없는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-111">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="bfe6f-112">CLR에 `AppDomain` 자동으로 중단 하거나 [ICLRPolicyManager](iclrpolicymanager-interface.md)에서 메서드를 호출 하 여 계속 실행 되도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-112">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="bfe6f-113">프로세스에서 관리 코드를 실행 하는 데 할당이 중요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-113">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="bfe6f-114">이 값은 시작 하는 동안 및 종료자를 실행할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-114">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="bfe6f-115">메모리를 할당할 수 없는 경우 CLR은 프로세스에서 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-115">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="bfe6f-116">할당이 실패 하는 경우 CLR은 효과적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-116">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="bfe6f-117">CLR에 대 한 모든 후속 호출은 HOST_E_CLRNOTAVAILABLE와 함께 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-117">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="bfe6f-118">할당을 요청한 태스크를 실행 하는 데 할당이 중요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-118">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="bfe6f-119">메모리를 할당할 수 없는 경우 CLR에서 작업을 실행할 수 있음을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-119">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="bfe6f-120">오류가 발생 하는 경우 CLR은 <xref:System.Threading.ThreadAbortException> 물리적 작업 시스템 스레드에서을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-120">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfe6f-121">설명</span><span class="sxs-lookup"><span data-stu-id="bfe6f-121">Remarks</span></span>  

 <span data-ttu-id="bfe6f-122">[IHostMemoryManager](ihostmemorymanager-interface.md) 및 [IHostMAlloc](ihostmalloc-interface.md) 인터페이스에 정의 된 메모리 할당 메서드는이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-122">The memory allocation methods defined in the [IHostMemoryManager](ihostmemorymanager-interface.md) and [IHostMAlloc](ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="bfe6f-123">오류의 심각도에 따라 호스트는 할당 요청을 즉시 장애 조치 (failover) 하거나 만족할 때까지 기다릴지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-123">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe6f-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfe6f-124">Requirements</span></span>  

 <span data-ttu-id="bfe6f-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfe6f-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe6f-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bfe6f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfe6f-127">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfe6f-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfe6f-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe6f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe6f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfe6f-129">See also</span></span>

- [<span data-ttu-id="bfe6f-130">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfe6f-130">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="bfe6f-131">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="bfe6f-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
