---
description: '자세히 알아보기: ICLRPolicyManager:: SetDefaultAction 메서드'
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
ms.openlocfilehash: cedf29f6217660493b151e06220158e931385d79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637367"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="8c71d-103">ICLRPolicyManager::SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="8c71d-103">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="8c71d-104">지정 된 작업이 수행 될 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-104">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c71d-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c71d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c71d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c71d-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="8c71d-107">진행 CLR 동작을 사용자 지정 해야 하는 동작을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="8c71d-108">진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, 발생할 때 CLR이 수행 해야 하는 정책 작업을 나타냅니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="8c71d-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c71d-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="8c71d-109">Return Value</span></span>  
  
|<span data-ttu-id="8c71d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c71d-110">HRESULT</span></span>|<span data-ttu-id="8c71d-111">설명</span><span class="sxs-lookup"><span data-stu-id="8c71d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c71d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c71d-112">S_OK</span></span>|<span data-ttu-id="8c71d-113">`SetDefaultAction` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-113">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="8c71d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c71d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c71d-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c71d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c71d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c71d-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-117">The call timed out.</span></span>|  
|<span data-ttu-id="8c71d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c71d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c71d-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c71d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c71d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c71d-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c71d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c71d-122">E_FAIL</span></span>|<span data-ttu-id="8c71d-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c71d-124">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c71d-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8c71d-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8c71d-126">E_INVALIDARG</span></span>|<span data-ttu-id="8c71d-127">에 대해 잘못 된가 `action` 지정 되었거나 `operation` 에 잘못 된 값이 제공 된 `operation` 경우</span><span class="sxs-lookup"><span data-stu-id="8c71d-127">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c71d-128">설명</span><span class="sxs-lookup"><span data-stu-id="8c71d-128">Remarks</span></span>  

 <span data-ttu-id="8c71d-129">모든 정책 동작 값을 CLR 작업의 기본 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-129">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="8c71d-130">`SetDefaultAction` 일반적으로 동작을 에스컬레이션 하는 데만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-130">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="8c71d-131">예를 들어 호스트는 스레드 중단이 강제 스레드 중단으로 전환 되도록 지정할 수 있지만 반대의 경우에는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-131">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="8c71d-132">다음 표에서는 `action` 가능한 각 값에 대 한 유효한 값을 설명 합니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="8c71d-132">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="8c71d-133">값 `operation`</span><span class="sxs-lookup"><span data-stu-id="8c71d-133">Value for `operation`</span></span>|<span data-ttu-id="8c71d-134">유효한 값 `action`</span><span class="sxs-lookup"><span data-stu-id="8c71d-134">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="8c71d-135">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="8c71d-135">OPR_ThreadAbort</span></span>|<span data-ttu-id="8c71d-136">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="8c71d-136">-   eAbortThread</span></span><br /><span data-ttu-id="8c71d-137">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="8c71d-137">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8c71d-138">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-138">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-139">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-139">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-140">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-140">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-141">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-141">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-142">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-142">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-143">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-143">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8c71d-144">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8c71d-144">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="8c71d-145">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8c71d-145">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="8c71d-146">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="8c71d-146">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8c71d-147">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-147">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-148">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-148">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-149">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-149">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-150">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-150">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-151">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-151">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-152">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-152">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8c71d-153">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="8c71d-153">OPR_AppDomainUnload</span></span>|<span data-ttu-id="8c71d-154">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-154">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-155">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-155">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-156">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-156">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-157">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-157">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-158">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-158">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-159">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-159">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8c71d-160">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="8c71d-160">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="8c71d-161">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-161">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-162">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-162">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-163">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-163">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-164">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-164">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-165">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-165">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8c71d-166">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="8c71d-166">OPR_ProcessExit</span></span>|<span data-ttu-id="8c71d-167">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-167">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-168">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-168">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-169">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-169">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-170">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-170">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8c71d-171">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="8c71d-171">OPR_FinalizerRun</span></span>|<span data-ttu-id="8c71d-172">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="8c71d-172">-   eNoAction</span></span><br /><span data-ttu-id="8c71d-173">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="8c71d-173">-   eAbortThread</span></span><br /><span data-ttu-id="8c71d-174">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="8c71d-174">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8c71d-175">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-175">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-176">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8c71d-176">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8c71d-177">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-177">-   eExitProcess</span></span><br /><span data-ttu-id="8c71d-178">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-178">-   eFastExitProcess</span></span><br /><span data-ttu-id="8c71d-179">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8c71d-179">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8c71d-180">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="8c71d-180">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c71d-181">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c71d-181">Requirements</span></span>  

 <span data-ttu-id="8c71d-182">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c71d-182">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c71d-183">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8c71d-183">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c71d-184">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c71d-184">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c71d-185">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c71d-185">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c71d-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c71d-186">See also</span></span>

- [<span data-ttu-id="8c71d-187">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="8c71d-187">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="8c71d-188">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="8c71d-188">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="8c71d-189">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c71d-189">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
