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
ms.openlocfilehash: fb02b5c941e15d172140565e8efb625234947cd7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130571"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="8f7f2-102">ICLRSyncManager::DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="8f7f2-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="8f7f2-103">CLR (공용 언어 런타임)에서 [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)를 호출 하 여 만든 반복기를 소멸 시 키 지 않도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f7f2-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7f2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f7f2-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="8f7f2-106">진행 `CreateRWLockOwnerIterator`에 대 한 호출을 사용 하 여 만든 반복기입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7f2-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8f7f2-107">Return Value</span></span>  
  
|<span data-ttu-id="8f7f2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f7f2-108">HRESULT</span></span>|<span data-ttu-id="8f7f2-109">설명</span><span class="sxs-lookup"><span data-stu-id="8f7f2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f7f2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f7f2-110">S_OK</span></span>|<span data-ttu-id="8f7f2-111">`DeleteRWLockOwnerIterator` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="8f7f2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f7f2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f7f2-113">CLR이 프로세스에 로드 되지 않았거나 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="8f7f2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f7f2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f7f2-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-115">The call timed out.</span></span>|  
|<span data-ttu-id="8f7f2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f7f2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f7f2-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f7f2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f7f2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f7f2-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f7f2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f7f2-120">E_FAIL</span></span>|<span data-ttu-id="8f7f2-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f7f2-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f7f2-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f7f2-124">주의</span><span class="sxs-lookup"><span data-stu-id="8f7f2-124">Remarks</span></span>  
 <span data-ttu-id="8f7f2-125">호스트는이 메서드를 호출 하 고 `CreateRWLockOwnerIterator` 하 여 해당 스레딩 구현이 동기화 된 상태로 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7f2-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f7f2-126">Requirements</span></span>  
 <span data-ttu-id="8f7f2-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7f2-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f7f2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f7f2-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f7f2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f7f2-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7f2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7f2-131">참조</span><span class="sxs-lookup"><span data-stu-id="8f7f2-131">See also</span></span>

- [<span data-ttu-id="8f7f2-132">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f7f2-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8f7f2-133">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f7f2-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
