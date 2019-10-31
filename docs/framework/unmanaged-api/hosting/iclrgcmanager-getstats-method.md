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
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141149"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="b618c-102">ICLRGCManager::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="b618c-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="b618c-103">공용 언어 런타임의 가비지 컬렉션 시스템에 대 한 현재 통계 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b618c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b618c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b618c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b618c-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="b618c-106">[in, out] 요청한 통계를 포함 하는 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b618c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="b618c-107">Return Value</span></span>  
  
|<span data-ttu-id="b618c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b618c-108">HRESULT</span></span>|<span data-ttu-id="b618c-109">설명</span><span class="sxs-lookup"><span data-stu-id="b618c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b618c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b618c-110">S_OK</span></span>|<span data-ttu-id="b618c-111">`GetStats` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="b618c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b618c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b618c-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b618c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b618c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b618c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-115">The call timed out.</span></span>|  
|<span data-ttu-id="b618c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b618c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b618c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b618c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b618c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b618c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b618c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b618c-120">E_FAIL</span></span>|<span data-ttu-id="b618c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b618c-122">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b618c-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b618c-124">주의</span><span class="sxs-lookup"><span data-stu-id="b618c-124">Remarks</span></span>  
 <span data-ttu-id="b618c-125">CLR은 `pStats`의 `Flags` 필드로 지정 된 통계만 계산 하 고 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="b618c-126">`Flags` 필드를 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형의 하나 이상의 값으로 설정 하 여 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 구조체에서 설정할 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="b618c-127">사용 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b618c-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b618c-128">Requirements</span></span>  
 <span data-ttu-id="b618c-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b618c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b618c-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b618c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b618c-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b618c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b618c-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b618c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b618c-133">참조</span><span class="sxs-lookup"><span data-stu-id="b618c-133">See also</span></span>

- [<span data-ttu-id="b618c-134">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="b618c-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b618c-135">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="b618c-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="b618c-136">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="b618c-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="b618c-137">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="b618c-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b618c-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b618c-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b618c-139">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b618c-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="b618c-140">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b618c-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b618c-141">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b618c-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b618c-142">호스팅</span><span class="sxs-lookup"><span data-stu-id="b618c-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
