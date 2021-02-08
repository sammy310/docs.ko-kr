---
description: '자세한 정보: ICLRTask:: SetTaskIdentifier 메서드'
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
ms.openlocfilehash: e746d8ec96d16f7761dd49ac814ddbed073c2686
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784953"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="ecc02-103">ICLRTask::SetTaskIdentifier 메서드</span><span class="sxs-lookup"><span data-stu-id="ecc02-103">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="ecc02-104">지정 된 식별자 값을 현재 [ICLRTask](iclrtask-interface.md) 인스턴스로 표시 되는 작업과 연결 하도록 CLR (공용 언어 런타임)에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-104">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc02-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecc02-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc02-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecc02-106">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="ecc02-107">진행 현재 인스턴스가 나타내는 작업과 연결할 공용 언어 런타임의 고유 식별자입니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="ecc02-107">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecc02-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="ecc02-108">Return Value</span></span>  
  
|<span data-ttu-id="ecc02-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecc02-109">HRESULT</span></span>|<span data-ttu-id="ecc02-110">설명</span><span class="sxs-lookup"><span data-stu-id="ecc02-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecc02-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecc02-111">S_OK</span></span>|<span data-ttu-id="ecc02-112">`SetTaskIdentifier` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-112">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="ecc02-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ecc02-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ecc02-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ecc02-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ecc02-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ecc02-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-116">The call timed out.</span></span>|  
|<span data-ttu-id="ecc02-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ecc02-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ecc02-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ecc02-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ecc02-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ecc02-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ecc02-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecc02-121">E_FAIL</span></span>|<span data-ttu-id="ecc02-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ecc02-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ecc02-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecc02-125">설명</span><span class="sxs-lookup"><span data-stu-id="ecc02-125">Remarks</span></span>  

 <span data-ttu-id="ecc02-126">호스트는 디버깅 환경에서 CLR 및 호스트를 통합 하는 데 도움이 되는 작업과 식별자를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-126">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="ecc02-127">식별자는 CLR에 대해 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-127">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="ecc02-128">CLR은 디버거 응용 프로그램에이를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-128">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="ecc02-129">디버거는이 식별자를 사용 하 여 CLR 호출 스택을 호스트 호출 스택과 연결 하 고 디버거의 사용자 인터페이스에서 볼 때 해당 추적 정보를 통합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-129">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc02-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecc02-130">Requirements</span></span>  

 <span data-ttu-id="ecc02-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecc02-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc02-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ecc02-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecc02-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecc02-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecc02-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc02-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc02-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecc02-135">See also</span></span>

- [<span data-ttu-id="ecc02-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecc02-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ecc02-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecc02-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ecc02-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecc02-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ecc02-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecc02-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
