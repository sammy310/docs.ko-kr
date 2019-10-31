---
title: ICLRPolicyManager::SetTimeout 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 516ba1325404e757af8e38de239864b21b1640f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140754"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="a0b57-102">ICLRPolicyManager::SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="a0b57-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="a0b57-103">지정 된 작업에 대 한 시간 제한 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b57-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0b57-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b57-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0b57-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="a0b57-106">진행 시간 제한을 설정할 CLR (공용 언어 런타임) 작업을 나타내는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="a0b57-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="a0b57-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="a0b57-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="a0b57-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="a0b57-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="a0b57-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a0b57-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="a0b57-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a0b57-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="a0b57-112">진행 새 시간 제한 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="a0b57-113">값이 INFINITE 이면 작업이 시간 초과 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0b57-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="a0b57-114">Return Value</span></span>  
  
|<span data-ttu-id="a0b57-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0b57-115">HRESULT</span></span>|<span data-ttu-id="a0b57-116">설명</span><span class="sxs-lookup"><span data-stu-id="a0b57-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0b57-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0b57-117">S_OK</span></span>|<span data-ttu-id="a0b57-118">`SetTimeout` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="a0b57-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0b57-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0b57-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0b57-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0b57-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0b57-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-122">The call timed out.</span></span>|  
|<span data-ttu-id="a0b57-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0b57-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0b57-124">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0b57-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0b57-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0b57-126">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0b57-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0b57-127">E_FAIL</span></span>|<span data-ttu-id="a0b57-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0b57-129">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0b57-130">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0b57-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a0b57-131">E_INVALIDARG</span></span>|<span data-ttu-id="a0b57-132">지정 된 `operation`에 대 한 제한 시간을 설정할 수 없거나 `operation`에 대해 잘못 된 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0b57-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0b57-133">Requirements</span></span>  
 <span data-ttu-id="a0b57-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0b57-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b57-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a0b57-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0b57-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0b57-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0b57-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b57-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b57-138">참조</span><span class="sxs-lookup"><span data-stu-id="a0b57-138">See also</span></span>

- [<span data-ttu-id="a0b57-139">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="a0b57-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="a0b57-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0b57-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a0b57-141">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0b57-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
