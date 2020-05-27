---
title: IHostMemoryManager::RegisterMemoryNotificationCallback 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 0c20df85560f715e829fe02be599788854fcb0f1
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804472"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="d9e3c-102">IHostMemoryManager::RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="d9e3c-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="d9e3c-103">컴퓨터의 현재 메모리 로드를 CLR (공용 언어 런타임)에 알리기 위해 호스트에서 호출 하는 콜백 함수에 대 한 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9e3c-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9e3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9e3c-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d9e3c-106">진행 CLR에서 구현 하는 [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e3c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d9e3c-107">Return Value</span></span>  
  
|<span data-ttu-id="d9e3c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9e3c-108">HRESULT</span></span>|<span data-ttu-id="d9e3c-109">Description</span><span class="sxs-lookup"><span data-stu-id="d9e3c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9e3c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9e3c-110">S_OK</span></span>|<span data-ttu-id="d9e3c-111">`RegisterMemoryNotificationCallback`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="d9e3c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9e3c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9e3c-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9e3c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9e3c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9e3c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-115">The call timed out.</span></span>|  
|<span data-ttu-id="d9e3c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9e3c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9e3c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9e3c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9e3c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9e3c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9e3c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9e3c-120">E_FAIL</span></span>|<span data-ttu-id="d9e3c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9e3c-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9e3c-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9e3c-124">설명</span><span class="sxs-lookup"><span data-stu-id="d9e3c-124">Remarks</span></span>  
 <span data-ttu-id="d9e3c-125">인터페이스는 `ICLRMemoryNotificationCallback` 하나의 메서드 ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md))만 정의 하 고, `pCallback` 가 CLR에서 제공 하는 인스턴스에 대 한 포인터 이기 때문에 `ICLRMemoryNotificationCallback` 콜백 함수 자체에 대 한 등록은 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="d9e3c-126">호스트는 `OnMemoryNotification` 표준 Win32 함수를 사용 하는 대신를 호출 하 여 메모리 압력 상태를 보고 `CreateMemoryResourceNotification` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="d9e3c-127">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9e3c-128">에 대 한 호출은 `OnMemoryNotification` 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="d9e3c-129">항상 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e3c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9e3c-130">Requirements</span></span>  
 <span data-ttu-id="d9e3c-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e3c-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9e3c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9e3c-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e3c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e3c-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e3c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e3c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9e3c-135">See also</span></span>

- [<span data-ttu-id="d9e3c-136">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9e3c-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="d9e3c-137">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9e3c-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
