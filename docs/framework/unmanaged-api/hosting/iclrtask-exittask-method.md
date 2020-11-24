---
title: ICLRTask::ExitTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: bcd1cac47e4b59cc47c95145f0ccf60c92ea54fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690841"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="1f6fb-102">ICLRTask::ExitTask 메서드</span><span class="sxs-lookup"><span data-stu-id="1f6fb-102">ICLRTask::ExitTask Method</span></span>

<span data-ttu-id="1f6fb-103">현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업이 종료 되 고 작업을 정상적으로 종료 하려고 시도 하는 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f6fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f6fb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1f6fb-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="1f6fb-105">Return Value</span></span>  
  
|<span data-ttu-id="1f6fb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f6fb-106">HRESULT</span></span>|<span data-ttu-id="1f6fb-107">설명</span><span class="sxs-lookup"><span data-stu-id="1f6fb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f6fb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f6fb-108">S_OK</span></span>|<span data-ttu-id="1f6fb-109">`ExitTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="1f6fb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f6fb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f6fb-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f6fb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f6fb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f6fb-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-113">The call timed out.</span></span>|  
|<span data-ttu-id="1f6fb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f6fb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f6fb-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f6fb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f6fb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f6fb-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f6fb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f6fb-118">E_FAIL</span></span>|<span data-ttu-id="1f6fb-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f6fb-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f6fb-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f6fb-122">설명</span><span class="sxs-lookup"><span data-stu-id="1f6fb-122">Remarks</span></span>  

 <span data-ttu-id="1f6fb-123">`ExitTask` 관리 되지 않는 형식 라이브러리에서 스레드를 분리 하는 것과 비슷한 방식으로 작업의 완전 한 종료를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f6fb-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f6fb-124">Requirements</span></span>  

 <span data-ttu-id="1f6fb-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f6fb-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f6fb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f6fb-127">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f6fb-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f6fb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6fb-129">참조</span><span class="sxs-lookup"><span data-stu-id="1f6fb-129">See also</span></span>

- [<span data-ttu-id="1f6fb-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1f6fb-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1f6fb-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1f6fb-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
