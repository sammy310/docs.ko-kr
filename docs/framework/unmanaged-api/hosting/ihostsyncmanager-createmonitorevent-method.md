---
title: IHostSyncManager::CreateMonitorEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192024"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="dbb30-102">IHostSyncManager::CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="dbb30-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="dbb30-103">모니터링 되는 자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb30-104">구문</span><span class="sxs-lookup"><span data-stu-id="dbb30-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb30-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dbb30-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="dbb30-106">진행 이벤트 개체와 연결할 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="dbb30-107">제한이 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbb30-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="dbb30-108">Return Value</span></span>  
  
|<span data-ttu-id="dbb30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbb30-109">HRESULT</span></span>|<span data-ttu-id="dbb30-110">설명</span><span class="sxs-lookup"><span data-stu-id="dbb30-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbb30-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbb30-111">S_OK</span></span>|<span data-ttu-id="dbb30-112">`CreateMonitorEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="dbb30-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbb30-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbb30-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbb30-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbb30-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbb30-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-116">The call timed out.</span></span>|  
|<span data-ttu-id="dbb30-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbb30-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbb30-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbb30-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbb30-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbb30-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbb30-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbb30-121">E_FAIL</span></span>|<span data-ttu-id="dbb30-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbb30-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbb30-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dbb30-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dbb30-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dbb30-126">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbb30-127">주의</span><span class="sxs-lookup"><span data-stu-id="dbb30-127">Remarks</span></span>  
 <span data-ttu-id="dbb30-128">`CreateMonitorEvent`는 CLR이 관리 되는 <xref:System.Threading.Monitor?displayProperty=nameWithType> 형식의 구현에서 사용 하는 `IHostAutoEvent` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="dbb30-129">이 메서드는 `bManualReset` 매개 변수에 지정 된 `false` 값을 사용 하 여 Win32 `CreateEvent` 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="dbb30-130">호스트는 쿠키를 사용 하 여 [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) 메서드를 호출 하 여 모니터에서 대기 중인 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb30-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbb30-131">Requirements</span></span>  
 <span data-ttu-id="dbb30-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbb30-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb30-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dbb30-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbb30-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb30-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbb30-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb30-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb30-136">참조</span><span class="sxs-lookup"><span data-stu-id="dbb30-136">See also</span></span>

- [<span data-ttu-id="dbb30-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbb30-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dbb30-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbb30-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="dbb30-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbb30-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
