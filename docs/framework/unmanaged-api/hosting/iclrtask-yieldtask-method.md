---
title: ICLRTask::YieldTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
ms.openlocfilehash: 43f2048c8ab85fa7e94f73aad430400ad4c8352f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124589"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="f43b6-102">ICLRTask::YieldTask 메서드</span><span class="sxs-lookup"><span data-stu-id="f43b6-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="f43b6-103">CLR (공용 언어 런타임)이 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 작업을 분리 하 고 다른 작업에서 프로세서 시간을 사용할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="f43b6-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f43b6-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f43b6-105">Return Value</span></span>  
  
|<span data-ttu-id="f43b6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f43b6-106">HRESULT</span></span>|<span data-ttu-id="f43b6-107">설명</span><span class="sxs-lookup"><span data-stu-id="f43b6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f43b6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f43b6-108">S_OK</span></span>|<span data-ttu-id="f43b6-109">`YieldTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="f43b6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f43b6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f43b6-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f43b6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f43b6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f43b6-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-113">The call timed out.</span></span>|  
|<span data-ttu-id="f43b6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f43b6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f43b6-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f43b6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f43b6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f43b6-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f43b6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f43b6-118">E_FAIL</span></span>|<span data-ttu-id="f43b6-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f43b6-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f43b6-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f43b6-122">주의</span><span class="sxs-lookup"><span data-stu-id="f43b6-122">Remarks</span></span>  
 <span data-ttu-id="f43b6-123">호스트는 `YieldTask`를 호출 하 여 다른 작업 또는 프로세스에 대 한 프로세서 리소스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="f43b6-124">이 메서드는 주로 장기 실행 코드가 CPU 시간을 제공할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="f43b6-125">런타임에서는 현재 `ICLRTask` 인스턴스가 처리 시간을 얻을 수 있는 상태로 표시 되지만 성공 여부는 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43b6-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f43b6-126">Requirements</span></span>  
 <span data-ttu-id="f43b6-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f43b6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43b6-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f43b6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f43b6-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f43b6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f43b6-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43b6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43b6-131">참조</span><span class="sxs-lookup"><span data-stu-id="f43b6-131">See also</span></span>

- [<span data-ttu-id="f43b6-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f43b6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f43b6-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f43b6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f43b6-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f43b6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f43b6-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f43b6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
