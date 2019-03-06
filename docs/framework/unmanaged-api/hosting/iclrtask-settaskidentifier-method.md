---
title: ICLRTask::SetTaskIdentifier 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58a010def407751a49cbb1de51c59a3df85cfb18
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487770"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="418d8-102">ICLRTask::SetTaskIdentifier 메서드</span><span class="sxs-lookup"><span data-stu-id="418d8-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="418d8-103">공용 언어 런타임 (CLR) 현재 나타내는 작업을 사용 하 여 지정 된 식별자 값을 연결할 지시 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="418d8-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="418d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="418d8-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="418d8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="418d8-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="418d8-106">[in] 현재 작업과 연결할 공용 언어 런타임에 대 한 고유 식별자 `ICLRTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="418d8-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="418d8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="418d8-107">Return Value</span></span>  
  
|<span data-ttu-id="418d8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="418d8-108">HRESULT</span></span>|<span data-ttu-id="418d8-109">설명</span><span class="sxs-lookup"><span data-stu-id="418d8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="418d8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="418d8-110">S_OK</span></span>|<span data-ttu-id="418d8-111">`SetTaskIdentifier` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="418d8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="418d8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="418d8-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="418d8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="418d8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="418d8-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-115">The call timed out.</span></span>|  
|<span data-ttu-id="418d8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="418d8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="418d8-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="418d8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="418d8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="418d8-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="418d8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="418d8-120">E_FAIL</span></span>|<span data-ttu-id="418d8-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="418d8-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="418d8-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="418d8-124">설명</span><span class="sxs-lookup"><span data-stu-id="418d8-124">Remarks</span></span>  
 <span data-ttu-id="418d8-125">호스트에서는 식별자를 CLR 및 디버깅 환경에서 호스트에 통합할 수 있도록 하는 작업에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="418d8-126">식별자는 CLR에 대 한 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="418d8-127">CLR은 디버거 응용 프로그램에 따라이 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="418d8-128">디버거가는 CLR 호출 스택을 호스트 호출 스택과 연결할이 식별자를 사용할 수 있으며 해당 추적 정보를 디버거 사용자 인터페이스에서 볼 때 통합을 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="418d8-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="418d8-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="418d8-129">Requirements</span></span>  
 <span data-ttu-id="418d8-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="418d8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="418d8-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="418d8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="418d8-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="418d8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="418d8-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="418d8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418d8-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="418d8-134">See also</span></span>
- [<span data-ttu-id="418d8-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d8-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="418d8-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d8-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="418d8-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d8-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="418d8-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d8-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
