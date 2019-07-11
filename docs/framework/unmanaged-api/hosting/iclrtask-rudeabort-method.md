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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7750d50b772ff17cf9dcd05de2e2f34556714e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770472"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="4600d-102">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="4600d-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="4600d-103">CLR (공용 언어 런타임)를 나타내는 현재 작업을 중단 하도록 지시 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 즉시 및 무조건 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4600d-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4600d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4600d-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="4600d-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="4600d-105">Return Value</span></span>  
  
|<span data-ttu-id="4600d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4600d-106">HRESULT</span></span>|<span data-ttu-id="4600d-107">Description</span><span class="sxs-lookup"><span data-stu-id="4600d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4600d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4600d-108">S_OK</span></span>|<span data-ttu-id="4600d-109">`RudeAbort` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="4600d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4600d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4600d-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4600d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4600d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4600d-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-113">The call timed out.</span></span>|  
|<span data-ttu-id="4600d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4600d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4600d-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4600d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4600d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4600d-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4600d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4600d-118">E_FAIL</span></span>|<span data-ttu-id="4600d-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4600d-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4600d-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4600d-122">설명</span><span class="sxs-lookup"><span data-stu-id="4600d-122">Remarks</span></span>  
 <span data-ttu-id="4600d-123">호스트 `RudeAbort` 즉시 작업을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="4600d-124">종료자 및 예외 처리 루틴 실행을 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4600d-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4600d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4600d-125">Requirements</span></span>  
 <span data-ttu-id="4600d-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4600d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4600d-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4600d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4600d-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4600d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4600d-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4600d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4600d-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="4600d-130">See also</span></span>

- [<span data-ttu-id="4600d-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4600d-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4600d-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4600d-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4600d-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4600d-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4600d-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4600d-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
