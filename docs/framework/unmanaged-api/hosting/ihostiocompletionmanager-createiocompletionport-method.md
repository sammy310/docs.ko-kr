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
ms.openlocfilehash: c3fa8aeebe529564c0ecc4a970f586fffc97ee05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133873"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="898b9-102">IHostIoCompletionManager::CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="898b9-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="898b9-103">호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="898b9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="898b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="898b9-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="898b9-106">제한이 새로 만든 i/o 완료 포트의 핸들에 대 한 포인터 이거나, 포트를 만들 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="898b9-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="898b9-107">Return Value</span></span>  
  
|<span data-ttu-id="898b9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="898b9-108">HRESULT</span></span>|<span data-ttu-id="898b9-109">설명</span><span class="sxs-lookup"><span data-stu-id="898b9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="898b9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="898b9-110">S_OK</span></span>|<span data-ttu-id="898b9-111">`CreateIoCompletionPort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="898b9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="898b9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="898b9-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="898b9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="898b9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="898b9-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-115">The call timed out.</span></span>|  
|<span data-ttu-id="898b9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="898b9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="898b9-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="898b9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="898b9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="898b9-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="898b9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="898b9-120">E_FAIL</span></span>|<span data-ttu-id="898b9-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="898b9-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="898b9-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="898b9-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="898b9-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="898b9-125">요청한 리소스를 할당 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="898b9-126">주의</span><span class="sxs-lookup"><span data-stu-id="898b9-126">Remarks</span></span>  
 <span data-ttu-id="898b9-127">CLR은 `CreateIoCompletionPort` 메서드를 호출 하 여 호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="898b9-128">[IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 i/o 작업을이 포트에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="898b9-129">호스트는 [IclrioOnComplete manager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)를 호출 하 여 CLR에 상태를 다시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898b9-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="898b9-130">Requirements</span></span>  
 <span data-ttu-id="898b9-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="898b9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898b9-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="898b9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="898b9-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="898b9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="898b9-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898b9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898b9-135">참조</span><span class="sxs-lookup"><span data-stu-id="898b9-135">See also</span></span>

- [<span data-ttu-id="898b9-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="898b9-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="898b9-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="898b9-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
