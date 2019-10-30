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
ms.openlocfilehash: 3a58664a7dc81059214246b53cf967b50cd61063
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140744"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="4fb11-102">ICLRPolicyManager::SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="4fb11-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="4fb11-103">지정 된 작업에 대 한 시간 제한 값을 설정 하 고, 작업이 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb11-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fb11-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fb11-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4fb11-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="4fb11-106">진행 제한 시간 및 `action` 정책을 설정할 작업을 나타내는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="4fb11-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="4fb11-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="4fb11-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="4fb11-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="4fb11-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="4fb11-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4fb11-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="4fb11-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="4fb11-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="4fb11-112">진행 새 시간 제한 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="4fb11-113">값이 INFINITE 이면 시간 제한이 `operation` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="4fb11-114">진행 `operation` 발생 하는 경우 CLR에서 수행 해야 하는 정책 작업을 나타내는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fb11-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="4fb11-115">Return Value</span></span>  
  
|<span data-ttu-id="4fb11-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fb11-116">HRESULT</span></span>|<span data-ttu-id="4fb11-117">설명</span><span class="sxs-lookup"><span data-stu-id="4fb11-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fb11-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fb11-118">S_OK</span></span>|<span data-ttu-id="4fb11-119">`SetTimeoutAndAction` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="4fb11-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4fb11-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4fb11-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4fb11-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fb11-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4fb11-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-123">The call timed out.</span></span>|  
|<span data-ttu-id="4fb11-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4fb11-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4fb11-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4fb11-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4fb11-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4fb11-127">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4fb11-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4fb11-128">E_FAIL</span></span>|<span data-ttu-id="4fb11-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4fb11-130">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4fb11-131">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4fb11-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4fb11-132">E_INVALIDARG</span></span>|<span data-ttu-id="4fb11-133">지정 된 `operation`에 대 한 제한 시간을 설정할 수 없거나 `action`에 대해 잘못 된 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fb11-134">주의</span><span class="sxs-lookup"><span data-stu-id="4fb11-134">Remarks</span></span>  
 <span data-ttu-id="4fb11-135">`SetTimeoutAndAction`는 [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 및 [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드의 기능을 캡슐화 하 고이 두 메서드에 대 한 순차적 호출 대신 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4fb11-136">모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="4fb11-137">유효한 값은 이러한 두 메서드에 대 한 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fb11-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb11-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fb11-138">Requirements</span></span>  
 <span data-ttu-id="4fb11-139">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fb11-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb11-140">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4fb11-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fb11-141">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb11-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fb11-142">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb11-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb11-143">참조</span><span class="sxs-lookup"><span data-stu-id="4fb11-143">See also</span></span>

- [<span data-ttu-id="4fb11-144">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="4fb11-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="4fb11-145">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="4fb11-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="4fb11-146">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fb11-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="4fb11-147">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="4fb11-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="4fb11-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="4fb11-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
