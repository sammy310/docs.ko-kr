---
description: '자세히 알아보기: ICLRGCManager:: GetStats 메서드'
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
ms.openlocfilehash: 94b20fb313f06d73f1e7fafd1f46fefb0da3fe95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790024"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="46cff-103">ICLRGCManager::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="46cff-103">ICLRGCManager::GetStats Method</span></span>

<span data-ttu-id="46cff-104">공용 언어 런타임의 가비지 컬렉션 시스템에 대 한 현재 통계 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-104">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46cff-105">구문</span><span class="sxs-lookup"><span data-stu-id="46cff-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46cff-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46cff-106">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="46cff-107">[in, out] 요청한 통계를 포함 하는 [COR_GC_STATS](cor-gc-stats-structure.md) 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-107">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46cff-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="46cff-108">Return Value</span></span>  
  
|<span data-ttu-id="46cff-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46cff-109">HRESULT</span></span>|<span data-ttu-id="46cff-110">설명</span><span class="sxs-lookup"><span data-stu-id="46cff-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46cff-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46cff-111">S_OK</span></span>|<span data-ttu-id="46cff-112">`GetStats` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-112">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="46cff-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46cff-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46cff-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46cff-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46cff-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46cff-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-116">The call timed out.</span></span>|  
|<span data-ttu-id="46cff-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46cff-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46cff-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46cff-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46cff-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46cff-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46cff-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46cff-121">E_FAIL</span></span>|<span data-ttu-id="46cff-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46cff-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46cff-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46cff-125">설명</span><span class="sxs-lookup"><span data-stu-id="46cff-125">Remarks</span></span>  

 <span data-ttu-id="46cff-126">CLR은의 필드에 지정 된 통계만 계산 하 고 반환 `Flags` `pStats` 합니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-126">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="46cff-127">필드를 `Flags` [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) 열거형의 하나 이상의 값으로 설정 하 여 [COR_GC_STATS](cor-gc-stats-structure.md) 구조에서 설정할 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-127">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="46cff-128">사용 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-128">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="46cff-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46cff-129">Requirements</span></span>  

 <span data-ttu-id="46cff-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46cff-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46cff-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="46cff-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46cff-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46cff-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46cff-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46cff-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46cff-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46cff-134">See also</span></span>

- [<span data-ttu-id="46cff-135">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="46cff-135">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="46cff-136">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="46cff-136">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="46cff-137">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="46cff-137">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="46cff-138">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="46cff-138">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="46cff-139">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46cff-139">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="46cff-140">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46cff-140">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="46cff-141">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46cff-141">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="46cff-142">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46cff-142">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="46cff-143">호스팅</span><span class="sxs-lookup"><span data-stu-id="46cff-143">Hosting</span></span>](index.md)
