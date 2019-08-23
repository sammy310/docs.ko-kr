---
title: ICLRMemoryNotificationCallback::OnMemoryNotification 메서드
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949700"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="792e1-102">ICLRMemoryNotificationCallback::OnMemoryNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="792e1-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="792e1-103">컴퓨터의 메모리 로드를 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="792e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="792e1-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="792e1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="792e1-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="792e1-106">진행 컴퓨터에 현재 발생 하 고 있는 메모리 압력을 나타내는 [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="792e1-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="792e1-107">Return Value</span></span>  
  
|<span data-ttu-id="792e1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="792e1-108">HRESULT</span></span>|<span data-ttu-id="792e1-109">Description</span><span class="sxs-lookup"><span data-stu-id="792e1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="792e1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="792e1-110">S_OK</span></span>|<span data-ttu-id="792e1-111">`OnMemoryNotification`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="792e1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="792e1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="792e1-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="792e1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="792e1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="792e1-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-115">The call timed out.</span></span>|  
|<span data-ttu-id="792e1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="792e1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="792e1-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="792e1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="792e1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="792e1-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="792e1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="792e1-120">E_FAIL</span></span>|<span data-ttu-id="792e1-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="792e1-122">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="792e1-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="792e1-124">설명</span><span class="sxs-lookup"><span data-stu-id="792e1-124">Remarks</span></span>  
 <span data-ttu-id="792e1-125">CLR은 `OnMemoryNotification` [IHostMemoryManager:: registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) 메서드를 호출 하 여에 콜백을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="792e1-126">런타임은 콜백에서 반환 된 정보를 사용 하 여 호스트에서 메모리 리소스가 부족 하다 고 보고할 때 추가 메모리를 확보 합니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="792e1-127">에 대 `OnMemoryNotification` 한 호출은 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="792e1-128">항상 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="792e1-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="792e1-129">Requirements</span></span>  
 <span data-ttu-id="792e1-130">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="792e1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="792e1-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="792e1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="792e1-132">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="792e1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="792e1-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="792e1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792e1-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="792e1-134">See also</span></span>

- [<span data-ttu-id="792e1-135">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="792e1-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="792e1-136">RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="792e1-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="792e1-137">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="792e1-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
