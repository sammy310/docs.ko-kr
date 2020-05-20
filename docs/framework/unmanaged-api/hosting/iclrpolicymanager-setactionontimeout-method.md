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
ms.openlocfilehash: 0b8e7dfbe377e60b548003af10fb11392b514030
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703458"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="d2d27-102">ICLRPolicyManager::SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="d2d27-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="d2d27-103">지정 된 작업의 제한 시간이 초과 될 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d27-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2d27-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2d27-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2d27-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d2d27-106">진행 시간 제한 작업을 지정할 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="d2d27-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="d2d27-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d2d27-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="d2d27-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d2d27-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="d2d27-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d2d27-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="d2d27-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d2d27-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="d2d27-112">진행 작업 시간이 초과 될 때 수행할 정책 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2d27-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="d2d27-113">Return Value</span></span>  
  
|<span data-ttu-id="d2d27-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2d27-114">HRESULT</span></span>|<span data-ttu-id="d2d27-115">설명</span><span class="sxs-lookup"><span data-stu-id="d2d27-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2d27-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2d27-116">S_OK</span></span>|<span data-ttu-id="d2d27-117">`SetActionOnTimeout`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="d2d27-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d2d27-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d2d27-119">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d2d27-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d2d27-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d2d27-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-121">The call timed out.</span></span>|  
|<span data-ttu-id="d2d27-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d2d27-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d2d27-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d2d27-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d2d27-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d2d27-125">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d2d27-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2d27-126">E_FAIL</span></span>|<span data-ttu-id="d2d27-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2d27-128">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d2d27-129">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d2d27-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d2d27-130">E_INVALIDARG</span></span>|<span data-ttu-id="d2d27-131">지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `operation` 된 경우</span><span class="sxs-lookup"><span data-stu-id="d2d27-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2d27-132">설명</span><span class="sxs-lookup"><span data-stu-id="d2d27-132">Remarks</span></span>  
 <span data-ttu-id="d2d27-133">시간 제한 값은 CLR에서 설정 된 기본 시간 제한 이거나 [ICLRPolicyManager:: SetTimeout](iclrpolicymanager-settimeout-method.md) 메서드 호출에서 호스트에서 지정한 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="d2d27-134">모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="d2d27-135">`SetActionOnTimeout`는 일반적으로 동작을 에스컬레이션 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="d2d27-136">예를 들어 호스트는 스레드 중단이 강제 스레드 중단으로 전환 되도록 지정할 수 있지만 반대의 경우에는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="d2d27-137">다음 표에서는 `action` 유효한 값에 대 한 유효한 값을 설명 합니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="d2d27-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="d2d27-138">값`operation`</span><span class="sxs-lookup"><span data-stu-id="d2d27-138">Value for `operation`</span></span>|<span data-ttu-id="d2d27-139">유효한 값`action`</span><span class="sxs-lookup"><span data-stu-id="d2d27-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="d2d27-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d2d27-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="d2d27-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d2d27-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="d2d27-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="d2d27-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="d2d27-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d2d27-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d2d27-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d2d27-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d2d27-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-145">-   eExitProcess</span></span><br /><span data-ttu-id="d2d27-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="d2d27-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d2d27-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d2d27-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d2d27-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d2d27-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="d2d27-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d2d27-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d2d27-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d2d27-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d2d27-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-152">-   eExitProcess</span></span><br /><span data-ttu-id="d2d27-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="d2d27-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d2d27-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d2d27-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d2d27-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d2d27-156">OPR_ProcessExit</span></span>|<span data-ttu-id="d2d27-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-157">-   eExitProcess</span></span><br /><span data-ttu-id="d2d27-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="d2d27-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d2d27-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d2d27-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d2d27-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2d27-161">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2d27-161">Requirements</span></span>  
 <span data-ttu-id="d2d27-162">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d27-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2d27-163">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2d27-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2d27-164">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d27-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2d27-165">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2d27-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d27-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2d27-166">See also</span></span>

- [<span data-ttu-id="d2d27-167">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="d2d27-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d2d27-168">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="d2d27-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="d2d27-169">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2d27-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d2d27-170">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2d27-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
