---
title: EClrOperation 열거형
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b000ed3d75ddb6a7882cb8f03ff2cec64fb9fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767882"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="ca5d7-102">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="ca5d7-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="ca5d7-103">호스트 정책 작업을 적용할 수 있는 작업 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca5d7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="ca5d7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ca5d7-105">Members</span></span>  
  
|<span data-ttu-id="ca5d7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ca5d7-106">Member</span></span>|<span data-ttu-id="ca5d7-107">Description</span><span class="sxs-lookup"><span data-stu-id="ca5d7-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="ca5d7-108">호스트 정책 작업을 수행할 때 지정할 수는 <xref:System.AppDomain> 정상적이 지 않은 (강제) 방식으로 언로드되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="ca5d7-109">호스트 정책 작업을 수행할 때 지정할 수는 <xref:System.AppDomain> 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="ca5d7-110">호스트 종료 자가 실행 시 수행 될 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="ca5d7-111">호스트는 프로세스가 종료 시 수행 될 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="ca5d7-112">호스트 정책 스레드가 중단 될 때 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="ca5d7-113">호스트 정책 코드의 중요 영역에서 강제 스레드 중단이 발생할 경우 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="ca5d7-114">호스트 코드는 중요 하지 않은 영역에서 강제 스레드 중단이 발생할 경우 되려면 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca5d7-115">설명</span><span class="sxs-lookup"><span data-stu-id="ca5d7-115">Remarks</span></span>  
 <span data-ttu-id="ca5d7-116">공용 언어 런타임 (CLR) 안정성 인프라 중단 되 고 리소스 간에 코드 및 코드의 중요 하지 않은 지역에서 발생 하는 중요 한 영역에서 발생 하는 할당 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="ca5d7-117">이 차이 호스트 코드에서 오류가 발생 하는 위치에 따라 다양 한 정책을 설정할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="ca5d7-118">A *중요 한 코드 영역* CLR에서 해당 작업을 중단 또는 리소스에는 현재 태스크에만 영향이 대 한 요청을 완료 하지 못함을 줄 수 없는 공간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="ca5d7-119">예를 들어 작업 잠금을 보유 하는 메모리 할당 요청 시 오류를 나타내는 hresult가 하는 경우 충분 하지 않기 위해 해당 작업의 안정성을 중단 합니다 <xref:System.AppDomain>이므로 <xref:System.AppDomain> 다른 포함 될 수 있습니다 동일한 잠금을 대기 하는 태스크입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="ca5d7-120">중단할 현재 작업 응답을 중지 하도록 다른 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="ca5d7-121">이런 경우 호스트 해야 전체를 언로드할 수 <xref:System.AppDomain> 위험 잠재적 불안정 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="ca5d7-122">A *중요 하지 않은 코드 영역의*, 다른 한편으로 여기서 CLR 중단 또는 실패는 오류가 발생 하는 작업에만 영향이 보장할 수 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="ca5d7-123">또한 CLR 정상적이 고 정상 되지 않은 (강제) 중단을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="ca5d7-124">일반적으로 정상적으로 중단 하기 위해 모든 노력 강제 중단은 이러한 보증도 하지 않습니다 하는 동안 작업을 중단 하기 전에 예외 처리 루틴 및 종료자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5d7-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca5d7-125">Requirements</span></span>  
 <span data-ttu-id="ca5d7-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca5d7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5d7-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca5d7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca5d7-128">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca5d7-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca5d7-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5d7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5d7-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca5d7-130">See also</span></span>

- [<span data-ttu-id="ca5d7-131">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="ca5d7-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="ca5d7-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="ca5d7-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ca5d7-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca5d7-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="ca5d7-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca5d7-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="ca5d7-135">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="ca5d7-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
