---
title: ICLRPolicyManager::SetDefaultAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d339fbadc3260d20fac848ad7f1a9031c3443aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154663"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="755f5-102">ICLRPolicyManager::SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="755f5-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="755f5-103">CLR (공용 언어 런타임)은 지정 된 작업이 수행 될 때 수행 해야 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="755f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="755f5-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="755f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="755f5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="755f5-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 는 CLR에 대 한 동작을 사용자 지정할 수는 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="755f5-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값을 나타내는 경우 CLR 정책 작업을 수행 해야 `operation` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="755f5-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="755f5-108">Return Value</span></span>  
  
|<span data-ttu-id="755f5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="755f5-109">HRESULT</span></span>|<span data-ttu-id="755f5-110">설명</span><span class="sxs-lookup"><span data-stu-id="755f5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="755f5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="755f5-111">S_OK</span></span>|`SetDefaultAction` <span data-ttu-id="755f5-112">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-112">returned successfully.</span></span>|  
|<span data-ttu-id="755f5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="755f5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="755f5-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="755f5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="755f5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="755f5-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-116">The call timed out.</span></span>|  
|<span data-ttu-id="755f5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="755f5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="755f5-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="755f5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="755f5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="755f5-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="755f5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="755f5-121">E_FAIL</span></span>|<span data-ttu-id="755f5-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="755f5-123">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="755f5-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="755f5-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="755f5-125">E_INVALIDARG</span></span>|<span data-ttu-id="755f5-126">잘못 된 `action` 에 대해 지정 된 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `operation`합니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="755f5-127">설명</span><span class="sxs-lookup"><span data-stu-id="755f5-127">Remarks</span></span>  
 <span data-ttu-id="755f5-128">CLR 작업에 대 한 기본 동작으로 일부 정책은 동작 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> `SetDefaultAction` <span data-ttu-id="755f5-129">에스컬레이션 동작에만 일반적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-129">can typically be used only to escalate behavior.</span></span> <span data-ttu-id="755f5-130">예를 들어 호스트 스레드 중단으로 강제 변환할 수 있는지 지정할 수 있습니다 스레드 중단 하지만 반대를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="755f5-131">아래 표에 유효한 `action` 각각의 가능한 값 `operation` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="755f5-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="755f5-132">에 대 한 값</span><span class="sxs-lookup"><span data-stu-id="755f5-132">Value for</span></span> `operation`|<span data-ttu-id="755f5-133">에 대 한 유효한 값</span><span class="sxs-lookup"><span data-stu-id="755f5-133">Valid values for</span></span> `action`|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="755f5-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="755f5-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="755f5-135">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="755f5-135">-   eAbortThread</span></span><br /><span data-ttu-id="755f5-136">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="755f5-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="755f5-137">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-138">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-139">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-139">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-140">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-141">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-142">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="755f5-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="755f5-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="755f5-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="755f5-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="755f5-145">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="755f5-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="755f5-146">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-147">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-148">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-148">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-149">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-150">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-151">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="755f5-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="755f5-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="755f5-153">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-154">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-155">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-155">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-156">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-157">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-158">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="755f5-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="755f5-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="755f5-160">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-161">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-161">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-162">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-163">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-164">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="755f5-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="755f5-165">OPR_ProcessExit</span></span>|<span data-ttu-id="755f5-166">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-166">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-167">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-168">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-169">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="755f5-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="755f5-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="755f5-171">-   eNoAction</span><span class="sxs-lookup"><span data-stu-id="755f5-171">-   eNoAction</span></span><br /><span data-ttu-id="755f5-172">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="755f5-172">-   eAbortThread</span></span><br /><span data-ttu-id="755f5-173">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="755f5-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="755f5-174">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-175">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="755f5-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="755f5-176">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-176">-   eExitProcess</span></span><br /><span data-ttu-id="755f5-177">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="755f5-178">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="755f5-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="755f5-179">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="755f5-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="755f5-180">요구 사항</span><span class="sxs-lookup"><span data-stu-id="755f5-180">Requirements</span></span>  
 <span data-ttu-id="755f5-181">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="755f5-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="755f5-182">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="755f5-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="755f5-183">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="755f5-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="755f5-184">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="755f5-184">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="755f5-185">참고자료</span><span class="sxs-lookup"><span data-stu-id="755f5-185">See also</span></span>

- [<span data-ttu-id="755f5-186">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="755f5-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="755f5-187">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="755f5-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="755f5-188">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="755f5-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
