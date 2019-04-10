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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 668e570c315f5473f222905a061f05ac94afa81a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183406"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="e12da-102">ICLRTask::GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="e12da-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="e12da-103">태스크와 관련 된 통계 메모리 사용 정보를 가져옵니다는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12da-104">구문</span><span class="sxs-lookup"><span data-stu-id="e12da-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e12da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e12da-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="e12da-106">[out] 에 대 한 포인터를 [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) 할당 된 바이트 수를 포함 하 여 작업의 메모리 사용량에 대 한 세부 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e12da-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e12da-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e12da-107">Return Value</span></span>  
  
|<span data-ttu-id="e12da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e12da-108">HRESULT</span></span>|<span data-ttu-id="e12da-109">설명</span><span class="sxs-lookup"><span data-stu-id="e12da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e12da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e12da-110">S_OK</span></span>|`GetMemStats` <span data-ttu-id="e12da-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-111">returned successfully.</span></span>|  
|<span data-ttu-id="e12da-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e12da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e12da-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e12da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e12da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e12da-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-115">The call timed out.</span></span>|  
|<span data-ttu-id="e12da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e12da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e12da-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e12da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e12da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e12da-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e12da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e12da-120">E_FAIL</span></span>|<span data-ttu-id="e12da-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e12da-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e12da-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e12da-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e12da-124">Requirements</span></span>  
 <span data-ttu-id="e12da-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e12da-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12da-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e12da-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e12da-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e12da-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e12da-128">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e12da-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e12da-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="e12da-129">See also</span></span>

- [<span data-ttu-id="e12da-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e12da-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e12da-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e12da-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e12da-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e12da-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e12da-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e12da-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
