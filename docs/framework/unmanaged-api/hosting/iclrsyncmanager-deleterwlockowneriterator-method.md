---
title: ICLRSyncManager::DeleteRWLockOwnerIterator 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a30ac0ab8c985af04709ddd8e8e5dd9bca776dcb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759085"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="2b789-102">ICLRSyncManager::DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="2b789-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="2b789-103">CLR (공용 언어 런타임)를 호출 하 여 생성 된 반복기 삭제를 요청 [iclrsyncmanager:: Createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b789-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b789-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b789-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b789-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="2b789-106">[in] 에 대 한 호출을 사용 하 여 생성 된 반복기 `CreateRWLockOwnerIterator`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b789-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="2b789-107">Return Value</span></span>  
  
|<span data-ttu-id="2b789-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b789-108">HRESULT</span></span>|<span data-ttu-id="2b789-109">Description</span><span class="sxs-lookup"><span data-stu-id="2b789-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b789-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b789-110">S_OK</span></span>|<span data-ttu-id="2b789-111">`DeleteRWLockOwnerIterator` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="2b789-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b789-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b789-113">CLR을 프로세스로 로드 되지 않았습니다 또는 상태는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="2b789-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b789-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b789-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-115">The call timed out.</span></span>|  
|<span data-ttu-id="2b789-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b789-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b789-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b789-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b789-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b789-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b789-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b789-120">E_FAIL</span></span>|<span data-ttu-id="2b789-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b789-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b789-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b789-124">설명</span><span class="sxs-lookup"><span data-stu-id="2b789-124">Remarks</span></span>  
 <span data-ttu-id="2b789-125">호스트에서이 메서드를 호출할 수 및 `CreateRWLockOwnerIterator` 스레딩 구현이 동기화 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b789-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b789-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b789-126">Requirements</span></span>  
 <span data-ttu-id="2b789-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b789-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b789-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b789-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b789-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2b789-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b789-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b789-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b789-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b789-131">See also</span></span>

- [<span data-ttu-id="2b789-132">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b789-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2b789-133">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b789-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
