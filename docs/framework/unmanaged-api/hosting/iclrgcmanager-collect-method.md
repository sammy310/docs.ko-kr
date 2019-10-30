---
title: ICLRGCManager::Collect 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: a7dae98d1f2dc2448bd3a5df2d6143b7be0bb734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129266"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="d1c99-102">ICLRGCManager::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="d1c99-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="d1c99-103">지정 된 세대에 대 한 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c99-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1c99-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1c99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1c99-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="d1c99-106">진행 수집할 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-106">[in] The generation to collect.</span></span> <span data-ttu-id="d1c99-107">값-1은 모든 세대의 컬렉션을 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1c99-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d1c99-108">Return Value</span></span>  
  
|<span data-ttu-id="d1c99-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1c99-109">HRESULT</span></span>|<span data-ttu-id="d1c99-110">설명</span><span class="sxs-lookup"><span data-stu-id="d1c99-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1c99-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1c99-111">S_OK</span></span>|<span data-ttu-id="d1c99-112">`Collect` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="d1c99-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d1c99-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d1c99-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d1c99-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d1c99-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d1c99-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-116">The call timed out.</span></span>|  
|<span data-ttu-id="d1c99-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d1c99-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d1c99-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d1c99-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d1c99-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d1c99-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d1c99-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1c99-121">E_FAIL</span></span>|<span data-ttu-id="d1c99-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d1c99-123">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d1c99-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1c99-125">주의</span><span class="sxs-lookup"><span data-stu-id="d1c99-125">Remarks</span></span>  
 <span data-ttu-id="d1c99-126">`Collect` 메서드는 현재 상태에 관계 없이 CLR의 가비지 수집기가 컬렉션을 수행 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1c99-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c99-127">Requirements</span></span>  
 <span data-ttu-id="d1c99-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1c99-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1c99-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d1c99-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1c99-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c99-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1c99-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1c99-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c99-132">참조</span><span class="sxs-lookup"><span data-stu-id="d1c99-132">See also</span></span>

- [<span data-ttu-id="d1c99-133">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="d1c99-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="d1c99-134">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="d1c99-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="d1c99-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1c99-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d1c99-136">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1c99-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="d1c99-137">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1c99-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="d1c99-138">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1c99-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d1c99-139">호스팅</span><span class="sxs-lookup"><span data-stu-id="d1c99-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
