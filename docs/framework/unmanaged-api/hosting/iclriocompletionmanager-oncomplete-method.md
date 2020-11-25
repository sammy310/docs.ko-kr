---
title: ICLRIoCompletionManager::OnComplete 메서드
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: 15119974acf74b49669e5ffbee59fbff9e5c84c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714109"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="ac404-102">ICLRIoCompletionManager::OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="ac404-102">ICLRIoCompletionManager::OnComplete Method</span></span>

<span data-ttu-id="ac404-103">[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac404-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac404-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac404-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac404-105">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="ac404-106">진행 바인딩 작업의 상태를 나타내는 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="ac404-107">S_OK 작업이 성공적으로 완료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="ac404-108">HOST_E_INTERRUPTED는 호출이 완료 되기 전에 종료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="ac404-109">E_FAIL은 알 수 없거나 복구할 수 없는 치명적인 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="ac404-110">진행 I/o 요청을 처리 하는 동안 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="ac404-111">진행 `OVERLAPPED` 메서드 호출에 전달 된 구조체에 대 한 포인터 `IHostIoCompletionManager::Bind` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac404-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac404-112">Return Value</span></span>  
  
|<span data-ttu-id="ac404-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac404-113">HRESULT</span></span>|<span data-ttu-id="ac404-114">설명</span><span class="sxs-lookup"><span data-stu-id="ac404-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac404-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac404-115">S_OK</span></span>|<span data-ttu-id="ac404-116">`OnComplete` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="ac404-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac404-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac404-118">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac404-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac404-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac404-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-120">The call timed out.</span></span>|  
|<span data-ttu-id="ac404-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac404-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac404-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac404-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac404-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac404-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac404-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac404-125">E_FAIL</span></span>|<span data-ttu-id="ac404-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac404-127">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac404-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac404-129">설명</span><span class="sxs-lookup"><span data-stu-id="ac404-129">Remarks</span></span>  

 <span data-ttu-id="ac404-130">호스트에서 i/o 완료 추상화를 구현 하는 경우 CLR은 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)의 메서드를 사용 하 여 호스트를 통해 i/o 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="ac404-131">그런 다음 호스트는 메서드를 호출 `OnComplete` 하 여 이러한 요청의 결과를 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac404-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac404-132">Requirements</span></span>  

 <span data-ttu-id="ac404-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac404-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac404-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ac404-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac404-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac404-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac404-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac404-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac404-137">참조</span><span class="sxs-lookup"><span data-stu-id="ac404-137">See also</span></span>

- [<span data-ttu-id="ac404-138">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac404-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ac404-139">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac404-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="ac404-140">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac404-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
