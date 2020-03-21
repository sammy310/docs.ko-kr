---
title: IHostPolicyManager::OnDefaultAction 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178017"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="465e5-102">IHostPolicyManager::OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="465e5-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="465e5-103">CLR(공통 언어 런타임)이 스레드 중단 또는 <xref:System.AppDomain> 언로드에 대한 응답으로 [ICLRPolicyManager:SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 메서드에 대한 호출에 의해 설정된 기본 작업을 수행하려고 한다는 것을 호스트에 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="465e5-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="465e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="465e5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="465e5-106">【인】 CLR이 응답하는 이벤트의 종류를 나타내는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="465e5-107">【인】 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 중 하나로, CLR이 이벤트에 응답하여 수행중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="465e5-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="465e5-108">Return Value</span></span>  
  
|<span data-ttu-id="465e5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="465e5-109">HRESULT</span></span>|<span data-ttu-id="465e5-110">Description</span><span class="sxs-lookup"><span data-stu-id="465e5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="465e5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="465e5-111">S_OK</span></span>|<span data-ttu-id="465e5-112">`OnDefaultAction`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="465e5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="465e5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="465e5-114">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="465e5-115">성공적 으로</span><span class="sxs-lookup"><span data-stu-id="465e5-115">successfully</span></span>|  
|<span data-ttu-id="465e5-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="465e5-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="465e5-117">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-117">The call timed out.</span></span>|  
|<span data-ttu-id="465e5-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="465e5-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="465e5-119">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="465e5-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="465e5-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="465e5-121">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="465e5-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="465e5-122">E_FAIL</span></span>|<span data-ttu-id="465e5-123">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="465e5-124">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="465e5-125">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="465e5-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="465e5-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="465e5-126">Requirements</span></span>  
 <span data-ttu-id="465e5-127">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="465e5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="465e5-128">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="465e5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="465e5-129">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="465e5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="465e5-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="465e5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465e5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="465e5-131">See also</span></span>

- [<span data-ttu-id="465e5-132">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="465e5-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="465e5-133">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="465e5-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="465e5-134">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="465e5-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="465e5-135">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="465e5-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
