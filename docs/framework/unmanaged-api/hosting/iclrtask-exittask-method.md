---
title: ICLRTask::ExitTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075889"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="618ba-102">ICLRTask::ExitTask 메서드</span><span class="sxs-lookup"><span data-stu-id="618ba-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="618ba-103">CLR (공용 언어 런타임) 태스크를 나타내는 현재 알립니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스 종료 되 고 태스크를 종료 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="618ba-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="618ba-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="618ba-105">Return Value</span></span>  
  
|<span data-ttu-id="618ba-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="618ba-106">HRESULT</span></span>|<span data-ttu-id="618ba-107">설명</span><span class="sxs-lookup"><span data-stu-id="618ba-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="618ba-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="618ba-108">S_OK</span></span>|<span data-ttu-id="618ba-109">`ExitTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="618ba-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="618ba-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="618ba-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="618ba-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="618ba-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="618ba-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-113">The call timed out.</span></span>|  
|<span data-ttu-id="618ba-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="618ba-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="618ba-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="618ba-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="618ba-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="618ba-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="618ba-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="618ba-118">E_FAIL</span></span>|<span data-ttu-id="618ba-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="618ba-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="618ba-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="618ba-122">설명</span><span class="sxs-lookup"><span data-stu-id="618ba-122">Remarks</span></span>  
 <span data-ttu-id="618ba-123">`ExitTask` 관리 되지 않는 형식 라이브러리에서 스레드를 분리 하는 비슷한 방식으로 작업의 완전 한 종료를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="618ba-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="618ba-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="618ba-124">Requirements</span></span>  
 <span data-ttu-id="618ba-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="618ba-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="618ba-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="618ba-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="618ba-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="618ba-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="618ba-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="618ba-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618ba-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="618ba-129">See also</span></span>

- [<span data-ttu-id="618ba-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="618ba-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="618ba-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="618ba-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="618ba-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="618ba-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="618ba-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="618ba-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
