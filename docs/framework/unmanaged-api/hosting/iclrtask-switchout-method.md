---
description: '자세한 정보: ICLRTask:: SwitchOut 메서드'
title: ICLRTask::SwitchOut 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 6c491c4d9005fb850c5adecd025730f1ea71f513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784940"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="72185-103">ICLRTask::SwitchOut 메서드</span><span class="sxs-lookup"><span data-stu-id="72185-103">ICLRTask::SwitchOut Method</span></span>

<span data-ttu-id="72185-104">현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업이 더 이상 작동 하지 않는 상태임을 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72185-104">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72185-105">구문</span><span class="sxs-lookup"><span data-stu-id="72185-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="72185-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="72185-106">Return Value</span></span>  
  
|<span data-ttu-id="72185-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72185-107">HRESULT</span></span>|<span data-ttu-id="72185-108">설명</span><span class="sxs-lookup"><span data-stu-id="72185-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72185-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="72185-109">S_OK</span></span>|<span data-ttu-id="72185-110">`SwitchOut` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-110">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="72185-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72185-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72185-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72185-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72185-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72185-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-114">The call timed out.</span></span>|  
|<span data-ttu-id="72185-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72185-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72185-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72185-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72185-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72185-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72185-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72185-119">E_FAIL</span></span>|<span data-ttu-id="72185-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72185-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72185-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72185-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72185-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72185-123">설명</span><span class="sxs-lookup"><span data-stu-id="72185-123">Remarks</span></span>  

 <span data-ttu-id="72185-124">호스트는 `SwitchOut` 를 호출 하 여 현재 인스턴스가 나타내는 작업의 실행을 일시적으로 중지 했음을 CLR에 알리고 작업을 다시 `ICLRTask` 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="72185-124">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72185-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72185-125">Requirements</span></span>  

 <span data-ttu-id="72185-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72185-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72185-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="72185-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72185-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72185-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72185-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72185-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72185-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72185-130">See also</span></span>

- [<span data-ttu-id="72185-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72185-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="72185-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72185-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="72185-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72185-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="72185-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72185-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
