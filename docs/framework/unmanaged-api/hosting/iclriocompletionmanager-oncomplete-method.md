---
description: '자세한 정보: IclrioOnComplete Manager:: 메서드'
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
ms.openlocfilehash: d54b189debdfc2959676b53fd3fb51b2c10dce17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789888"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="c2b6f-103">ICLRIoCompletionManager::OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="c2b6f-103">ICLRIoCompletionManager::OnComplete Method</span></span>

<span data-ttu-id="c2b6f-104">[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-104">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b6f-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2b6f-105">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2b6f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2b6f-106">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="c2b6f-107">진행 바인딩 작업의 상태를 나타내는 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-107">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="c2b6f-108">S_OK 작업이 성공적으로 완료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-108">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="c2b6f-109">HOST_E_INTERRUPTED는 호출이 완료 되기 전에 종료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-109">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="c2b6f-110">E_FAIL은 알 수 없거나 복구할 수 없는 치명적인 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-110">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="c2b6f-111">진행 I/o 요청을 처리 하는 동안 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-111">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="c2b6f-112">진행 `OVERLAPPED` 메서드 호출에 전달 된 구조체에 대 한 포인터 `IHostIoCompletionManager::Bind` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-112">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2b6f-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="c2b6f-113">Return Value</span></span>  
  
|<span data-ttu-id="c2b6f-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2b6f-114">HRESULT</span></span>|<span data-ttu-id="c2b6f-115">설명</span><span class="sxs-lookup"><span data-stu-id="c2b6f-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2b6f-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2b6f-116">S_OK</span></span>|<span data-ttu-id="c2b6f-117">`OnComplete` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-117">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="c2b6f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2b6f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2b6f-119">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2b6f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2b6f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2b6f-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-121">The call timed out.</span></span>|  
|<span data-ttu-id="c2b6f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2b6f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2b6f-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2b6f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2b6f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2b6f-125">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2b6f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2b6f-126">E_FAIL</span></span>|<span data-ttu-id="c2b6f-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2b6f-128">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2b6f-129">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2b6f-130">설명</span><span class="sxs-lookup"><span data-stu-id="c2b6f-130">Remarks</span></span>  

 <span data-ttu-id="c2b6f-131">호스트에서 i/o 완료 추상화를 구현 하는 경우 CLR은 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)의 메서드를 사용 하 여 호스트를 통해 i/o 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-131">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="c2b6f-132">그런 다음 호스트는 메서드를 호출 `OnComplete` 하 여 이러한 요청의 결과를 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-132">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b6f-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2b6f-133">Requirements</span></span>  

 <span data-ttu-id="c2b6f-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b6f-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c2b6f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2b6f-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b6f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2b6f-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b6f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b6f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2b6f-138">See also</span></span>

- [<span data-ttu-id="c2b6f-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2b6f-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c2b6f-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2b6f-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="c2b6f-141">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2b6f-141">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
