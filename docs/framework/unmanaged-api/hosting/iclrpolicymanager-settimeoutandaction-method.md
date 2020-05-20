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
ms.openlocfilehash: efd30ef04c148d5e098110efcb37e50f143884e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703430"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="3b41a-102">ICLRPolicyManager::SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="3b41a-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="3b41a-103">지정 된 작업에 대 한 시간 제한 값을 설정 하 고, 작업이 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b41a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b41a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b41a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b41a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="3b41a-106">진행 제한 시간 및 `action` 정책을 설정할 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="3b41a-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="3b41a-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3b41a-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="3b41a-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3b41a-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="3b41a-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3b41a-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="3b41a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3b41a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="3b41a-112">진행 새 시간 제한 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="3b41a-113">값이 INFINITE 이면 `operation` 시간 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="3b41a-114">진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, CLR이 발생할 때 수행 해야 하는 정책 작업을 나타냅니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="3b41a-114">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b41a-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="3b41a-115">Return Value</span></span>  
  
|<span data-ttu-id="3b41a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b41a-116">HRESULT</span></span>|<span data-ttu-id="3b41a-117">설명</span><span class="sxs-lookup"><span data-stu-id="3b41a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b41a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b41a-118">S_OK</span></span>|<span data-ttu-id="3b41a-119">`SetTimeoutAndAction`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="3b41a-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b41a-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b41a-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b41a-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b41a-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b41a-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-123">The call timed out.</span></span>|  
|<span data-ttu-id="3b41a-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b41a-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b41a-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b41a-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b41a-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b41a-127">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b41a-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b41a-128">E_FAIL</span></span>|<span data-ttu-id="3b41a-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b41a-130">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b41a-131">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3b41a-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3b41a-132">E_INVALIDARG</span></span>|<span data-ttu-id="3b41a-133">지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `action` 된 경우</span><span class="sxs-lookup"><span data-stu-id="3b41a-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b41a-134">설명</span><span class="sxs-lookup"><span data-stu-id="3b41a-134">Remarks</span></span>  
 <span data-ttu-id="3b41a-135">`SetTimeoutAndAction`는 [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 및 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 메서드의 기능을 캡슐화 하며 이러한 두 메서드에 대 한 순차적 호출 대신 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3b41a-136">모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="3b41a-137">유효한 값은 이러한 두 메서드에 대 한 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b41a-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b41a-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b41a-138">Requirements</span></span>  
 <span data-ttu-id="3b41a-139">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b41a-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b41a-140">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3b41a-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b41a-141">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b41a-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b41a-142">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b41a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b41a-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b41a-143">See also</span></span>

- [<span data-ttu-id="3b41a-144">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="3b41a-144">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="3b41a-145">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="3b41a-145">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="3b41a-146">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b41a-146">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="3b41a-147">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="3b41a-147">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="3b41a-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="3b41a-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
