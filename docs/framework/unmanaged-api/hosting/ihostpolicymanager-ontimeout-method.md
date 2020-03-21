---
title: IHostPolicyManager::OnTimeout 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178013"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="62b45-102">IHostPolicyManager::OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="62b45-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="62b45-103">호스트에 공통 언어 런타임(CLR)이 [ICLRPolicyPolicy::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드에 대한 호출에서 지정한 작업을 수행하려고 한다는 것을 호스트에 시간 지정에 대한 응답으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b45-104">구문</span><span class="sxs-lookup"><span data-stu-id="62b45-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62b45-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62b45-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="62b45-106">【인】 시간 중지된 작업 종류를 나타내는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="62b45-107">【인】 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 중 하나로, CLR이 시간 시간에 대한 응답으로 수행하는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62b45-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="62b45-108">Return Value</span></span>  
  
|<span data-ttu-id="62b45-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62b45-109">HRESULT</span></span>|<span data-ttu-id="62b45-110">Description</span><span class="sxs-lookup"><span data-stu-id="62b45-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62b45-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="62b45-111">S_OK</span></span>|<span data-ttu-id="62b45-112">`OnTimeout`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="62b45-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62b45-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62b45-114">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62b45-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62b45-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62b45-116">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-116">The call timed out.</span></span>|  
|<span data-ttu-id="62b45-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62b45-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62b45-118">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62b45-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62b45-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62b45-120">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62b45-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62b45-121">E_FAIL</span></span>|<span data-ttu-id="62b45-122">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62b45-123">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62b45-124">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="62b45-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62b45-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62b45-125">Requirements</span></span>  
 <span data-ttu-id="62b45-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62b45-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62b45-127">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="62b45-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62b45-128">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="62b45-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62b45-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62b45-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b45-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62b45-130">See also</span></span>

- [<span data-ttu-id="62b45-131">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="62b45-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="62b45-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="62b45-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="62b45-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62b45-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="62b45-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62b45-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
