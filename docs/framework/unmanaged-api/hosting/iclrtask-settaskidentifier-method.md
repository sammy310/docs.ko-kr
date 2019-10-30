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
ms.openlocfilehash: cf6d84e483188ea7ed3376ba9b28906a38913fd4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124634"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="66a8b-102">ICLRTask::SetTaskIdentifier 메서드</span><span class="sxs-lookup"><span data-stu-id="66a8b-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="66a8b-103">지정 된 식별자 값을 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스로 표시 되는 작업과 연결 하도록 CLR (공용 언어 런타임)에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="66a8b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66a8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66a8b-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="66a8b-106">진행 현재 `ICLRTask` 인스턴스가 나타내는 작업과 연결할 공용 언어 런타임의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66a8b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="66a8b-107">Return Value</span></span>  
  
|<span data-ttu-id="66a8b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66a8b-108">HRESULT</span></span>|<span data-ttu-id="66a8b-109">설명</span><span class="sxs-lookup"><span data-stu-id="66a8b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66a8b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="66a8b-110">S_OK</span></span>|<span data-ttu-id="66a8b-111">`SetTaskIdentifier` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="66a8b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66a8b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66a8b-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66a8b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66a8b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66a8b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-115">The call timed out.</span></span>|  
|<span data-ttu-id="66a8b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66a8b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66a8b-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66a8b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66a8b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66a8b-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66a8b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66a8b-120">E_FAIL</span></span>|<span data-ttu-id="66a8b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66a8b-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66a8b-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66a8b-124">주의</span><span class="sxs-lookup"><span data-stu-id="66a8b-124">Remarks</span></span>  
 <span data-ttu-id="66a8b-125">호스트는 디버깅 환경에서 CLR 및 호스트를 통합 하는 데 도움이 되는 작업과 식별자를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="66a8b-126">식별자는 CLR에 대해 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="66a8b-127">CLR은 디버거 응용 프로그램에이를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="66a8b-128">디버거는이 식별자를 사용 하 여 CLR 호출 스택을 호스트 호출 스택과 연결 하 고 디버거의 사용자 인터페이스에서 볼 때 해당 추적 정보를 통합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66a8b-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66a8b-129">Requirements</span></span>  
 <span data-ttu-id="66a8b-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66a8b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a8b-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="66a8b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66a8b-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66a8b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66a8b-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a8b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a8b-134">참조</span><span class="sxs-lookup"><span data-stu-id="66a8b-134">See also</span></span>

- [<span data-ttu-id="66a8b-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66a8b-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="66a8b-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66a8b-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="66a8b-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66a8b-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="66a8b-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66a8b-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
