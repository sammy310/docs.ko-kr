---
title: IHostTaskManager::SetLocale 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79d4c5b2b2bbe821ff546324fd3af04cb3472e4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149827"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="aa4a6-102">IHostTaskManager::SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="aa4a6-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="aa4a6-103">로캘 또는 문화권을 현재 실행 중인 작업의 CLR (공용 언어 런타임)가 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa4a6-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa4a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa4a6-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="aa4a6-106">[in] 새로 할당 된 지리적 culture 및 언어에 매핑하는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa4a6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa4a6-107">Return Value</span></span>  
  
|<span data-ttu-id="aa4a6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa4a6-108">HRESULT</span></span>|<span data-ttu-id="aa4a6-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa4a6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa4a6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa4a6-110">S_OK</span></span>|`SetLocale` <span data-ttu-id="aa4a6-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-111">returned successfully.</span></span>|  
|<span data-ttu-id="aa4a6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa4a6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa4a6-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa4a6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa4a6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa4a6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-115">The call timed out.</span></span>|  
|<span data-ttu-id="aa4a6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa4a6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa4a6-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa4a6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa4a6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa4a6-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa4a6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa4a6-120">E_FAIL</span></span>|<span data-ttu-id="aa4a6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa4a6-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa4a6-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="aa4a6-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="aa4a6-124">E_NOTIMPL</span></span>|<span data-ttu-id="aa4a6-125">호스트에서 관리 되는 사용자 로캘을 수정 하는 코드를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa4a6-126">설명</span><span class="sxs-lookup"><span data-stu-id="aa4a6-126">Remarks</span></span>  
 <span data-ttu-id="aa4a6-127">런타임 호출 `SetLocale` 때 값을 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 속성은 관리 코드에 의해 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="aa4a6-128">이 메서드는 호스트가 로캘의 동기화를 위한 메커니즘을 가질 수 있습니다 실행 하는 데 사용할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="aa4a6-129">호스트 관리 코드에서 변경 하는 로캘을 허용 하지 않거나 로캘을 동기화 메커니즘을 구현 하지 않습니다, 경우 E_NOTIMPL이 메서드에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa4a6-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa4a6-130">Requirements</span></span>  
 <span data-ttu-id="aa4a6-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa4a6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa4a6-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa4a6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa4a6-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="aa4a6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="aa4a6-134">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="aa4a6-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa4a6-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa4a6-135">See also</span></span>

- [<span data-ttu-id="aa4a6-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa4a6-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="aa4a6-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa4a6-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="aa4a6-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa4a6-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="aa4a6-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa4a6-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="aa4a6-140">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="aa4a6-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
