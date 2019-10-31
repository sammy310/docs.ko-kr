---
title: EPolicyAction 열거형
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138225"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="2203a-102">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="2203a-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="2203a-103">[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 및 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)에서 설명 하는 오류에 설명 된 작업에 대해 호스트가 설정할 수 있는 정책 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2203a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2203a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="2203a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2203a-105">Members</span></span>  
  
|<span data-ttu-id="2203a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2203a-106">Member</span></span>|<span data-ttu-id="2203a-107">설명</span><span class="sxs-lookup"><span data-stu-id="2203a-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="2203a-108">CLR (공용 언어 런타임)이 스레드를 정상적으로 중단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="2203a-109">정상적인 중단에는 모든 `finally` 블록을 실행 하려는 시도, 스레드 중단과 관련 된 `catch` 블록 및 종료자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="2203a-110">CLR이 비활성화 상태를 시작 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="2203a-111">영향을 받는 프로세스에서 더 이상 관리 코드를 실행할 수 없으며, 스레드가 CLR에 시작 되지 않도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="2203a-112">CLR에서 종료자 실행, 정리 및 로깅 작업 수행을 포함 하 여 프로세스의 정상적인 종료를 시도 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="2203a-113">종료자를 실행 하거나 정리 및 로깅 작업을 수행 하지 않고 CLR에서 즉시 프로세스를 종료 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="2203a-114">그러나 알림이 디버거로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="2203a-115">아무 동작도 수행 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="2203a-116">CLR에서 잘못 된 스레드 중단을 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="2203a-117"><xref:System.EnterpriseServices.MustRunInClientContextAttribute> 표시 된 `catch` 및 `finally` 블록만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="2203a-118">CLR에서 종료자 또는 로깅 작업을 실행 하지 않고 프로세스를 종료 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="2203a-119">CLR이 <xref:System.AppDomain>의 강제 언로드를 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="2203a-120"><xref:System.EnterpriseServices.MustRunInClientContextAttribute> 표시 된 종료자만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="2203a-121">마찬가지로 해당 스택에서이 <xref:System.AppDomain> 있는 모든 스레드는 `ThreadAbortException`를 받으며 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 표시 된 `catch` 및 `finally` 블록만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="2203a-122">조건에 적합 한 예외 (예: 메모리 부족, 버퍼 오버플로 등)를 throw 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="2203a-123"><xref:System.AppDomain>를 언로드하기 위해 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="2203a-124">CLR에서 종료자를 실행 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2203a-125">주의</span><span class="sxs-lookup"><span data-stu-id="2203a-125">Remarks</span></span>  
 <span data-ttu-id="2203a-126">호스트는 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) 인터페이스의 메서드를 호출 하 여 정책 작업을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2203a-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="2203a-127">강제 및 정상적인 중단에 대 한 자세한 내용은 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 열거형을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2203a-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2203a-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2203a-128">Requirements</span></span>  
 <span data-ttu-id="2203a-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2203a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2203a-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2203a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2203a-131">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2203a-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2203a-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2203a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2203a-133">참조</span><span class="sxs-lookup"><span data-stu-id="2203a-133">See also</span></span>

- [<span data-ttu-id="2203a-134">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="2203a-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="2203a-135">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2203a-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="2203a-136">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2203a-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="2203a-137">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2203a-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
