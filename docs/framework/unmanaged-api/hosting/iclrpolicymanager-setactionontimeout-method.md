---
title: ICLRPolicyManager::SetActionOnTimeout 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30ab869ed6b06f5c9e53d819e20d3307ccc0e8f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638998"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="13fe5-102">ICLRPolicyManager::SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="13fe5-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="13fe5-103">지정 된 작업 시간이 초과 되 면 공용 언어 런타임 (CLR)를 수행 해야 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fe5-104">구문</span><span class="sxs-lookup"><span data-stu-id="13fe5-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13fe5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13fe5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="13fe5-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 제한 시간 동작을 지정 하는 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="13fe5-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="13fe5-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="13fe5-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="13fe5-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="13fe5-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="13fe5-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="13fe5-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="13fe5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="13fe5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="13fe5-112">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 작업 시간이 초과 되 면 수행할 정책 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13fe5-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="13fe5-113">Return Value</span></span>  
  
|<span data-ttu-id="13fe5-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13fe5-114">HRESULT</span></span>|<span data-ttu-id="13fe5-115">설명</span><span class="sxs-lookup"><span data-stu-id="13fe5-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13fe5-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="13fe5-116">S_OK</span></span>|<span data-ttu-id="13fe5-117">`SetActionOnTimeout` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="13fe5-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13fe5-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13fe5-119">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13fe5-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13fe5-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13fe5-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-121">The call timed out.</span></span>|  
|<span data-ttu-id="13fe5-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13fe5-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13fe5-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13fe5-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13fe5-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13fe5-125">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13fe5-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13fe5-126">E_FAIL</span></span>|<span data-ttu-id="13fe5-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13fe5-128">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13fe5-129">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="13fe5-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="13fe5-130">E_INVALIDARG</span></span>|<span data-ttu-id="13fe5-131">제한 시간을 설정할 수 없습니다 지정 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `operation`합니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13fe5-132">설명</span><span class="sxs-lookup"><span data-stu-id="13fe5-132">Remarks</span></span>  
 <span data-ttu-id="13fe5-133">시간 제한 값을 CLR에서 설정 된 기본 시간 제한 또는 호스트에 대 한 호출에서 지정 된 값 수를 [iclrpolicymanager:: Settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="13fe5-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="13fe5-134">일부 정책은 동작 값을 CLR 작업에 대 한 제한 시간 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="13fe5-135">`SetActionOnTimeout` 일반적으로 에스컬레이션 동작에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="13fe5-136">예를 들어 호스트 스레드 중단으로 강제 변환할 수 있는지 지정할 수 있습니다 스레드 중단 하지만 반대를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="13fe5-137">아래 표에 유효한 `action` 값에 대 한 유효한 `operation` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13fe5-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="13fe5-138">에 대 한 값 `operation`</span><span class="sxs-lookup"><span data-stu-id="13fe5-138">Value for `operation`</span></span>|<span data-ttu-id="13fe5-139">에 대 한 유효한 값 `action`</span><span class="sxs-lookup"><span data-stu-id="13fe5-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="13fe5-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="13fe5-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="13fe5-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="13fe5-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="13fe5-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="13fe5-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="13fe5-143">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="13fe5-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="13fe5-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="13fe5-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="13fe5-145">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-145">-   eExitProcess</span></span><br /><span data-ttu-id="13fe5-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="13fe5-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="13fe5-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="13fe5-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="13fe5-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="13fe5-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="13fe5-150">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="13fe5-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="13fe5-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="13fe5-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="13fe5-152">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-152">-   eExitProcess</span></span><br /><span data-ttu-id="13fe5-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="13fe5-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="13fe5-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="13fe5-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="13fe5-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="13fe5-156">OPR_ProcessExit</span></span>|<span data-ttu-id="13fe5-157">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-157">-   eExitProcess</span></span><br /><span data-ttu-id="13fe5-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="13fe5-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="13fe5-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="13fe5-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="13fe5-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13fe5-161">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13fe5-161">Requirements</span></span>  
 <span data-ttu-id="13fe5-162">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13fe5-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fe5-163">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13fe5-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13fe5-164">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="13fe5-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13fe5-165">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fe5-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fe5-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="13fe5-166">See also</span></span>

- [<span data-ttu-id="13fe5-167">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="13fe5-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="13fe5-168">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="13fe5-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="13fe5-169">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13fe5-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="13fe5-170">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13fe5-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
