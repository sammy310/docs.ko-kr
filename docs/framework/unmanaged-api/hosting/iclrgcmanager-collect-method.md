---
description: '자세히 알아보기: ICLRGCManager:: Collect 메서드'
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
ms.openlocfilehash: 7c2649f7ce3472c504c1e48a203cf89d4b8508e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746063"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="bd2b7-103">ICLRGCManager::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="bd2b7-103">ICLRGCManager::Collect Method</span></span>

<span data-ttu-id="bd2b7-104">지정 된 세대에 대 한 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-104">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd2b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd2b7-105">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd2b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd2b7-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="bd2b7-107">진행 수집할 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-107">[in] The generation to collect.</span></span> <span data-ttu-id="bd2b7-108">값-1은 모든 세대의 컬렉션을 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-108">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd2b7-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="bd2b7-109">Return Value</span></span>  
  
|<span data-ttu-id="bd2b7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd2b7-110">HRESULT</span></span>|<span data-ttu-id="bd2b7-111">설명</span><span class="sxs-lookup"><span data-stu-id="bd2b7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd2b7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd2b7-112">S_OK</span></span>|<span data-ttu-id="bd2b7-113">`Collect` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-113">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="bd2b7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd2b7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd2b7-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd2b7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd2b7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd2b7-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-117">The call timed out.</span></span>|  
|<span data-ttu-id="bd2b7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd2b7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd2b7-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd2b7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd2b7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd2b7-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd2b7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd2b7-122">E_FAIL</span></span>|<span data-ttu-id="bd2b7-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd2b7-124">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd2b7-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd2b7-126">설명</span><span class="sxs-lookup"><span data-stu-id="bd2b7-126">Remarks</span></span>  

 <span data-ttu-id="bd2b7-127">`Collect`메서드는 현재 상태에 관계 없이 CLR의 가비지 수집기가 컬렉션을 수행 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-127">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd2b7-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd2b7-128">Requirements</span></span>  

 <span data-ttu-id="bd2b7-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd2b7-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bd2b7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd2b7-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd2b7-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd2b7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2b7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd2b7-133">See also</span></span>

- [<span data-ttu-id="bd2b7-134">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="bd2b7-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="bd2b7-135">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="bd2b7-135">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="bd2b7-136">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd2b7-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="bd2b7-137">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd2b7-137">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="bd2b7-138">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd2b7-138">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="bd2b7-139">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd2b7-139">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="bd2b7-140">호스팅</span><span class="sxs-lookup"><span data-stu-id="bd2b7-140">Hosting</span></span>](index.md)
