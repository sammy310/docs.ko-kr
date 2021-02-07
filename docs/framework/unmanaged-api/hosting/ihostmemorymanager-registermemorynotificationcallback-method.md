---
description: '자세히 알아보기: IHostMemoryManager:: RegisterMemoryNotificationCallback 메서드'
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
ms.openlocfilehash: 26a7468aba4f473eebff78a8c67eeb5b3e866e9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707766"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="528f2-103">IHostMemoryManager::RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="528f2-103">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>

<span data-ttu-id="528f2-104">컴퓨터의 현재 메모리 로드를 CLR (공용 언어 런타임)에 알리기 위해 호스트에서 호출 하는 콜백 함수에 대 한 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-104">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528f2-105">구문</span><span class="sxs-lookup"><span data-stu-id="528f2-105">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="528f2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="528f2-106">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="528f2-107">진행 CLR에서 구현 하는 [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-107">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="528f2-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="528f2-108">Return Value</span></span>  
  
|<span data-ttu-id="528f2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="528f2-109">HRESULT</span></span>|<span data-ttu-id="528f2-110">설명</span><span class="sxs-lookup"><span data-stu-id="528f2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="528f2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="528f2-111">S_OK</span></span>|<span data-ttu-id="528f2-112">`RegisterMemoryNotificationCallback` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-112">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="528f2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="528f2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="528f2-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="528f2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="528f2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="528f2-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-116">The call timed out.</span></span>|  
|<span data-ttu-id="528f2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="528f2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="528f2-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="528f2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="528f2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="528f2-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="528f2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="528f2-121">E_FAIL</span></span>|<span data-ttu-id="528f2-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="528f2-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="528f2-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="528f2-125">설명</span><span class="sxs-lookup"><span data-stu-id="528f2-125">Remarks</span></span>  

 <span data-ttu-id="528f2-126">인터페이스는 `ICLRMemoryNotificationCallback` 하나의 메서드 ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md))만 정의 하 고, `pCallback` 가 CLR에서 제공 하는 인스턴스에 대 한 포인터 이기 때문에 `ICLRMemoryNotificationCallback` 콜백 함수 자체에 대 한 등록은 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-126">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="528f2-127">호스트는 `OnMemoryNotification` 표준 Win32 함수를 사용 하는 대신를 호출 하 여 메모리 압력 상태를 보고 `CreateMemoryResourceNotification` 합니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-127">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="528f2-128">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="528f2-128">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="528f2-129">에 대 한 호출은 `OnMemoryNotification` 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-129">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="528f2-130">항상 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-130">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528f2-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="528f2-131">Requirements</span></span>  

 <span data-ttu-id="528f2-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="528f2-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="528f2-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="528f2-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="528f2-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="528f2-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="528f2-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="528f2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528f2-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="528f2-136">See also</span></span>

- [<span data-ttu-id="528f2-137">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="528f2-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="528f2-138">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="528f2-138">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
