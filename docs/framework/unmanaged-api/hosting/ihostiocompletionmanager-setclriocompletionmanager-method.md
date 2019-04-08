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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd48664c78e3f5772cdfa655ebbc7cfa716f4950
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107206"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="06129-102">IHostIoCompletionManager::SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="06129-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="06129-103">호스트에 대 한 인터페이스 포인터를 제공 합니다 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) 는 CLR (공용 언어 런타임)에 의해 구현 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="06129-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06129-104">구문</span><span class="sxs-lookup"><span data-stu-id="06129-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06129-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06129-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="06129-106">[in] 에 대 한 인터페이스 포인터를 `ICLRIoCompletionManager` CLR에서 제공 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="06129-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06129-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="06129-107">Return Value</span></span>  
  
|<span data-ttu-id="06129-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06129-108">HRESULT</span></span>|<span data-ttu-id="06129-109">설명</span><span class="sxs-lookup"><span data-stu-id="06129-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06129-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="06129-110">S_OK</span></span>|`SetCLRIoCompletionManager` <span data-ttu-id="06129-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06129-111">returned successfully.</span></span>|  
|<span data-ttu-id="06129-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06129-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06129-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06129-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06129-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06129-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-115">The call timed out.</span></span>|  
|<span data-ttu-id="06129-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06129-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06129-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06129-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06129-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06129-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06129-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06129-120">E_FAIL</span></span>|<span data-ttu-id="06129-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06129-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06129-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06129-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06129-124">설명</span><span class="sxs-lookup"><span data-stu-id="06129-124">Remarks</span></span>  
 <span data-ttu-id="06129-125">CLR이 호출 후 `SetCLRIoCompletionManager`, 호스트를 호출 해야 합니다 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) I/O 요청을 완료 되 면 CLR에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06129-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06129-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06129-126">Requirements</span></span>  
 <span data-ttu-id="06129-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06129-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06129-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06129-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06129-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="06129-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="06129-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="06129-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="06129-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="06129-131">See also</span></span>

- [<span data-ttu-id="06129-132">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06129-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="06129-133">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06129-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
