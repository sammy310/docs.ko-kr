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
ms.openlocfilehash: 90675d9be71342efa903767abbf63102b40a2c35
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804684"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="ffc73-102">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffc73-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="ffc73-103">CLR (공용 언어 런타임)이 호스트에서 제공 하는 i/o 완료 포트와 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffc73-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-104">Methods</span></span>  
  
|<span data-ttu-id="ffc73-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-105">Method</span></span>|<span data-ttu-id="ffc73-106">Description</span><span class="sxs-lookup"><span data-stu-id="ffc73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffc73-107">Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-107">Bind Method</span></span>](ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="ffc73-108">I/o 완료 포트에 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="ffc73-109">CloseIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-109">CloseIoCompletionPort Method</span></span>](ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="ffc73-110">에 대 한 이전 호출을 통해 만든 포트를 닫습니다 `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="ffc73-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="ffc73-111">CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-111">CreateIoCompletionPort Method</span></span>](ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="ffc73-112">호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="ffc73-113">GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-113">GetAvailableThreads Method</span></span>](ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="ffc73-114">현재 요청을 처리 하 고 있지 않은 i/o 완료 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="ffc73-115">GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-115">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="ffc73-116">호스트가 i/o 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="ffc73-117">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-117">GetMaxThreads Method</span></span>](ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="ffc73-118">호스트가 i/o 요청을 처리 하기 위해 할당할 수 있는 최대 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="ffc73-119">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-119">GetMinThreads Method</span></span>](ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="ffc73-120">호스트가 서비스 i/o 요청에 제공 하는 최소 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="ffc73-121">InitializeHostOverlapped 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-121">InitializeHostOverlapped Method</span></span>](ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="ffc73-122">호스트에 i/o 요청에 대 한 사용자 지정 데이터를 초기화할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="ffc73-123">SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="ffc73-124">호스트에 CLR에서 구현 하는 [Iclriocompletionmanager](iclriocompletionmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="ffc73-125">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-125">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="ffc73-126">호스트에서 i/o 요청을 처리 하는 데 많은 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="ffc73-127">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ffc73-127">SetMinThreads Method</span></span>](ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="ffc73-128">호스트에서 i/o 완료에 대해 할당할 최소 스레드 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffc73-129">설명</span><span class="sxs-lookup"><span data-stu-id="ffc73-129">Remarks</span></span>  
 <span data-ttu-id="ffc73-130">`IHostIoCompletionManager``ICLRIoCompletionManager`는 CLR에서 구현 하는 인터페이스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="ffc73-131">CLR은의 메서드를 호출 `IHostIoCompletionManager` 하 여 호스트에서 제공 하는 포트에 핸들을 바인딩하고 호스트는의 메서드를 호출 하 여 `ICLRIoCompletionManager` i/o 요청 완료를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc73-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffc73-132">Requirements</span></span>  
 <span data-ttu-id="ffc73-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc73-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc73-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ffc73-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffc73-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc73-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffc73-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc73-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc73-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffc73-137">See also</span></span>

- [<span data-ttu-id="ffc73-138">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffc73-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
