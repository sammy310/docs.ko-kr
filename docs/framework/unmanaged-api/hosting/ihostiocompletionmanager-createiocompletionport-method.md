---
title: IHostIoCompletionManager::CreateIoCompletionPort 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d50ea76c4d6448173002f720e1779233522ef499
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736519"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="6edc8-102">IHostIoCompletionManager::CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="6edc8-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="6edc8-103">호스트에 새 I/O 완료 포트를 만든 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6edc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6edc8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6edc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6edc8-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="6edc8-106">[out] 새로 만든된 I/O 완료 포트 또는 0 (영)을 포트를 만들 수 없는 경우에 대 한 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6edc8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6edc8-107">Return Value</span></span>  
  
|<span data-ttu-id="6edc8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6edc8-108">HRESULT</span></span>|<span data-ttu-id="6edc8-109">설명</span><span class="sxs-lookup"><span data-stu-id="6edc8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6edc8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6edc8-110">S_OK</span></span>|<span data-ttu-id="6edc8-111">`CreateIoCompletionPort` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="6edc8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6edc8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6edc8-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6edc8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6edc8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6edc8-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-115">The call timed out.</span></span>|  
|<span data-ttu-id="6edc8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6edc8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6edc8-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6edc8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6edc8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6edc8-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6edc8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6edc8-120">E_FAIL</span></span>|<span data-ttu-id="6edc8-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6edc8-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6edc8-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6edc8-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6edc8-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6edc8-125">요청된 된 리소스를 할당할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6edc8-126">설명</span><span class="sxs-lookup"><span data-stu-id="6edc8-126">Remarks</span></span>  
 <span data-ttu-id="6edc8-127">CLR에서는 `CreateIoCompletionPort` 만들도록 새 I/O 완료 포트를 호스트에 요청 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="6edc8-128">I/O 작업에 대 한 호출을 통해이 포트에 바인딩되기는 [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6edc8-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="6edc8-129">호스트 상태를 보고 다시 CLR에 호출한 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6edc8-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6edc8-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6edc8-130">Requirements</span></span>  
 <span data-ttu-id="6edc8-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6edc8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6edc8-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6edc8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6edc8-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6edc8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6edc8-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6edc8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6edc8-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="6edc8-135">See also</span></span>

- [<span data-ttu-id="6edc8-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6edc8-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="6edc8-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6edc8-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
