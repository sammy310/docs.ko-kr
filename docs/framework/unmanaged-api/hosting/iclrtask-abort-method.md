---
description: '자세한 정보: ICLRTask:: Abort 메서드'
title: ICLRTask::Abort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: ddb761ac50d7401180355236aa8fdc22cca1c580
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785011"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="378ea-103">ICLRTask::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="378ea-103">ICLRTask::Abort Method</span></span>

<span data-ttu-id="378ea-104">CLR (공용 언어 런타임)이 현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업을 중단 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-104">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378ea-105">구문</span><span class="sxs-lookup"><span data-stu-id="378ea-105">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="378ea-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="378ea-106">Return Value</span></span>  
  
|<span data-ttu-id="378ea-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="378ea-107">HRESULT</span></span>|<span data-ttu-id="378ea-108">설명</span><span class="sxs-lookup"><span data-stu-id="378ea-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="378ea-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="378ea-109">S_OK</span></span>|<span data-ttu-id="378ea-110">`Abort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-110">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="378ea-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="378ea-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="378ea-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="378ea-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="378ea-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="378ea-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-114">The call timed out.</span></span>|  
|<span data-ttu-id="378ea-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="378ea-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="378ea-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="378ea-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="378ea-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="378ea-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="378ea-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="378ea-119">E_FAIL</span></span>|<span data-ttu-id="378ea-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="378ea-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="378ea-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="378ea-123">설명</span><span class="sxs-lookup"><span data-stu-id="378ea-123">Remarks</span></span>  

 <span data-ttu-id="378ea-124">호스트가를 호출 하면 CLR에서이 발생 <xref:System.Threading.ThreadAbortException> `Abort` 합니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-124">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="378ea-125">종료자 또는 예외 처리 메커니즘과 같은 사용자 코드가 실행 될 때까지 기다리지 않고 예외 정보가 초기화 된 후 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-125">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="378ea-126">따라서에 대 한 호출은 `Abort` 빠르게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-126">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378ea-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="378ea-127">Requirements</span></span>  

 <span data-ttu-id="378ea-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="378ea-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="378ea-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="378ea-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="378ea-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="378ea-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="378ea-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="378ea-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378ea-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="378ea-132">See also</span></span>

- [<span data-ttu-id="378ea-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ea-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="378ea-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ea-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="378ea-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ea-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="378ea-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ea-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
