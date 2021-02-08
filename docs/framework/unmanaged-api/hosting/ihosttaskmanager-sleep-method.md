---
description: '자세히 알아보기: IHostTaskManager:: Sleep 메서드'
title: IHostTaskManager::Sleep 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: fedb87c6bd4558a2aa6158299551327cb2271d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789374"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="e9ad3-103">IHostTaskManager::Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ad3-103">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="e9ad3-104">현재 태스크가 절전 모드로 전환 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-104">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ad3-105">구문</span><span class="sxs-lookup"><span data-stu-id="e9ad3-105">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9ad3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9ad3-106">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="e9ad3-107">진행 스레드가 절전 모드로 전환 되는 시간 간격 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-107">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="e9ad3-108">진행 이 작업이 차단 될 경우 호스트가 수행할 동작을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 열거형 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9ad3-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="e9ad3-109">Return Value</span></span>  
  
|<span data-ttu-id="e9ad3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9ad3-110">HRESULT</span></span>|<span data-ttu-id="e9ad3-111">설명</span><span class="sxs-lookup"><span data-stu-id="e9ad3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9ad3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9ad3-112">S_OK</span></span>|<span data-ttu-id="e9ad3-113">`Sleep` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-113">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="e9ad3-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9ad3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9ad3-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9ad3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9ad3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9ad3-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-117">The call timed out.</span></span>|  
|<span data-ttu-id="e9ad3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9ad3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9ad3-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9ad3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9ad3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9ad3-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9ad3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9ad3-122">E_FAIL</span></span>|<span data-ttu-id="e9ad3-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9ad3-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9ad3-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9ad3-126">설명</span><span class="sxs-lookup"><span data-stu-id="e9ad3-126">Remarks</span></span>  

 <span data-ttu-id="e9ad3-127">일반적으로 CLR은 `IHostTaskManager::Sleep` <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 사용자 코드에서가 호출 될 때를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-127">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9ad3-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9ad3-128">Requirements</span></span>  

 <span data-ttu-id="e9ad3-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ad3-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e9ad3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9ad3-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9ad3-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ad3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ad3-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9ad3-133">See also</span></span>

- [<span data-ttu-id="e9ad3-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ad3-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e9ad3-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ad3-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e9ad3-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ad3-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e9ad3-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ad3-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
