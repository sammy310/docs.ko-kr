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
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732483"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="492db-102">ICLRPolicyManager::SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="492db-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="492db-103">지정 된 작업이 수행 될 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="492db-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492db-104">구문</span><span class="sxs-lookup"><span data-stu-id="492db-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="492db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="492db-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="492db-106">진행 CLR 동작을 사용자 지정 해야 하는 동작을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="492db-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="492db-107">진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, 발생할 때 CLR이 수행 해야 하는 정책 작업을 나타냅니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="492db-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="492db-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="492db-108">Return Value</span></span>  
  
|<span data-ttu-id="492db-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="492db-109">HRESULT</span></span>|<span data-ttu-id="492db-110">설명</span><span class="sxs-lookup"><span data-stu-id="492db-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="492db-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="492db-111">S_OK</span></span>|<span data-ttu-id="492db-112">`SetDefaultAction` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="492db-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="492db-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="492db-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="492db-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="492db-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="492db-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-116">The call timed out.</span></span>|  
|<span data-ttu-id="492db-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="492db-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="492db-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="492db-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="492db-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="492db-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="492db-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="492db-121">E_FAIL</span></span>|<span data-ttu-id="492db-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="492db-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="492db-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492db-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="492db-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="492db-125">E_INVALIDARG</span></span>|<span data-ttu-id="492db-126">에 대해 잘못 된가 `action` 지정 되었거나 `operation` 에 잘못 된 값이 제공 된 `operation` 경우</span><span class="sxs-lookup"><span data-stu-id="492db-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="492db-127">설명</span><span class="sxs-lookup"><span data-stu-id="492db-127">Remarks</span></span>  

 <span data-ttu-id="492db-128">모든 정책 동작 값을 CLR 작업의 기본 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="492db-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="492db-129">`SetDefaultAction` 일반적으로 동작을 에스컬레이션 하는 데만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="492db-130">예를 들어 호스트는 스레드 중단이 강제 스레드 중단으로 전환 되도록 지정할 수 있지만 반대의 경우에는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492db-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="492db-131">다음 표에서는 `action` 가능한 각 값에 대 한 유효한 값을 설명 합니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="492db-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="492db-132">값 `operation`</span><span class="sxs-lookup"><span data-stu-id="492db-132">Value for `operation`</span></span>|<span data-ttu-id="492db-133">유효한 값 `action`</span><span class="sxs-lookup"><span data-stu-id="492db-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="492db-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="492db-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="492db-135">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="492db-135">-   eAbortThread</span></span><br /><span data-ttu-id="492db-136">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="492db-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="492db-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="492db-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="492db-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-139">-   eExitProcess</span></span><br /><span data-ttu-id="492db-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-142">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="492db-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="492db-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="492db-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="492db-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="492db-145">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="492db-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="492db-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="492db-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="492db-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-148">-   eExitProcess</span></span><br /><span data-ttu-id="492db-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-151">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="492db-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="492db-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="492db-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="492db-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="492db-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-155">-   eExitProcess</span></span><br /><span data-ttu-id="492db-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-158">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="492db-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="492db-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="492db-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="492db-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-161">-   eExitProcess</span></span><br /><span data-ttu-id="492db-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-164">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="492db-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="492db-165">OPR_ProcessExit</span></span>|<span data-ttu-id="492db-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-166">-   eExitProcess</span></span><br /><span data-ttu-id="492db-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-169">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="492db-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="492db-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="492db-171">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="492db-171">-   eNoAction</span></span><br /><span data-ttu-id="492db-172">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="492db-172">-   eAbortThread</span></span><br /><span data-ttu-id="492db-173">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="492db-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="492db-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="492db-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="492db-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="492db-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-176">-   eExitProcess</span></span><br /><span data-ttu-id="492db-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="492db-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="492db-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="492db-179">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="492db-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="492db-180">요구 사항</span><span class="sxs-lookup"><span data-stu-id="492db-180">Requirements</span></span>  

 <span data-ttu-id="492db-181">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="492db-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492db-182">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="492db-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="492db-183">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492db-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="492db-184">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492db-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492db-185">참조</span><span class="sxs-lookup"><span data-stu-id="492db-185">See also</span></span>

- [<span data-ttu-id="492db-186">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="492db-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="492db-187">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="492db-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="492db-188">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="492db-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
