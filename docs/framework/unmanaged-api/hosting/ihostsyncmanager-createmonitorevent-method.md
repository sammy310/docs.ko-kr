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
ms.openlocfilehash: c0f7e1fd6bf4c9386300b11477df85e87899fc67
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803315"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="e6056-102">IHostSyncManager::CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="e6056-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="e6056-103">모니터링 되는 자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6056-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6056-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6056-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e6056-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="e6056-106">진행 이벤트 개체와 연결할 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="e6056-107">제한이 [IHostAutoEvent](ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6056-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="e6056-108">Return Value</span></span>  
  
|<span data-ttu-id="e6056-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6056-109">HRESULT</span></span>|<span data-ttu-id="e6056-110">Description</span><span class="sxs-lookup"><span data-stu-id="e6056-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6056-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6056-111">S_OK</span></span>|<span data-ttu-id="e6056-112">`CreateMonitorEvent`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="e6056-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6056-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6056-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6056-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6056-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6056-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6056-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6056-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6056-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6056-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6056-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6056-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6056-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6056-121">E_FAIL</span></span>|<span data-ttu-id="e6056-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6056-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6056-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e6056-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e6056-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e6056-126">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6056-127">설명</span><span class="sxs-lookup"><span data-stu-id="e6056-127">Remarks</span></span>  
 <span data-ttu-id="e6056-128">`CreateMonitorEvent``IHostAutoEvent`CLR이 관리 되는 형식의 구현에서 사용 하는를 반환 합니다 <xref:System.Threading.Monitor?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e6056-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="e6056-129">이 메서드는 `CreateEvent` `false` 매개 변수에 지정 된 값을 사용 하 여 Win32 함수를 미러링합니다 `bManualReset` .</span><span class="sxs-lookup"><span data-stu-id="e6056-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="e6056-130">호스트는 쿠키를 사용 하 여 [ICLRSyncManager:: GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) 메서드를 호출 하 여 모니터에서 대기 중인 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6056-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6056-131">Requirements</span></span>  
 <span data-ttu-id="e6056-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6056-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6056-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e6056-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6056-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6056-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6056-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6056-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6056-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6056-136">See also</span></span>

- [<span data-ttu-id="e6056-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6056-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e6056-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6056-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e6056-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6056-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
