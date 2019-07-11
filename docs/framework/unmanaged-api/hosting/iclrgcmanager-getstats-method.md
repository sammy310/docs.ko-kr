---
title: ICLRGCManager::GetStats 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 768d16a05bbe139c3fe02677526bc28809a93be0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779726"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="849d3-102">ICLRGCManager::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="849d3-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="849d3-103">공용 언어 런타임의 가비지 컬렉션 시스템에 대 한 현재 통계의 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="849d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="849d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="849d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="849d3-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="849d3-106">[out에서] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 요청된 통계를 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="849d3-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="849d3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="849d3-107">Return Value</span></span>  
  
|<span data-ttu-id="849d3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="849d3-108">HRESULT</span></span>|<span data-ttu-id="849d3-109">설명</span><span class="sxs-lookup"><span data-stu-id="849d3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="849d3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="849d3-110">S_OK</span></span>|<span data-ttu-id="849d3-111">`GetStats` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="849d3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="849d3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="849d3-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="849d3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="849d3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="849d3-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-115">The call timed out.</span></span>|  
|<span data-ttu-id="849d3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="849d3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="849d3-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="849d3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="849d3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="849d3-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="849d3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="849d3-120">E_FAIL</span></span>|<span data-ttu-id="849d3-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="849d3-122">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="849d3-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="849d3-124">설명</span><span class="sxs-lookup"><span data-stu-id="849d3-124">Remarks</span></span>  
 <span data-ttu-id="849d3-125">CLR 계산 하 고 지정 된 통계만 반환 합니다 `Flags` 필드에 `pStats`입니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="849d3-126">설정 합니다 `Flags` 필드의 하나 이상의 값에는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 에서 통계를 지정 하는 열거형을 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 설정할 구조는 합니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="849d3-127">사용 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="849d3-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="849d3-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="849d3-128">Requirements</span></span>  
 <span data-ttu-id="849d3-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="849d3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="849d3-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="849d3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="849d3-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="849d3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="849d3-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="849d3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849d3-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="849d3-133">See also</span></span>

- [<span data-ttu-id="849d3-134">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="849d3-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="849d3-135">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="849d3-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="849d3-136">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="849d3-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="849d3-137">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="849d3-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="849d3-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="849d3-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="849d3-139">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="849d3-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="849d3-140">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="849d3-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="849d3-141">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="849d3-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="849d3-142">호스팅</span><span class="sxs-lookup"><span data-stu-id="849d3-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
