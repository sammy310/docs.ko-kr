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
ms.openlocfilehash: 37c306df76a796d6e0a2b7540ebd85c13865dfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682980"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="8843e-102">IHostSyncManager::CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="8843e-102">IHostSyncManager::CreateAutoEvent Method</span></span>

<span data-ttu-id="8843e-103">자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8843e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8843e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8843e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8843e-105">Parameters</span></span>  

 `ppEvent`  
 <span data-ttu-id="8843e-106">제한이 호스트에서 구현 하는 [IHostAutoEvent](ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8843e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8843e-107">Return Value</span></span>  
  
|<span data-ttu-id="8843e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8843e-108">HRESULT</span></span>|<span data-ttu-id="8843e-109">설명</span><span class="sxs-lookup"><span data-stu-id="8843e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8843e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8843e-110">S_OK</span></span>|<span data-ttu-id="8843e-111">`CreateAutoEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8843e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8843e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8843e-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8843e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8843e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8843e-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-115">The call timed out.</span></span>|  
|<span data-ttu-id="8843e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8843e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8843e-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8843e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8843e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8843e-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8843e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8843e-120">E_FAIL</span></span>|<span data-ttu-id="8843e-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8843e-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8843e-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8843e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8843e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8843e-125">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8843e-126">설명</span><span class="sxs-lookup"><span data-stu-id="8843e-126">Remarks</span></span>  

 <span data-ttu-id="8843e-127">`CreateAutoEvent` 대기 스레드를 해제 한 후 상태가 신호를 받지 않는 자동으로 변경 되는 자동 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="8843e-128">이 메서드는 `CreateEvent` `false` 매개 변수에 지정 된 값을 사용 하 여 Win32 함수를 미러링합니다. `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="8843e-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8843e-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8843e-129">Requirements</span></span>  

 <span data-ttu-id="8843e-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8843e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8843e-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8843e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8843e-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8843e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8843e-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8843e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8843e-134">참조</span><span class="sxs-lookup"><span data-stu-id="8843e-134">See also</span></span>

- [<span data-ttu-id="8843e-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8843e-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8843e-136">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8843e-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="8843e-137">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8843e-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="8843e-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8843e-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
