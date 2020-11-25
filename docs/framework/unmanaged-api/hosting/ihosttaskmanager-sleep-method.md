---
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
ms.openlocfilehash: 372b15a565f8a7484c1c42c387098a38f7bbf428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702058"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="73a66-102">IHostTaskManager::Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="73a66-102">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="73a66-103">현재 태스크가 절전 모드로 전환 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a66-104">구문</span><span class="sxs-lookup"><span data-stu-id="73a66-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73a66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73a66-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="73a66-106">진행 스레드가 절전 모드로 전환 되는 시간 간격 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="73a66-107">진행 이 작업이 차단 될 경우 호스트가 수행할 동작을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 열거형 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73a66-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="73a66-108">Return Value</span></span>  
  
|<span data-ttu-id="73a66-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73a66-109">HRESULT</span></span>|<span data-ttu-id="73a66-110">설명</span><span class="sxs-lookup"><span data-stu-id="73a66-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73a66-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73a66-111">S_OK</span></span>|<span data-ttu-id="73a66-112">`Sleep` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="73a66-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73a66-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73a66-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73a66-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73a66-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73a66-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-116">The call timed out.</span></span>|  
|<span data-ttu-id="73a66-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73a66-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73a66-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73a66-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73a66-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73a66-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73a66-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73a66-121">E_FAIL</span></span>|<span data-ttu-id="73a66-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73a66-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73a66-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a66-125">설명</span><span class="sxs-lookup"><span data-stu-id="73a66-125">Remarks</span></span>  

 <span data-ttu-id="73a66-126">일반적으로 CLR은 `IHostTaskManager::Sleep` <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 사용자 코드에서가 호출 될 때를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73a66-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73a66-127">Requirements</span></span>  

 <span data-ttu-id="73a66-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73a66-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a66-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="73a66-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73a66-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73a66-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73a66-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73a66-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a66-132">참조</span><span class="sxs-lookup"><span data-stu-id="73a66-132">See also</span></span>

- [<span data-ttu-id="73a66-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73a66-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="73a66-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73a66-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="73a66-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73a66-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="73a66-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73a66-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
