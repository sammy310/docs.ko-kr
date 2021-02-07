---
description: '자세히 알아보기: IHostThreadPoolManager 인터페이스'
title: IHostThreadPoolManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 0361b7a08f781a8748e43959f65ce0e9f21bbac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728407"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="456b7-103">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="456b7-103">IHostThreadPoolManager Interface</span></span>

<span data-ttu-id="456b7-104">CLR (공용 언어 런타임)이 스레드 풀을 구성 하 고 작업 항목을 스레드 풀에 대기 시킬 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-104">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="456b7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-105">Methods</span></span>  
  
|<span data-ttu-id="456b7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-106">Method</span></span>|<span data-ttu-id="456b7-107">설명</span><span class="sxs-lookup"><span data-stu-id="456b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="456b7-108">GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-108">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="456b7-109">현재 작업 항목을 처리 하 고 있지 않은 스레드 풀의 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-109">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="456b7-110">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-110">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="456b7-111">호스트가 스레드 풀에서 동시에 유지 관리 하는 최대 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-111">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="456b7-112">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-112">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="456b7-113">호스트에서 요청을 미리 대비 하 여 유지 하는 유휴 스레드의 최소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-113">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="456b7-114">QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-114">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="456b7-115">함수를 실행 하기 위해 큐에 대기 시키고 함수에서 사용할 데이터가 포함 된 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-115">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="456b7-116">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-116">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="456b7-117">호스트가 스레드 풀에서 유지 관리할 수 있는 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-117">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="456b7-118">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="456b7-118">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="456b7-119">호스트에서 요청을 예측 하 여 유지 해야 하는 최소 유휴 스레드 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-119">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="456b7-120">설명</span><span class="sxs-lookup"><span data-stu-id="456b7-120">Remarks</span></span>  

 <span data-ttu-id="456b7-121">호스트는 및 메서드에 대 한 호출에 지정 된 값을 사용 하 여 스레드 풀을 구성할 필요가 없습니다 `SetMaxThreads` `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="456b7-121">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="456b7-122">이 경우 호스트는 이러한 메서드에서 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-122">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="456b7-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="456b7-123">Requirements</span></span>  

 <span data-ttu-id="456b7-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="456b7-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="456b7-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="456b7-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="456b7-126">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456b7-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="456b7-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="456b7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456b7-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="456b7-128">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="456b7-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="456b7-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
