---
title: IHostTaskManager::SetUILocale 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 173eda2882ca9172c840d0d4fa65ef972fd779da
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749331"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="a82f2-102">IHostTaskManager::SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="a82f2-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="a82f2-103">CLR (공용 언어 런타임) 사용자 인터페이스 (UI) 로캘 또는 문화권을 현재 실행 중인 작업 변경에 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a82f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a82f2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a82f2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a82f2-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="a82f2-106">[in] 새로 할당 된 지리적 culture 및 언어에 매핑하는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a82f2-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a82f2-107">Return Value</span></span>  
  
|<span data-ttu-id="a82f2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a82f2-108">HRESULT</span></span>|<span data-ttu-id="a82f2-109">설명</span><span class="sxs-lookup"><span data-stu-id="a82f2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a82f2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a82f2-110">S_OK</span></span>|<span data-ttu-id="a82f2-111">`SetUILocale` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="a82f2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a82f2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a82f2-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a82f2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a82f2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a82f2-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-115">The call timed out.</span></span>|  
|<span data-ttu-id="a82f2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a82f2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a82f2-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a82f2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a82f2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a82f2-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a82f2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a82f2-120">E_FAIL</span></span>|<span data-ttu-id="a82f2-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a82f2-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a82f2-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a82f2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a82f2-124">E_NOTIMPL</span></span>|<span data-ttu-id="a82f2-125">호스트는 UI 문화권을 변경 하려면 관리 되는 사용자 코드를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a82f2-126">설명</span><span class="sxs-lookup"><span data-stu-id="a82f2-126">Remarks</span></span>  
 <span data-ttu-id="a82f2-127">런타임 호출 `SetUILocale` 때 값을 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> 속성은 관리 코드에 의해 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="a82f2-128">이 메서드는 호스트가 로캘의 동기화를 위한 메커니즘을 가질 수 있습니다 실행 하는 데 사용할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="a82f2-129">호스트의 UI 로캘 관리 코드에서 변경할 수 없도록 또는 로캘 동기화 하는 메커니즘을 구현 하지 않는 경우이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f2-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a82f2-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a82f2-130">Requirements</span></span>  
 <span data-ttu-id="a82f2-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a82f2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82f2-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a82f2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a82f2-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a82f2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a82f2-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82f2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82f2-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a82f2-135">See also</span></span>

- [<span data-ttu-id="a82f2-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82f2-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a82f2-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82f2-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a82f2-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82f2-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a82f2-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82f2-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a82f2-140">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="a82f2-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
