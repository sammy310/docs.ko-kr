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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1746527a2667676dfeab89e72874204460bcd33c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126674"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="5149d-102">ICLRGCManager::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="5149d-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="5149d-103">지정된 된 세대의 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5149d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5149d-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5149d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5149d-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="5149d-106">[in] 수집을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-106">[in] The generation to collect.</span></span> <span data-ttu-id="5149d-107">모든 세대의 수집을 수행 하는 값이-1입니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5149d-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5149d-108">Return Value</span></span>  
  
|<span data-ttu-id="5149d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5149d-109">HRESULT</span></span>|<span data-ttu-id="5149d-110">설명</span><span class="sxs-lookup"><span data-stu-id="5149d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5149d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5149d-111">S_OK</span></span>|`Collect` <span data-ttu-id="5149d-112">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-112">returned successfully.</span></span>|  
|<span data-ttu-id="5149d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5149d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5149d-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5149d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5149d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5149d-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-116">The call timed out.</span></span>|  
|<span data-ttu-id="5149d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5149d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5149d-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5149d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5149d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5149d-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5149d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5149d-121">E_FAIL</span></span>|<span data-ttu-id="5149d-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5149d-123">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5149d-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5149d-125">설명</span><span class="sxs-lookup"><span data-stu-id="5149d-125">Remarks</span></span>  
 <span data-ttu-id="5149d-126">`Collect` 메서드를 사용 하면 CLR의 가비지 수집기가 현재 상태에 관계 없이 수집을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5149d-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5149d-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5149d-127">Requirements</span></span>  
 <span data-ttu-id="5149d-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5149d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5149d-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5149d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5149d-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5149d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5149d-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5149d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5149d-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="5149d-132">See also</span></span>

- [<span data-ttu-id="5149d-133">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="5149d-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="5149d-134">가비지 컬렉션</span><span class="sxs-lookup"><span data-stu-id="5149d-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="5149d-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5149d-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5149d-136">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5149d-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="5149d-137">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5149d-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5149d-138">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5149d-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5149d-139">호스팅</span><span class="sxs-lookup"><span data-stu-id="5149d-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
