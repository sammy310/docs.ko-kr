---
description: ICLRSyncManager::D eleteRWLockOwnerIterator 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 7968f326f1ad92fe6e3a0f91749fb7e462e81c04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789777"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="f1471-103">ICLRSyncManager::DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="f1471-103">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>

<span data-ttu-id="f1471-104">CLR (공용 언어 런타임)에서 [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)를 호출 하 여 만든 반복기를 소멸 시 키 지 않도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-104">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1471-105">구문</span><span class="sxs-lookup"><span data-stu-id="f1471-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1471-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1471-106">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="f1471-107">진행 호출을 사용 하 여 만든 반복기입니다 `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="f1471-107">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1471-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="f1471-108">Return Value</span></span>  
  
|<span data-ttu-id="f1471-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1471-109">HRESULT</span></span>|<span data-ttu-id="f1471-110">설명</span><span class="sxs-lookup"><span data-stu-id="f1471-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1471-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1471-111">S_OK</span></span>|<span data-ttu-id="f1471-112">`DeleteRWLockOwnerIterator` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-112">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="f1471-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1471-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1471-114">CLR이 프로세스에 로드 되지 않았거나 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-114">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="f1471-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1471-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1471-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-116">The call timed out.</span></span>|  
|<span data-ttu-id="f1471-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1471-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1471-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1471-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1471-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1471-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1471-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1471-121">E_FAIL</span></span>|<span data-ttu-id="f1471-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1471-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1471-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1471-125">설명</span><span class="sxs-lookup"><span data-stu-id="f1471-125">Remarks</span></span>  

 <span data-ttu-id="f1471-126">호스트는이 메서드를 호출 하 고 `CreateRWLockOwnerIterator` 해당 스레딩 구현이 동기화 된 상태로 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-126">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1471-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1471-127">Requirements</span></span>  

 <span data-ttu-id="f1471-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1471-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1471-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1471-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1471-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1471-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1471-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1471-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1471-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1471-132">See also</span></span>

- [<span data-ttu-id="f1471-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1471-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f1471-134">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1471-134">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
