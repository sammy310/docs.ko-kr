---
title: IHostSyncManager::CreateAutoEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: b3778e12dd96d4f4653633252e13469601c4879d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139443"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="ce096-102">IHostSyncManager::CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="ce096-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="ce096-103">자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce096-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce096-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce096-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce096-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="ce096-106">제한이 호스트에서 구현 하는 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce096-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ce096-107">Return Value</span></span>  
  
|<span data-ttu-id="ce096-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce096-108">HRESULT</span></span>|<span data-ttu-id="ce096-109">설명</span><span class="sxs-lookup"><span data-stu-id="ce096-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce096-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce096-110">S_OK</span></span>|<span data-ttu-id="ce096-111">`CreateAutoEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ce096-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce096-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce096-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce096-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce096-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce096-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-115">The call timed out.</span></span>|  
|<span data-ttu-id="ce096-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce096-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce096-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce096-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce096-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce096-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce096-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce096-120">E_FAIL</span></span>|<span data-ttu-id="ce096-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce096-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce096-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce096-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce096-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce096-125">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce096-126">주의</span><span class="sxs-lookup"><span data-stu-id="ce096-126">Remarks</span></span>  
 <span data-ttu-id="ce096-127">`CreateAutoEvent`는 대기 스레드를 해제 한 후 상태가 자동으로 신호를 받지 않는 것으로 자동으로 변경 되는 자동 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="ce096-128">이 메서드는 `bManualReset` 매개 변수에 지정 된 `false` 값을 사용 하 여 Win32 `CreateEvent` 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce096-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce096-129">Requirements</span></span>  
 <span data-ttu-id="ce096-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce096-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce096-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ce096-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce096-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce096-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce096-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce096-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce096-134">참조</span><span class="sxs-lookup"><span data-stu-id="ce096-134">See also</span></span>

- [<span data-ttu-id="ce096-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce096-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ce096-136">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce096-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="ce096-137">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce096-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="ce096-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce096-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
