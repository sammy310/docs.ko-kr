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
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176333"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="82841-102">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="82841-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="82841-103">공통 언어 런타임(CLR)은 현재 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스로 표시되는 작업을 즉시 무조건 중단하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="82841-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82841-104">구문</span><span class="sxs-lookup"><span data-stu-id="82841-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="82841-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="82841-105">Return Value</span></span>  
  
|<span data-ttu-id="82841-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82841-106">HRESULT</span></span>|<span data-ttu-id="82841-107">Description</span><span class="sxs-lookup"><span data-stu-id="82841-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82841-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="82841-108">S_OK</span></span>|<span data-ttu-id="82841-109">`RudeAbort`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="82841-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="82841-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82841-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82841-111">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="82841-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82841-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82841-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82841-113">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-113">The call timed out.</span></span>|  
|<span data-ttu-id="82841-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82841-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82841-115">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82841-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82841-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82841-117">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82841-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82841-118">E_FAIL</span></span>|<span data-ttu-id="82841-119">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82841-120">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82841-121">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="82841-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82841-122">설명</span><span class="sxs-lookup"><span data-stu-id="82841-122">Remarks</span></span>  
 <span data-ttu-id="82841-123">호스트는 `RudeAbort` 작업을 즉시 중단하도록 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="82841-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="82841-124">종료자 및 예외 처리 루틴이 실행되지 는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82841-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82841-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82841-125">Requirements</span></span>  
 <span data-ttu-id="82841-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82841-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82841-127">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="82841-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82841-128">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="82841-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82841-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82841-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82841-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82841-130">See also</span></span>

- [<span data-ttu-id="82841-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82841-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="82841-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82841-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="82841-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82841-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="82841-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82841-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
