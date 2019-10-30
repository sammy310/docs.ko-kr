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
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131156"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="e1396-102">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="e1396-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="e1396-103">호스트에서 정책 작업을 적용할 수 있는 작업 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1396-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1396-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e1396-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e1396-105">Members</span></span>  
  
|<span data-ttu-id="e1396-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1396-106">Member</span></span>|<span data-ttu-id="e1396-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1396-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="e1396-108">호스트는 <xref:System.AppDomain>가 정상적이 지 않은 방식으로 언로드될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="e1396-109">호스트는 <xref:System.AppDomain> 언로드될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="e1396-110">호스트는 종료 자가 실행 될 때 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="e1396-111">호스트는 프로세스가 종료 될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="e1396-112">호스트는 스레드가 중단 될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="e1396-113">호스트는 중요 한 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="e1396-114">호스트는 중요 하지 않은 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1396-115">주의</span><span class="sxs-lookup"><span data-stu-id="e1396-115">Remarks</span></span>  
 <span data-ttu-id="e1396-116">CLR (공용 언어 런타임) 안정성 인프라는 중요 한 코드 영역에서 발생 하는 중단 및 리소스 할당 오류와 중요 하지 않은 코드 영역에서 발생 하는 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="e1396-117">이러한 구분은 호스트에서 코드에 오류가 발생 하는 위치에 따라 다른 정책을 설정할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="e1396-118">*중요 한 코드 영역은* CLR에서 작업 중단 또는 리소스에 대 한 요청 완료 실패로 인해 현재 작업에만 영향을 줄 수 있음을 보장할 수 없는 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="e1396-119">예를 들어 태스크가 잠금을 보유 하 고 메모리 할당 요청을 수행할 때 실패를 나타내는 HRESULT를 수신 하는 경우, <xref:System.AppDomain> 다른 작업을 포함할 수 있기 때문에 해당 작업을 중단 하 여 <xref:System.AppDomain>의 안정성을 보장 하는 것 만으로는 충분 하지 않습니다. 동일한 잠금이 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="e1396-120">현재 작업을 중단 하면 다른 작업의 응답이 중지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="e1396-121">이러한 경우 호스트는 잠재적으로 불안정 한 위험 보다는 전체 <xref:System.AppDomain>를 언로드할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="e1396-122">반면, *중요 하지 않은 코드 영역은*CLR에서 중단 또는 실패가 오류가 발생 한 작업에만 영향을 줄 수 있도록 보장 하는 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="e1396-123">또한 CLR은 정상 및 정상 (강제) 중단을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="e1396-124">일반적으로 정상 또는 정상 abort는 작업을 중단 하기 전에 예외 처리 루틴 및 종료자를 실행 하는 데 모든 노력을 하지만, 잘못 된 abort는 이러한 보장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1396-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1396-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1396-125">Requirements</span></span>  
 <span data-ttu-id="e1396-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1396-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1396-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1396-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1396-128">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1396-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1396-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1396-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1396-130">참조</span><span class="sxs-lookup"><span data-stu-id="e1396-130">See also</span></span>

- [<span data-ttu-id="e1396-131">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="e1396-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="e1396-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="e1396-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="e1396-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1396-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e1396-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1396-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="e1396-135">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="e1396-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
