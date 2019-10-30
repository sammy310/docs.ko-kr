---
title: ICLRTask::GetMemStats 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139695"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="2ab28-102">ICLRTask::GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="2ab28-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="2ab28-103">현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 작업과 관련 된 통계 메모리 사용 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab28-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ab28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ab28-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="2ab28-106">제한이 할당 된 바이트 수를 포함 하 여 태스크의 메모리 사용량에 대 한 세부 정보를 포함 하는 [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ab28-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="2ab28-107">Return Value</span></span>  
  
|<span data-ttu-id="2ab28-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ab28-108">HRESULT</span></span>|<span data-ttu-id="2ab28-109">설명</span><span class="sxs-lookup"><span data-stu-id="2ab28-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ab28-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ab28-110">S_OK</span></span>|<span data-ttu-id="2ab28-111">`GetMemStats` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="2ab28-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ab28-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ab28-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ab28-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ab28-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ab28-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ab28-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ab28-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ab28-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ab28-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ab28-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ab28-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ab28-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ab28-120">E_FAIL</span></span>|<span data-ttu-id="2ab28-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ab28-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ab28-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ab28-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ab28-124">Requirements</span></span>  
 <span data-ttu-id="2ab28-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab28-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab28-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2ab28-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ab28-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab28-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab28-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab28-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab28-129">참조</span><span class="sxs-lookup"><span data-stu-id="2ab28-129">See also</span></span>

- [<span data-ttu-id="2ab28-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ab28-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2ab28-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ab28-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2ab28-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ab28-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2ab28-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ab28-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
