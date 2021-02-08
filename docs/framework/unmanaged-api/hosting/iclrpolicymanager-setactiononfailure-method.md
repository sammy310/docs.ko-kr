---
description: '자세히 알아보기: ICLRPolicyManager:: SetActionOnFailure 메서드'
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
ms.openlocfilehash: 67d3ca5d7924caf0a768b4de53b4b24f1c72fa27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789803"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="972db-103">ICLRPolicyManager::SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="972db-103">ICLRPolicyManager::SetActionOnFailure Method</span></span>

<span data-ttu-id="972db-104">지정 된 오류가 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="972db-104">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="972db-105">구문</span><span class="sxs-lookup"><span data-stu-id="972db-105">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="972db-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="972db-106">Parameters</span></span>  

 `failure`  
 <span data-ttu-id="972db-107">진행 작업을 수행할 실패 유형을 나타내는 [EClrFailure](eclrfailure-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="972db-107">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="972db-108">진행 오류가 발생할 때 수행할 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="972db-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="972db-109">지원 되는 값의 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="972db-109">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="972db-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="972db-110">Return Value</span></span>  
  
|<span data-ttu-id="972db-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="972db-111">HRESULT</span></span>|<span data-ttu-id="972db-112">설명</span><span class="sxs-lookup"><span data-stu-id="972db-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="972db-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="972db-113">S_OK</span></span>|<span data-ttu-id="972db-114">`SetActionOnFailure` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-114">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="972db-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="972db-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="972db-116">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-116">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="972db-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="972db-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="972db-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-118">The call timed out.</span></span>|  
|<span data-ttu-id="972db-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="972db-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="972db-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="972db-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="972db-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="972db-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="972db-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="972db-123">E_FAIL</span></span>|<span data-ttu-id="972db-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="972db-125">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="972db-125">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="972db-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="972db-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="972db-127">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="972db-127">E_INVALIDARG</span></span>|<span data-ttu-id="972db-128">지정 된 작업에 대해 정책 작업을 설정할 수 없거나 작업에 대해 잘못 된 정책 동작을 지정한 경우</span><span class="sxs-lookup"><span data-stu-id="972db-128">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="972db-129">설명</span><span class="sxs-lookup"><span data-stu-id="972db-129">Remarks</span></span>  

 <span data-ttu-id="972db-130">기본적으로 CLR은 메모리와 같은 리소스를 할당 하지 못한 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="972db-130">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="972db-131">`SetActionOnFailure` 오류가 발생할 때 수행할 정책 작업을 지정 하 여 호스트가이 동작을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="972db-131">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="972db-132">다음 표에서는 지원 되는 [EClrFailure](eclrfailure-enumeration.md) 및 [EPolicyAction](epolicyaction-enumeration.md) 값의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="972db-132">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="972db-133">FAIL_ 접두사는 [EClrFailure](eclrfailure-enumeration.md) 값에서 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="972db-133">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="972db-134">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="972db-134">NonCriticalResource</span></span>|<span data-ttu-id="972db-135">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="972db-135">CriticalResource</span></span>|<span data-ttu-id="972db-136">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="972db-136">FatalRuntime</span></span>|<span data-ttu-id="972db-137">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="972db-137">OrphanedLock</span></span>|<span data-ttu-id="972db-138">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="972db-138">StackOverflow</span></span>|<span data-ttu-id="972db-139">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="972db-139">AccessViolation</span></span>|<span data-ttu-id="972db-140">CodeContract</span><span class="sxs-lookup"><span data-stu-id="972db-140">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="972db-141">X</span><span class="sxs-lookup"><span data-stu-id="972db-141">X</span></span>|<span data-ttu-id="972db-142">X</span><span class="sxs-lookup"><span data-stu-id="972db-142">X</span></span>||||<span data-ttu-id="972db-143">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-143">N/A</span></span>||  
|<span data-ttu-id="972db-144">eThrowException</span><span class="sxs-lookup"><span data-stu-id="972db-144">eThrowException</span></span>|<span data-ttu-id="972db-145">X</span><span class="sxs-lookup"><span data-stu-id="972db-145">X</span></span>|<span data-ttu-id="972db-146">X</span><span class="sxs-lookup"><span data-stu-id="972db-146">X</span></span>||||<span data-ttu-id="972db-147">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-147">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="972db-148">X</span><span class="sxs-lookup"><span data-stu-id="972db-148">X</span></span>|<span data-ttu-id="972db-149">X</span><span class="sxs-lookup"><span data-stu-id="972db-149">X</span></span>||||<span data-ttu-id="972db-150">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-150">N/A</span></span>|<span data-ttu-id="972db-151">X</span><span class="sxs-lookup"><span data-stu-id="972db-151">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="972db-152">X</span><span class="sxs-lookup"><span data-stu-id="972db-152">X</span></span>|<span data-ttu-id="972db-153">X</span><span class="sxs-lookup"><span data-stu-id="972db-153">X</span></span>||||<span data-ttu-id="972db-154">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-154">N/A</span></span>|<span data-ttu-id="972db-155">X</span><span class="sxs-lookup"><span data-stu-id="972db-155">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="972db-156">X</span><span class="sxs-lookup"><span data-stu-id="972db-156">X</span></span>|<span data-ttu-id="972db-157">X</span><span class="sxs-lookup"><span data-stu-id="972db-157">X</span></span>||<span data-ttu-id="972db-158">X</span><span class="sxs-lookup"><span data-stu-id="972db-158">X</span></span>||<span data-ttu-id="972db-159">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-159">N/A</span></span>|<span data-ttu-id="972db-160">X</span><span class="sxs-lookup"><span data-stu-id="972db-160">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="972db-161">X</span><span class="sxs-lookup"><span data-stu-id="972db-161">X</span></span>|<span data-ttu-id="972db-162">X</span><span class="sxs-lookup"><span data-stu-id="972db-162">X</span></span>||<span data-ttu-id="972db-163">X</span><span class="sxs-lookup"><span data-stu-id="972db-163">X</span></span>|<span data-ttu-id="972db-164">X</span><span class="sxs-lookup"><span data-stu-id="972db-164">X</span></span>|<span data-ttu-id="972db-165">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-165">N/A</span></span>|<span data-ttu-id="972db-166">X</span><span class="sxs-lookup"><span data-stu-id="972db-166">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="972db-167">X</span><span class="sxs-lookup"><span data-stu-id="972db-167">X</span></span>|<span data-ttu-id="972db-168">X</span><span class="sxs-lookup"><span data-stu-id="972db-168">X</span></span>||<span data-ttu-id="972db-169">X</span><span class="sxs-lookup"><span data-stu-id="972db-169">X</span></span>|<span data-ttu-id="972db-170">X</span><span class="sxs-lookup"><span data-stu-id="972db-170">X</span></span>|<span data-ttu-id="972db-171">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-171">N/A</span></span>|<span data-ttu-id="972db-172">X</span><span class="sxs-lookup"><span data-stu-id="972db-172">X</span></span>|  
|<span data-ttu-id="972db-173">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="972db-173">eFastExitProcess</span></span>|<span data-ttu-id="972db-174">X</span><span class="sxs-lookup"><span data-stu-id="972db-174">X</span></span>|<span data-ttu-id="972db-175">X</span><span class="sxs-lookup"><span data-stu-id="972db-175">X</span></span>||<span data-ttu-id="972db-176">X</span><span class="sxs-lookup"><span data-stu-id="972db-176">X</span></span>|<span data-ttu-id="972db-177">X</span><span class="sxs-lookup"><span data-stu-id="972db-177">X</span></span>|<span data-ttu-id="972db-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-178">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="972db-179">X</span><span class="sxs-lookup"><span data-stu-id="972db-179">X</span></span>|<span data-ttu-id="972db-180">X</span><span class="sxs-lookup"><span data-stu-id="972db-180">X</span></span>|<span data-ttu-id="972db-181">X</span><span class="sxs-lookup"><span data-stu-id="972db-181">X</span></span>|<span data-ttu-id="972db-182">X</span><span class="sxs-lookup"><span data-stu-id="972db-182">X</span></span>|<span data-ttu-id="972db-183">X</span><span class="sxs-lookup"><span data-stu-id="972db-183">X</span></span>|<span data-ttu-id="972db-184">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-184">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="972db-185">X</span><span class="sxs-lookup"><span data-stu-id="972db-185">X</span></span>|<span data-ttu-id="972db-186">X</span><span class="sxs-lookup"><span data-stu-id="972db-186">X</span></span>|<span data-ttu-id="972db-187">X</span><span class="sxs-lookup"><span data-stu-id="972db-187">X</span></span>|<span data-ttu-id="972db-188">X</span><span class="sxs-lookup"><span data-stu-id="972db-188">X</span></span>|<span data-ttu-id="972db-189">X</span><span class="sxs-lookup"><span data-stu-id="972db-189">X</span></span>|<span data-ttu-id="972db-190">해당 없음</span><span class="sxs-lookup"><span data-stu-id="972db-190">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="972db-191">요구 사항</span><span class="sxs-lookup"><span data-stu-id="972db-191">Requirements</span></span>  

 <span data-ttu-id="972db-192">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="972db-192">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="972db-193">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="972db-193">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="972db-194">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="972db-194">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="972db-195">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="972db-195">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="972db-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="972db-196">See also</span></span>

- [<span data-ttu-id="972db-197">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="972db-197">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="972db-198">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="972db-198">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="972db-199">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="972db-199">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="972db-200">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="972db-200">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
