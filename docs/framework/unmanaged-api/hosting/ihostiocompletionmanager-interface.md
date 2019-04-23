---
title: IHostIoCompletionManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197271"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="3da23-102">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da23-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="3da23-103">CLR (공용 언어 런타임) 호스트에서 제공 하는 I/O 완료 포트를 사용 하 여 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3da23-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-104">Methods</span></span>  
  
|<span data-ttu-id="3da23-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-105">Method</span></span>|<span data-ttu-id="3da23-106">설명</span><span class="sxs-lookup"><span data-stu-id="3da23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3da23-107">Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="3da23-108">I/O 완료 포트에 대 한 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="3da23-109">CloseIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="3da23-110">에 대 한 이전 호출을 통해 생성 된 포트를 닫습니다 `CreateIoCompletionPort`합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="3da23-111">CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="3da23-112">호스트에 새 I/O 완료 포트를 만든 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="3da23-113">GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="3da23-114">현재 요청을 처리 하 고 있지는 I/O 완료 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="3da23-115">GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="3da23-116">호스트에서 I/O 요청에 추가 하려는 모든 사용자 지정 데이터의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="3da23-117">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="3da23-118">I/O 요청을 처리 하는 호스트를 할당할 수 있는 스레드의 최대 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="3da23-119">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="3da23-120">I/O 요청을 처리 하는 호스트를 제공 하는 스레드의 최소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="3da23-121">InitializeHostOverlapped 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="3da23-122">I/O 요청에 대 한 사용자 지정 데이터를 초기화할 수 있는 호스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="3da23-123">SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="3da23-124">호스트에 대 한 인터페이스 포인터에 제공을 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) 인스턴스는 CLR에서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="3da23-125">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="3da23-126">I/o 호스트를 할당 하는 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="3da23-127">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3da23-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="3da23-128">I/O 완료 될 때까지 호스트를 할당 해야 하는 스레드의 최소 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da23-129">설명</span><span class="sxs-lookup"><span data-stu-id="3da23-129">Remarks</span></span>  
 <span data-ttu-id="3da23-130">`IHostIoCompletionManager` 에 해당 하는 `ICLRIoCompletionManager` CLR에 의해 구현 되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="3da23-131">메서드를 호출 하는 CLR `IHostIoCompletionManager` 처리를 호스트가 제공 및 호스트의 메서드를 호출 하는 포트를 바인딩할 `ICLRIoCompletionManager` I/O 요청의 완료를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da23-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da23-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3da23-132">Requirements</span></span>  
 <span data-ttu-id="3da23-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3da23-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da23-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3da23-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3da23-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3da23-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3da23-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da23-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da23-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="3da23-137">See also</span></span>

- [<span data-ttu-id="3da23-138">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da23-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
