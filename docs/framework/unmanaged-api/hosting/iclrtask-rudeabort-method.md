---
title: ICLRTask::RudeAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691049"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="fafb6-102">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="fafb6-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="fafb6-103">현재 [ICLRTask 인터페이스](iclrtask-interface.md) 인스턴스로 표시 되는 작업을 즉시 중단 하도록 CLR (공용 언어 런타임)에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fafb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="fafb6-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="fafb6-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="fafb6-105">Return Value</span></span>  
  
|<span data-ttu-id="fafb6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fafb6-106">HRESULT</span></span>|<span data-ttu-id="fafb6-107">설명</span><span class="sxs-lookup"><span data-stu-id="fafb6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fafb6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fafb6-108">S_OK</span></span>|<span data-ttu-id="fafb6-109">`RudeAbort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="fafb6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fafb6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fafb6-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fafb6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fafb6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fafb6-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-113">The call timed out.</span></span>|  
|<span data-ttu-id="fafb6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fafb6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fafb6-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fafb6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fafb6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fafb6-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fafb6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fafb6-118">E_FAIL</span></span>|<span data-ttu-id="fafb6-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fafb6-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fafb6-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fafb6-122">설명</span><span class="sxs-lookup"><span data-stu-id="fafb6-122">Remarks</span></span>  

 <span data-ttu-id="fafb6-123">호스트는 `RudeAbort` 를 호출 하 여 작업을 즉시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="fafb6-124">종료자 및 예외 처리 루틴은 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fafb6-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fafb6-125">Requirements</span></span>  

 <span data-ttu-id="fafb6-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fafb6-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fafb6-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fafb6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fafb6-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fafb6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fafb6-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fafb6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafb6-130">참조</span><span class="sxs-lookup"><span data-stu-id="fafb6-130">See also</span></span>

- [<span data-ttu-id="fafb6-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafb6-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fafb6-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafb6-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fafb6-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafb6-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fafb6-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fafb6-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
