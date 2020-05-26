---
title: IHostGCManager::SuspensionEnding 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
ms.openlocfilehash: 4c05ee766bf40be2e9c39f01c7e1b16cb9fab50d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804844"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="a09fb-102">IHostGCManager::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="a09fb-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="a09fb-103">CLR (공용 언어 런타임)에서 가비지 컬렉션에 대해 일시 중단 된 스레드의 작업 실행을 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="a09fb-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a09fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a09fb-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="a09fb-106">진행 스레드를 다시 시작 하는 방금 완료 된 가비지 컬렉션 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a09fb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a09fb-107">Return Value</span></span>  
  
|<span data-ttu-id="a09fb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a09fb-108">HRESULT</span></span>|<span data-ttu-id="a09fb-109">Description</span><span class="sxs-lookup"><span data-stu-id="a09fb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a09fb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a09fb-110">S_OK</span></span>|<span data-ttu-id="a09fb-111">`SuspensionEnding`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="a09fb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a09fb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a09fb-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a09fb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a09fb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a09fb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-115">The call timed out.</span></span>|  
|<span data-ttu-id="a09fb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a09fb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a09fb-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a09fb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a09fb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a09fb-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a09fb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a09fb-120">E_FAIL</span></span>|<span data-ttu-id="a09fb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a09fb-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a09fb-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a09fb-124">설명</span><span class="sxs-lookup"><span data-stu-id="a09fb-124">Remarks</span></span>  
 <span data-ttu-id="a09fb-125">CLR은 `SuspensionEnding` 가비지 수집을 수행한 후를 호출 하 여 스레드가 실행을 다시 시작 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a09fb-126">메서드 호출이 수행 된 스레드를 다시 예약 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a09fb-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a09fb-127">Requirements</span></span>  
 <span data-ttu-id="a09fb-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a09fb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a09fb-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a09fb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a09fb-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a09fb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a09fb-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a09fb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09fb-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a09fb-132">See also</span></span>

- [<span data-ttu-id="a09fb-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a09fb-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a09fb-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a09fb-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a09fb-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a09fb-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a09fb-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a09fb-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="a09fb-137">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a09fb-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
