---
description: '자세히 알아보기: ICLRPolicyManager:: SetTimeoutAndAction 메서드'
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
ms.openlocfilehash: c91d43cce381bef804b30e9e1dcb50574ddcd1b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716577"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="897f9-103">ICLRPolicyManager::SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="897f9-103">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>

<span data-ttu-id="897f9-104">지정 된 작업에 대 한 시간 제한 값을 설정 하 고, 작업이 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-104">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="897f9-105">구문</span><span class="sxs-lookup"><span data-stu-id="897f9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="897f9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="897f9-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="897f9-107">진행 제한 시간 및 `action` 정책을 설정할 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="897f9-108">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="897f9-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="897f9-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="897f9-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="897f9-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="897f9-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="897f9-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="897f9-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="897f9-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="897f9-113">진행 새 시간 제한 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-113">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="897f9-114">값이 INFINITE 이면 `operation` 시간 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-114">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="897f9-115">진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, CLR이 발생할 때 수행 해야 하는 정책 작업을 나타냅니다 `operation` .</span><span class="sxs-lookup"><span data-stu-id="897f9-115">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="897f9-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="897f9-116">Return Value</span></span>  
  
|<span data-ttu-id="897f9-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="897f9-117">HRESULT</span></span>|<span data-ttu-id="897f9-118">설명</span><span class="sxs-lookup"><span data-stu-id="897f9-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="897f9-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="897f9-119">S_OK</span></span>|<span data-ttu-id="897f9-120">`SetTimeoutAndAction` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-120">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="897f9-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="897f9-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="897f9-122">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="897f9-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="897f9-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="897f9-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-124">The call timed out.</span></span>|  
|<span data-ttu-id="897f9-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="897f9-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="897f9-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="897f9-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="897f9-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="897f9-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="897f9-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="897f9-129">E_FAIL</span></span>|<span data-ttu-id="897f9-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="897f9-131">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="897f9-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="897f9-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="897f9-133">E_INVALIDARG</span></span>|<span data-ttu-id="897f9-134">지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `action` 된 경우</span><span class="sxs-lookup"><span data-stu-id="897f9-134">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="897f9-135">설명</span><span class="sxs-lookup"><span data-stu-id="897f9-135">Remarks</span></span>  

 <span data-ttu-id="897f9-136">`SetTimeoutAndAction` 는 [ICLRPolicyManager:: SetTimeout](iclrpolicymanager-settimeout-method.md) 및 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 메서드의 기능을 캡슐화 하며 이러한 두 메서드에 대 한 순차적 호출 대신 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-136">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="897f9-137">모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-137">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="897f9-138">유효한 값은 이러한 두 메서드에 대 한 항목의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="897f9-138">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="897f9-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="897f9-139">Requirements</span></span>  

 <span data-ttu-id="897f9-140">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="897f9-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="897f9-141">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="897f9-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="897f9-142">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="897f9-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="897f9-143">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="897f9-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897f9-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="897f9-144">See also</span></span>

- [<span data-ttu-id="897f9-145">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="897f9-145">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="897f9-146">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="897f9-146">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="897f9-147">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="897f9-147">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="897f9-148">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="897f9-148">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="897f9-149">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="897f9-149">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
