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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37d04855a7ddc613c3857867179ec84ea0f7b6ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780978"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="67e93-102">IHostPolicyManager::OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="67e93-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="67e93-103">CLR (공용 언어 런타임)를 호출 하 여 설정 된 기본 작업을 수행 하는 호스트에 알립니다 합니다 [iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 스레드 중단에 대 한 응답에서 메서드 또는 <xref:System.AppDomain> 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e93-104">구문</span><span class="sxs-lookup"><span data-stu-id="67e93-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67e93-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67e93-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="67e93-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) CLR가 응답 하는 이벤트의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="67e93-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) CLR 이벤트에 대 한 응답으로 수행 되는 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67e93-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="67e93-108">Return Value</span></span>  
  
|<span data-ttu-id="67e93-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67e93-109">HRESULT</span></span>|<span data-ttu-id="67e93-110">Description</span><span class="sxs-lookup"><span data-stu-id="67e93-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67e93-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="67e93-111">S_OK</span></span>|<span data-ttu-id="67e93-112">`OnDefaultAction` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="67e93-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67e93-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67e93-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="67e93-115">successfully</span><span class="sxs-lookup"><span data-stu-id="67e93-115">successfully</span></span>|  
|<span data-ttu-id="67e93-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67e93-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67e93-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-117">The call timed out.</span></span>|  
|<span data-ttu-id="67e93-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67e93-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67e93-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67e93-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67e93-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67e93-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67e93-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67e93-122">E_FAIL</span></span>|<span data-ttu-id="67e93-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67e93-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67e93-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e93-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67e93-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67e93-126">Requirements</span></span>  
 <span data-ttu-id="67e93-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67e93-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e93-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67e93-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67e93-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="67e93-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67e93-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e93-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e93-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="67e93-131">See also</span></span>

- [<span data-ttu-id="67e93-132">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="67e93-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="67e93-133">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="67e93-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="67e93-134">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67e93-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="67e93-135">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67e93-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
