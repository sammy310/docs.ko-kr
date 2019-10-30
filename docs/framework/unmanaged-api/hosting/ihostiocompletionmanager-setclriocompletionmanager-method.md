---
title: IHostIoCompletionManager::SetCLRIoCompletionManager 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: b84e92ca356ad83421d788a732926b614ffa4a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133784"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="89501-102">IHostIoCompletionManager::SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="89501-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="89501-103">호스트에 CLR (공용 언어 런타임)에 의해 구현 된 [Iclriocompletionmanager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89501-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89501-104">구문</span><span class="sxs-lookup"><span data-stu-id="89501-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89501-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89501-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="89501-106">진행 CLR에서 제공 하는 `ICLRIoCompletionManager` 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89501-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89501-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="89501-107">Return Value</span></span>  
  
|<span data-ttu-id="89501-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89501-108">HRESULT</span></span>|<span data-ttu-id="89501-109">설명</span><span class="sxs-lookup"><span data-stu-id="89501-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89501-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="89501-110">S_OK</span></span>|<span data-ttu-id="89501-111">`SetCLRIoCompletionManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="89501-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89501-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89501-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89501-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89501-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89501-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-115">The call timed out.</span></span>|  
|<span data-ttu-id="89501-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89501-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89501-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89501-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89501-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89501-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89501-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89501-120">E_FAIL</span></span>|<span data-ttu-id="89501-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89501-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89501-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89501-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="89501-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89501-124">주의</span><span class="sxs-lookup"><span data-stu-id="89501-124">Remarks</span></span>  
 <span data-ttu-id="89501-125">CLR `SetCLRIoCompletionManager`호출한 후 호스트는 [IclrioOnComplete manager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) 를 호출 하 여 i/o 요청이 완료 되었을 때 clr에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89501-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89501-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89501-126">Requirements</span></span>  
 <span data-ttu-id="89501-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89501-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89501-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="89501-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89501-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89501-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89501-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89501-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89501-131">참조</span><span class="sxs-lookup"><span data-stu-id="89501-131">See also</span></span>

- [<span data-ttu-id="89501-132">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89501-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="89501-133">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89501-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
