---
description: '자세히 알아보기: IHostGCManager:: SuspensionEnding 메서드'
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
ms.openlocfilehash: 43ec3db76e6e6448719f9c40ef2476da4e2ccf9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708623"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="37f95-103">IHostGCManager::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="37f95-103">IHostGCManager::SuspensionEnding Method</span></span>

<span data-ttu-id="37f95-104">CLR (공용 언어 런타임)에서 가비지 컬렉션에 대해 일시 중단 된 스레드의 작업 실행을 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-104">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f95-105">구문</span><span class="sxs-lookup"><span data-stu-id="37f95-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37f95-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37f95-106">Parameters</span></span>  

 `generation`  
 <span data-ttu-id="37f95-107">진행 스레드를 다시 시작 하는 방금 완료 된 가비지 컬렉션 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-107">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37f95-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="37f95-108">Return Value</span></span>  
  
|<span data-ttu-id="37f95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37f95-109">HRESULT</span></span>|<span data-ttu-id="37f95-110">설명</span><span class="sxs-lookup"><span data-stu-id="37f95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37f95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37f95-111">S_OK</span></span>|<span data-ttu-id="37f95-112">`SuspensionEnding` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-112">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="37f95-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37f95-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37f95-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37f95-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37f95-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37f95-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-116">The call timed out.</span></span>|  
|<span data-ttu-id="37f95-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37f95-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37f95-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37f95-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37f95-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37f95-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37f95-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37f95-121">E_FAIL</span></span>|<span data-ttu-id="37f95-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37f95-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37f95-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37f95-125">설명</span><span class="sxs-lookup"><span data-stu-id="37f95-125">Remarks</span></span>  

 <span data-ttu-id="37f95-126">CLR은 `SuspensionEnding` 가비지 수집을 수행한 후를 호출 하 여 스레드가 실행을 다시 시작 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-126">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37f95-127">메서드 호출이 수행 된 스레드를 다시 예약 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-127">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f95-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37f95-128">Requirements</span></span>  

 <span data-ttu-id="37f95-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37f95-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37f95-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="37f95-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37f95-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f95-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37f95-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37f95-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f95-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37f95-133">See also</span></span>

- [<span data-ttu-id="37f95-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f95-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="37f95-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f95-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="37f95-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f95-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="37f95-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f95-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="37f95-138">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f95-138">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
