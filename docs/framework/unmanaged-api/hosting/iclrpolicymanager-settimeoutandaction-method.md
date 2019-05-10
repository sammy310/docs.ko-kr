---
title: ICLRPolicyManager::SetTimeoutAndAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb5db23db752cc82b04d97cb2bc81a3155d465be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627171"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="f70e5-102">ICLRPolicyManager::SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="f70e5-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="f70e5-103">지정된 된 작업에 대 한 제한 시간 값을 설정 하 고는 CLR (공용 언어 런타임)는 작업이 수행 될 때 수행 해야 정책 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f70e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f70e5-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f70e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f70e5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="f70e5-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값을 나타내는 시간 제한 및 정책을 설정 하는 작업의 `action`합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="f70e5-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="f70e5-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="f70e5-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="f70e5-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="f70e5-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="f70e5-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f70e5-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="f70e5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f70e5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="f70e5-112">[in] 새 제한 시간 값을 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="f70e5-113">값이 무한 원인 `operation` 을 시간 초과 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="f70e5-114">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값을 CLR 때 수행 해야 하는 정책 작업을 나타내는 `operation` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f70e5-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="f70e5-115">Return Value</span></span>  
  
|<span data-ttu-id="f70e5-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f70e5-116">HRESULT</span></span>|<span data-ttu-id="f70e5-117">설명</span><span class="sxs-lookup"><span data-stu-id="f70e5-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f70e5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f70e5-118">S_OK</span></span>|<span data-ttu-id="f70e5-119">`SetTimeoutAndAction` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="f70e5-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f70e5-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f70e5-121">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f70e5-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f70e5-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f70e5-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-123">The call timed out.</span></span>|  
|<span data-ttu-id="f70e5-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f70e5-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f70e5-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f70e5-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f70e5-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f70e5-127">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f70e5-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f70e5-128">E_FAIL</span></span>|<span data-ttu-id="f70e5-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f70e5-130">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f70e5-131">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f70e5-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f70e5-132">E_INVALIDARG</span></span>|<span data-ttu-id="f70e5-133">제한 시간을 설정할 수 없습니다 지정 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `action`합니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f70e5-134">설명</span><span class="sxs-lookup"><span data-stu-id="f70e5-134">Remarks</span></span>  
 <span data-ttu-id="f70e5-135">`SetTimeoutAndAction` 기능을 캡슐화 합니다 [iclrpolicymanager:: Settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 하 고 [iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드를 두 가지 방법에 대 한 순차적 호출 대신 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f70e5-136">일부 정책은 동작 값을 CLR 작업에 대 한 제한 시간 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f70e5-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="f70e5-137">유효한 값에 대 한 이러한 두 가지 방법에 대 한 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f70e5-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f70e5-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f70e5-138">Requirements</span></span>  
 <span data-ttu-id="f70e5-139">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f70e5-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f70e5-140">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f70e5-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f70e5-141">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f70e5-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f70e5-142">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f70e5-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70e5-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="f70e5-143">See also</span></span>

- [<span data-ttu-id="f70e5-144">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="f70e5-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="f70e5-145">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="f70e5-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="f70e5-146">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f70e5-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="f70e5-147">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="f70e5-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="f70e5-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="f70e5-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
