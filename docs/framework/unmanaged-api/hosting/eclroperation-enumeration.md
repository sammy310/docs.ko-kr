---
description: '자세히 알아보기: EClrOperation 열거형'
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
ms.openlocfilehash: 9f75762a400955b5f36fb2a337f283e36a32658c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785564"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="e506e-103">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="e506e-103">EClrOperation Enumeration</span></span>

<span data-ttu-id="e506e-104">호스트에서 정책 작업을 적용할 수 있는 작업 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-104">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e506e-105">구문</span><span class="sxs-lookup"><span data-stu-id="e506e-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e506e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e506e-106">Members</span></span>  
  
|<span data-ttu-id="e506e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e506e-107">Member</span></span>|<span data-ttu-id="e506e-108">설명</span><span class="sxs-lookup"><span data-stu-id="e506e-108">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="e506e-109">호스트는가 <xref:System.AppDomain> 정상이 아닌 (강제) 방식으로 언로드될 때 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="e506e-110">호스트는가 언로드될 때 수행할 정책 작업을 지정할 수 있습니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e506e-110">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="e506e-111">호스트는 종료 자가 실행 될 때 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-111">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="e506e-112">호스트는 프로세스가 종료 될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-112">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="e506e-113">호스트는 스레드가 중단 될 때 수행할 정책 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-113">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="e506e-114">호스트는 중요 한 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-114">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="e506e-115">호스트는 중요 하지 않은 코드 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 정책 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-115">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e506e-116">설명</span><span class="sxs-lookup"><span data-stu-id="e506e-116">Remarks</span></span>  

 <span data-ttu-id="e506e-117">CLR (공용 언어 런타임) 안정성 인프라는 중요 한 코드 영역에서 발생 하는 중단 및 리소스 할당 오류와 중요 하지 않은 코드 영역에서 발생 하는 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-117">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="e506e-118">이러한 구분은 호스트에서 코드에 오류가 발생 하는 위치에 따라 다른 정책을 설정할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-118">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="e506e-119">*중요 한 코드 영역은* CLR에서 작업 중단 또는 리소스에 대 한 요청 완료 실패로 인해 현재 작업에만 영향을 줄 수 있음을 보장할 수 없는 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-119">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="e506e-120">예를 들어 태스크가 잠금을 보유 하 고 있고 메모리 할당 요청을 수행할 때 실패를 나타내는 HRESULT를 수신 하는 경우에는의 안정성을 보장 하기 위해 해당 작업을 중단 하는 것 만으로는 충분 하지 않습니다 .에는 <xref:System.AppDomain> <xref:System.AppDomain> 동일한 잠금을 기다리는 다른 태스크가 포함 될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-120">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="e506e-121">현재 작업을 중단 하면 다른 작업의 응답이 중지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-121">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="e506e-122">이러한 경우, 호스트는 잠재적 불안정성이 아닌 전체를 언로드하는 기능이 필요 합니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e506e-122">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="e506e-123">반면, *중요 하지 않은 코드 영역은* CLR에서 중단 또는 실패가 오류가 발생 한 작업에만 영향을 줄 수 있도록 보장 하는 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-123">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="e506e-124">또한 CLR은 정상 및 정상 (강제) 중단을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-124">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="e506e-125">일반적으로 정상 또는 정상 abort는 작업을 중단 하기 전에 예외 처리 루틴 및 종료자를 실행 하는 데 모든 노력을 하지만, 잘못 된 abort는 이러한 보장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e506e-125">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e506e-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e506e-126">Requirements</span></span>  

 <span data-ttu-id="e506e-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e506e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e506e-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e506e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e506e-129">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e506e-129">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e506e-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e506e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e506e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e506e-131">See also</span></span>

- [<span data-ttu-id="e506e-132">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="e506e-132">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="e506e-133">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="e506e-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="e506e-134">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e506e-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="e506e-135">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e506e-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="e506e-136">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="e506e-136">Hosting Enumerations</span></span>](hosting-enumerations.md)
