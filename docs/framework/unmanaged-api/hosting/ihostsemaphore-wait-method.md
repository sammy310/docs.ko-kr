---
description: '자세히 알아보기: IHostSemaphore:: Wait 메서드'
title: IHostSemaphore::Wait 메서드
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: 386f9806d6457f30d13e18e7d0d1ab16aafb84ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728446"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="b6eca-103">IHostSemaphore::Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="b6eca-103">IHostSemaphore::Wait Method</span></span>

<span data-ttu-id="b6eca-104">현재 [IHostSemaphore](ihostsemaphore-interface.md) 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-104">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6eca-105">구문</span><span class="sxs-lookup"><span data-stu-id="b6eca-105">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6eca-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6eca-106">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="b6eca-107">진행 현재 인스턴스를 소유 하 고 있지 않은 경우를 반환 하기 전에 대기 하는 시간 (밀리초)입니다 `IHostSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="b6eca-107">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="b6eca-108">진행 이 작업이 차단 되는 경우 호스트에서 수행할 작업을 지정 하는 [WAIT_OPTION](wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6eca-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="b6eca-109">Return Value</span></span>  
  
|<span data-ttu-id="b6eca-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6eca-110">HRESULT</span></span>|<span data-ttu-id="b6eca-111">설명</span><span class="sxs-lookup"><span data-stu-id="b6eca-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6eca-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6eca-112">S_OK</span></span>|<span data-ttu-id="b6eca-113">`Wait` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-113">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="b6eca-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6eca-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6eca-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6eca-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6eca-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6eca-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-117">The call timed out.</span></span>|  
|<span data-ttu-id="b6eca-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6eca-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6eca-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6eca-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6eca-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6eca-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6eca-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6eca-122">E_FAIL</span></span>|<span data-ttu-id="b6eca-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6eca-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6eca-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b6eca-126">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="b6eca-126">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="b6eca-127">호스트가 대기 간격 중에 교착 상태를 감지 하 여 교착 상태에서 현재 인스턴스를 선택 했습니다 `IHostSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="b6eca-127">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6eca-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6eca-128">Requirements</span></span>  

 <span data-ttu-id="b6eca-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6eca-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6eca-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b6eca-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6eca-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6eca-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6eca-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6eca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6eca-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6eca-133">See also</span></span>

- [<span data-ttu-id="b6eca-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6eca-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b6eca-135">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6eca-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="b6eca-136">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6eca-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="b6eca-137">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6eca-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="b6eca-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6eca-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
