---
description: '자세히 알아보기: IHostSyncManager:: CreateRWLockWriterEvent 메서드'
title: IHostSyncManager::CreateRWLockWriterEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 509f18ff49966e5da3a25e39258d33caf69249a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784758"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="a66a1-103">IHostSyncManager::CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="a66a1-103">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="a66a1-104">작성기 잠금 구현에 대 한 자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-104">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="a66a1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a66a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a66a1-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="a66a1-107">진행 자동 다시 설정 이벤트와 연결할 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-107">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="a66a1-108">제한이 [IHostAutoEvent](ihostautoevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-108">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a66a1-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="a66a1-109">Return Value</span></span>  
  
|<span data-ttu-id="a66a1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a66a1-110">HRESULT</span></span>|<span data-ttu-id="a66a1-111">설명</span><span class="sxs-lookup"><span data-stu-id="a66a1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a66a1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a66a1-112">S_OK</span></span>|<span data-ttu-id="a66a1-113">`CreateRWLockWriterEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-113">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a66a1-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a66a1-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a66a1-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a66a1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a66a1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a66a1-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-117">The call timed out.</span></span>|  
|<span data-ttu-id="a66a1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a66a1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a66a1-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a66a1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a66a1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a66a1-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a66a1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a66a1-122">E_FAIL</span></span>|<span data-ttu-id="a66a1-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a66a1-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a66a1-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a66a1-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a66a1-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a66a1-127">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a66a1-128">설명</span><span class="sxs-lookup"><span data-stu-id="a66a1-128">Remarks</span></span>  

 <span data-ttu-id="a66a1-129">CLR은 메서드를 호출 `CreateRWLockWriterEvent` 하 여 `IHostAutoEvent` 작성기 잠금을 구현 하는 데 사용할 인스턴스에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-129">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="a66a1-130">호스트는 지정 된 쿠키를 사용 하 여 [ICLRSyncManager](iclrsyncmanager-interface.md) 인터페이스의 반복 메서드를 호출 하 여 잠금을 기다리는 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-130">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a66a1-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a66a1-131">Requirements</span></span>  

 <span data-ttu-id="a66a1-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a66a1-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66a1-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a66a1-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a66a1-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a66a1-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a66a1-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a66a1-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66a1-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a66a1-136">See also</span></span>

- [<span data-ttu-id="a66a1-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a66a1-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a66a1-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a66a1-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="a66a1-139">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a66a1-139">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="a66a1-140">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a66a1-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
