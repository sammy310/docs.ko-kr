---
title: ICLRPolicyManager::SetActionOnFailure 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117432"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="41cb6-102">ICLRPolicyManager::SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="41cb6-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="41cb6-103">CLR (공용 언어 런타임)은 지정 된 오류가 발생할 때 수행 해야 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41cb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="41cb6-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41cb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41cb6-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="41cb6-106">[in] 중 하나는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 값을 나타내는 작업을 수행 하려는 실패 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="41cb6-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 오류가 발생할 경우 수행할 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="41cb6-108">에서 지원 되는 값 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41cb6-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41cb6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="41cb6-109">Return Value</span></span>  
  
|<span data-ttu-id="41cb6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41cb6-110">HRESULT</span></span>|<span data-ttu-id="41cb6-111">설명</span><span class="sxs-lookup"><span data-stu-id="41cb6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="41cb6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="41cb6-112">S_OK</span></span>|<span data-ttu-id="41cb6-113">`SetActionOnFailure` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="41cb6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="41cb6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="41cb6-115">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="41cb6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="41cb6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="41cb6-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-117">The call timed out.</span></span>|  
|<span data-ttu-id="41cb6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="41cb6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="41cb6-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="41cb6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="41cb6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="41cb6-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="41cb6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41cb6-122">E_FAIL</span></span>|<span data-ttu-id="41cb6-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="41cb6-124">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="41cb6-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="41cb6-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="41cb6-126">E_INVALIDARG</span></span>|<span data-ttu-id="41cb6-127">지정된 된 작업에 대 한 정책 작업을 설정할 수 없습니다 또는 작업에 대 한 정책 작업이 잘못 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41cb6-128">설명</span><span class="sxs-lookup"><span data-stu-id="41cb6-128">Remarks</span></span>  
 <span data-ttu-id="41cb6-129">기본적으로 CLR 메모리와 같은 리소스를 할당 하는 데 실패할 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="41cb6-130">`SetActionOnFailure` 호스트를 실패 시 되려면 정책 작업을 지정 하 여이 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="41cb6-131">다음 표에서 조합을 보여 줍니다 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 하 고 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 지원 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41cb6-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="41cb6-132">(에서 FAIL_ 접두사를 생략 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 값입니다.)</span><span class="sxs-lookup"><span data-stu-id="41cb6-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="41cb6-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="41cb6-133">NonCriticalResource</span></span>|<span data-ttu-id="41cb6-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="41cb6-134">CriticalResource</span></span>|<span data-ttu-id="41cb6-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="41cb6-135">FatalRuntime</span></span>|<span data-ttu-id="41cb6-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="41cb6-136">OrphanedLock</span></span>|<span data-ttu-id="41cb6-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="41cb6-137">StackOverflow</span></span>|<span data-ttu-id="41cb6-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="41cb6-138">AccessViolation</span></span>|<span data-ttu-id="41cb6-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="41cb6-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="41cb6-140">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-140">X</span></span>|<span data-ttu-id="41cb6-141">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-141">X</span></span>||||<span data-ttu-id="41cb6-142">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-142">N/A</span></span>||  
|<span data-ttu-id="41cb6-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="41cb6-143">eThrowException</span></span>|<span data-ttu-id="41cb6-144">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-144">X</span></span>|<span data-ttu-id="41cb6-145">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-145">X</span></span>||||<span data-ttu-id="41cb6-146">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="41cb6-147">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-147">X</span></span>|<span data-ttu-id="41cb6-148">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-148">X</span></span>||||<span data-ttu-id="41cb6-149">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-149">N/A</span></span>|<span data-ttu-id="41cb6-150">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="41cb6-151">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-151">X</span></span>|<span data-ttu-id="41cb6-152">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-152">X</span></span>||||<span data-ttu-id="41cb6-153">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-153">N/A</span></span>|<span data-ttu-id="41cb6-154">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="41cb6-155">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-155">X</span></span>|<span data-ttu-id="41cb6-156">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-156">X</span></span>||<span data-ttu-id="41cb6-157">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-157">X</span></span>||<span data-ttu-id="41cb6-158">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-158">N/A</span></span>|<span data-ttu-id="41cb6-159">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="41cb6-160">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-160">X</span></span>|<span data-ttu-id="41cb6-161">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-161">X</span></span>||<span data-ttu-id="41cb6-162">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-162">X</span></span>|<span data-ttu-id="41cb6-163">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-163">X</span></span>|<span data-ttu-id="41cb6-164">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-164">N/A</span></span>|<span data-ttu-id="41cb6-165">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="41cb6-166">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-166">X</span></span>|<span data-ttu-id="41cb6-167">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-167">X</span></span>||<span data-ttu-id="41cb6-168">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-168">X</span></span>|<span data-ttu-id="41cb6-169">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-169">X</span></span>|<span data-ttu-id="41cb6-170">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-170">N/A</span></span>|<span data-ttu-id="41cb6-171">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-171">X</span></span>|  
|<span data-ttu-id="41cb6-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="41cb6-172">eFastExitProcess</span></span>|<span data-ttu-id="41cb6-173">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-173">X</span></span>|<span data-ttu-id="41cb6-174">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-174">X</span></span>||<span data-ttu-id="41cb6-175">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-175">X</span></span>|<span data-ttu-id="41cb6-176">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-176">X</span></span>|<span data-ttu-id="41cb6-177">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="41cb6-178">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-178">X</span></span>|<span data-ttu-id="41cb6-179">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-179">X</span></span>|<span data-ttu-id="41cb6-180">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-180">X</span></span>|<span data-ttu-id="41cb6-181">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-181">X</span></span>|<span data-ttu-id="41cb6-182">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-182">X</span></span>|<span data-ttu-id="41cb6-183">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="41cb6-184">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-184">X</span></span>|<span data-ttu-id="41cb6-185">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-185">X</span></span>|<span data-ttu-id="41cb6-186">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-186">X</span></span>|<span data-ttu-id="41cb6-187">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-187">X</span></span>|<span data-ttu-id="41cb6-188">X</span><span class="sxs-lookup"><span data-stu-id="41cb6-188">X</span></span>|<span data-ttu-id="41cb6-189">N/A</span><span class="sxs-lookup"><span data-stu-id="41cb6-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="41cb6-190">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41cb6-190">Requirements</span></span>  
 <span data-ttu-id="41cb6-191">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41cb6-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cb6-192">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="41cb6-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41cb6-193">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="41cb6-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41cb6-194">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cb6-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cb6-195">참고자료</span><span class="sxs-lookup"><span data-stu-id="41cb6-195">See also</span></span>

- [<span data-ttu-id="41cb6-196">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="41cb6-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="41cb6-197">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="41cb6-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="41cb6-198">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41cb6-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="41cb6-199">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41cb6-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
