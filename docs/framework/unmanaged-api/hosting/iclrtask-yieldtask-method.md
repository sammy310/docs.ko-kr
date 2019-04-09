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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113674"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="d25f1-102">ICLRTask::YieldTask 메서드</span><span class="sxs-lookup"><span data-stu-id="d25f1-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="d25f1-103">CLR (공용 언어 런타임) 태스크를 예약할 요청 하는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 및 프로세서 시간을 다른 작업을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d25f1-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d25f1-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="d25f1-105">Return Value</span></span>  
  
|<span data-ttu-id="d25f1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d25f1-106">HRESULT</span></span>|<span data-ttu-id="d25f1-107">설명</span><span class="sxs-lookup"><span data-stu-id="d25f1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d25f1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d25f1-108">S_OK</span></span>|`YieldTask` <span data-ttu-id="d25f1-109">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-109">returned successfully.</span></span>|  
|<span data-ttu-id="d25f1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d25f1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d25f1-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d25f1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d25f1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d25f1-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-113">The call timed out.</span></span>|  
|<span data-ttu-id="d25f1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d25f1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d25f1-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d25f1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d25f1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d25f1-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d25f1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d25f1-118">E_FAIL</span></span>|<span data-ttu-id="d25f1-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d25f1-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d25f1-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d25f1-122">설명</span><span class="sxs-lookup"><span data-stu-id="d25f1-122">Remarks</span></span>  
 <span data-ttu-id="d25f1-123">호스트 `YieldTask` 다른 작업 또는 프로세스에 대 한 프로세서 리소스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="d25f1-124">이 메서드는 주로 CPU 시간을 포기 하는 장기 실행 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="d25f1-125">런타임 작업 하려고 하는 현재 `ICLRTask` 처리 시간을를 얻을 수 있지만 성공 되지 않을 수도 있는 상태의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d25f1-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25f1-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d25f1-126">Requirements</span></span>  
 <span data-ttu-id="d25f1-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d25f1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25f1-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d25f1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d25f1-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d25f1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d25f1-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d25f1-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d25f1-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="d25f1-131">See also</span></span>

- [<span data-ttu-id="d25f1-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d25f1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d25f1-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d25f1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d25f1-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d25f1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d25f1-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d25f1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
