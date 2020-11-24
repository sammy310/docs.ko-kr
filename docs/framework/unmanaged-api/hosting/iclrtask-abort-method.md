---
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
ms.openlocfilehash: aadbbb5fc6abd3829f14670e42149174f6ef238d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690852"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="22bd3-102">ICLRTask::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="22bd3-102">ICLRTask::Abort Method</span></span>

<span data-ttu-id="22bd3-103">CLR (공용 언어 런타임)이 현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업을 중단 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22bd3-104">구문</span><span class="sxs-lookup"><span data-stu-id="22bd3-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="22bd3-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="22bd3-105">Return Value</span></span>  
  
|<span data-ttu-id="22bd3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22bd3-106">HRESULT</span></span>|<span data-ttu-id="22bd3-107">설명</span><span class="sxs-lookup"><span data-stu-id="22bd3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22bd3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="22bd3-108">S_OK</span></span>|<span data-ttu-id="22bd3-109">`Abort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="22bd3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22bd3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22bd3-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22bd3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22bd3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22bd3-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-113">The call timed out.</span></span>|  
|<span data-ttu-id="22bd3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22bd3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22bd3-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22bd3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22bd3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22bd3-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22bd3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22bd3-118">E_FAIL</span></span>|<span data-ttu-id="22bd3-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22bd3-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22bd3-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22bd3-122">설명</span><span class="sxs-lookup"><span data-stu-id="22bd3-122">Remarks</span></span>  

 <span data-ttu-id="22bd3-123">호스트가를 호출 하면 CLR에서이 발생 <xref:System.Threading.ThreadAbortException> `Abort` 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="22bd3-124">종료자 또는 예외 처리 메커니즘과 같은 사용자 코드가 실행 될 때까지 기다리지 않고 예외 정보가 초기화 된 후 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="22bd3-125">따라서에 대 한 호출은 `Abort` 빠르게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22bd3-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22bd3-126">Requirements</span></span>  

 <span data-ttu-id="22bd3-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22bd3-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22bd3-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="22bd3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22bd3-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bd3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22bd3-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22bd3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bd3-131">참조</span><span class="sxs-lookup"><span data-stu-id="22bd3-131">See also</span></span>

- [<span data-ttu-id="22bd3-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22bd3-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="22bd3-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22bd3-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="22bd3-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22bd3-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="22bd3-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22bd3-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
