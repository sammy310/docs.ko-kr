---
title: ICLRControl::GetCLRManager 메서드
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97d75eb5fab396530a6f48314e96c8d47d06439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656493"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="15101-102">ICLRControl::GetCLRManager 메서드</span><span class="sxs-lookup"><span data-stu-id="15101-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="15101-103">호스트의 CLR (공용 언어 런타임)을 구성 하 여 관리자 형식의 모든 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15101-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15101-104">구문</span><span class="sxs-lookup"><span data-stu-id="15101-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15101-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15101-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="15101-106">[in] `IID` manager 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="15101-107">다음 `IID` 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15101-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="15101-108">IID_ICLRDebugManager: 형식임 `ppObject` 형식이 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-109">IID_ICLRErrorReportingManager: 형식임 `ppObject` 형식이 [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-110">IID_ICLRGCManager: 형식임 `ppObject` 형식이 [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-111">IID_ICLRHostProtectionManager: 형식임 `ppObject` 형식이 [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-112">IID_ICLROnEventManager: 형식임 `ppObject` 형식이 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-113">IID_ICLRPolicyManager: 형식임 `ppObject` 형식이 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="15101-114">IID_ICLRTaskManager: 형식임 `ppObject` 형식이 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="15101-115">[out] 잘못 된 관리자 유형이 요청 된 경우 null을 요청한 관리자에 대 한 인터페이스 포인터.</span><span class="sxs-lookup"><span data-stu-id="15101-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15101-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="15101-116">Return Value</span></span>  
  
|<span data-ttu-id="15101-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15101-117">HRESULT</span></span>|<span data-ttu-id="15101-118">설명</span><span class="sxs-lookup"><span data-stu-id="15101-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15101-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="15101-119">S_OK</span></span>|<span data-ttu-id="15101-120">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="15101-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15101-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15101-122">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15101-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15101-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15101-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-124">The call timed out.</span></span>|  
|<span data-ttu-id="15101-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15101-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15101-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15101-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15101-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15101-128">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15101-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15101-129">E_FAIL</span></span>|<span data-ttu-id="15101-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15101-131">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15101-132">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15101-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15101-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="15101-133">E_NOINTERFACE</span></span>|<span data-ttu-id="15101-134">인터페이스 형식이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15101-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15101-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15101-135">Requirements</span></span>  
 <span data-ttu-id="15101-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15101-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15101-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15101-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15101-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="15101-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15101-139">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15101-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15101-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="15101-140">See also</span></span>

- [<span data-ttu-id="15101-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15101-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="15101-142">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15101-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
