---
description: '자세히 알아보기: IHostSyncManager 인터페이스'
title: IHostSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: c3bd2928315567605d320c772de8ff824ad3cd09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784732"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="2ebeb-103">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ebeb-103">IHostSyncManager Interface</span></span>

<span data-ttu-id="2ebeb-104">Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 CLR (공용 언어 런타임)에서 동기화 기본 형식을 만들 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-104">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ebeb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-105">Methods</span></span>  
  
|<span data-ttu-id="2ebeb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-106">Method</span></span>|<span data-ttu-id="2ebeb-107">설명</span><span class="sxs-lookup"><span data-stu-id="2ebeb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ebeb-108">CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-108">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="2ebeb-109">자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-109">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="2ebeb-110">CreateCrst 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-110">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="2ebeb-111">동기화에 대 한 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-111">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="2ebeb-112">CreateCrstWithSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-112">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="2ebeb-113">동기화에 대 한 회전 수를 사용 하 여 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-113">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="2ebeb-114">CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-114">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="2ebeb-115">수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-115">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="2ebeb-116">CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-116">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="2ebeb-117">모니터링 되는 자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-117">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="2ebeb-118">CreateRWLockReaderEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-118">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="2ebeb-119">판독기 잠금 구현에 대 한 수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-119">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="2ebeb-120">CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-120">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="2ebeb-121">작성기 잠금 구현에 대 한 자동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-121">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="2ebeb-122">CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-122">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="2ebeb-123">대기 이벤트에 대 한 세마포에 사용할 CLR에 대 한 [IHostSemaphore](ihostsemaphore-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-123">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="2ebeb-124">SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="2ebeb-124">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="2ebeb-125">현재 인스턴스와 연결할 [ICLRSyncManager](iclrsyncmanager-interface.md) 인스턴스를 설정 합니다 `IHostSyncManager` .</span><span class="sxs-lookup"><span data-stu-id="2ebeb-125">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ebeb-126">설명</span><span class="sxs-lookup"><span data-stu-id="2ebeb-126">Remarks</span></span>  

 <span data-ttu-id="2ebeb-127">CLR은 IID_IHostSyncManager의를 사용 하 여 `IHostSyncManager` [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) 메서드를 호출 하 여 호스트의 구현을 검색 합니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="2ebeb-127">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebeb-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ebeb-128">Requirements</span></span>  

 <span data-ttu-id="2ebeb-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebeb-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2ebeb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ebeb-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ebeb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ebeb-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebeb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebeb-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ebeb-133">See also</span></span>

- [<span data-ttu-id="2ebeb-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ebeb-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2ebeb-135">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ebeb-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
