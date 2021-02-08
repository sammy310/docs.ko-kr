---
description: '자세히 알아보기: IHostSyncManager:: CreateAutoEvent 메서드'
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
ms.openlocfilehash: 69767f1e01ead93c874eecf01c3167a5dc0e4b82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784849"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="c2560-103">IHostSyncManager::CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="c2560-103">IHostSyncManager::CreateAutoEvent Method</span></span>

<span data-ttu-id="c2560-104">자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-104">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2560-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2560-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2560-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2560-106">Parameters</span></span>  

 `ppEvent`  
 <span data-ttu-id="c2560-107">제한이 호스트에서 구현 하는 [IHostAutoEvent](ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2560-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c2560-108">Return Value</span></span>  
  
|<span data-ttu-id="c2560-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2560-109">HRESULT</span></span>|<span data-ttu-id="c2560-110">설명</span><span class="sxs-lookup"><span data-stu-id="c2560-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2560-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2560-111">S_OK</span></span>|<span data-ttu-id="c2560-112">`CreateAutoEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-112">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c2560-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2560-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2560-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2560-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2560-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2560-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-116">The call timed out.</span></span>|  
|<span data-ttu-id="c2560-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2560-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2560-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2560-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2560-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2560-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2560-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2560-121">E_FAIL</span></span>|<span data-ttu-id="c2560-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2560-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2560-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c2560-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c2560-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c2560-126">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2560-127">설명</span><span class="sxs-lookup"><span data-stu-id="c2560-127">Remarks</span></span>  

 <span data-ttu-id="c2560-128">`CreateAutoEvent` 대기 스레드를 해제 한 후 상태가 신호를 받지 않는 자동으로 변경 되는 자동 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-128">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="c2560-129">이 메서드는 `CreateEvent` `false` 매개 변수에 지정 된 값을 사용 하 여 Win32 함수를 미러링합니다. `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="c2560-129">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2560-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2560-130">Requirements</span></span>  

 <span data-ttu-id="c2560-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2560-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2560-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c2560-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2560-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2560-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2560-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2560-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2560-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2560-135">See also</span></span>

- [<span data-ttu-id="c2560-136">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2560-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c2560-137">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2560-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="c2560-138">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2560-138">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="c2560-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2560-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
