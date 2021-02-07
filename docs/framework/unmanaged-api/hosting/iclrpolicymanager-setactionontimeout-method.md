---
description: '자세히 알아보기: ICLRPolicyManager:: SetActionOnTimeout 메서드'
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
ms.openlocfilehash: d682acd49bdc4fa0f8c58a1300e2215816fe2718
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689029"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="053b8-103">ICLRPolicyManager::SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="053b8-103">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="053b8-104">지정 된 작업의 제한 시간이 초과 될 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-104">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="053b8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="053b8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="053b8-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="053b8-107">진행 시간 제한 작업을 지정할 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="053b8-108">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="053b8-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="053b8-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="053b8-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="053b8-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="053b8-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="053b8-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="053b8-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="053b8-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="053b8-113">진행 작업 시간이 초과 될 때 수행할 정책 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-113">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="053b8-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="053b8-114">Return Value</span></span>  
  
|<span data-ttu-id="053b8-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="053b8-115">HRESULT</span></span>|<span data-ttu-id="053b8-116">설명</span><span class="sxs-lookup"><span data-stu-id="053b8-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053b8-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="053b8-117">S_OK</span></span>|<span data-ttu-id="053b8-118">`SetActionOnTimeout` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-118">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="053b8-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="053b8-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="053b8-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="053b8-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="053b8-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="053b8-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-122">The call timed out.</span></span>|  
|<span data-ttu-id="053b8-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="053b8-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="053b8-124">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="053b8-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="053b8-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="053b8-126">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="053b8-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="053b8-127">E_FAIL</span></span>|<span data-ttu-id="053b8-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="053b8-129">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="053b8-130">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="053b8-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="053b8-131">E_INVALIDARG</span></span>|<span data-ttu-id="053b8-132">지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `operation` 된 경우</span><span class="sxs-lookup"><span data-stu-id="053b8-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053b8-133">설명</span><span class="sxs-lookup"><span data-stu-id="053b8-133">Remarks</span></span>  

 <span data-ttu-id="053b8-134">시간 제한 값은 CLR에서 설정 된 기본 시간 제한 이거나 [ICLRPolicyManager:: SetTimeout](iclrpolicymanager-settimeout-method.md) 메서드 호출에서 호스트에서 지정한 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-134">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="053b8-135">모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-135">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="053b8-136">`SetActionOnTimeout` 는 일반적으로 동작을 에스컬레이션 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-136">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="053b8-137">예를 들어 호스트는 스레드 중단이 강제 스레드 중단으로 전환 되도록 지정할 수 있지만 반대의 경우에는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-137">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="053b8-138">다음 표에서는 `action` 유효한 값에 대 한 유효한 값을 설명 합니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="053b8-138">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="053b8-139">값 `operation`</span><span class="sxs-lookup"><span data-stu-id="053b8-139">Value for `operation`</span></span>|<span data-ttu-id="053b8-140">유효한 값 `action`</span><span class="sxs-lookup"><span data-stu-id="053b8-140">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="053b8-141">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="053b8-141">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="053b8-142">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="053b8-142">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="053b8-143">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="053b8-143">-   eRudeAbortThread</span></span><br /><span data-ttu-id="053b8-144">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="053b8-144">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="053b8-145">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="053b8-145">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="053b8-146">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-146">-   eExitProcess</span></span><br /><span data-ttu-id="053b8-147">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-147">-   eFastExitProcess</span></span><br /><span data-ttu-id="053b8-148">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-148">-   eRudeExitProcess</span></span><br /><span data-ttu-id="053b8-149">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="053b8-149">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="053b8-150">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="053b8-150">OPR_AppDomainUnload</span></span>|<span data-ttu-id="053b8-151">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="053b8-151">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="053b8-152">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="053b8-152">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="053b8-153">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-153">-   eExitProcess</span></span><br /><span data-ttu-id="053b8-154">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-154">-   eFastExitProcess</span></span><br /><span data-ttu-id="053b8-155">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-155">-   eRudeExitProcess</span></span><br /><span data-ttu-id="053b8-156">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="053b8-156">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="053b8-157">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="053b8-157">OPR_ProcessExit</span></span>|<span data-ttu-id="053b8-158">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-158">-   eExitProcess</span></span><br /><span data-ttu-id="053b8-159">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-159">-   eFastExitProcess</span></span><br /><span data-ttu-id="053b8-160">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="053b8-160">-   eRudeExitProcess</span></span><br /><span data-ttu-id="053b8-161">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="053b8-161">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="053b8-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="053b8-162">Requirements</span></span>  

 <span data-ttu-id="053b8-163">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="053b8-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053b8-164">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="053b8-164">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="053b8-165">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="053b8-165">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="053b8-166">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053b8-166">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053b8-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="053b8-167">See also</span></span>

- [<span data-ttu-id="053b8-168">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="053b8-168">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="053b8-169">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="053b8-169">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="053b8-170">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="053b8-170">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="053b8-171">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="053b8-171">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
