---
description: '자세한 정보: ICLRTask:: ExitTask 메서드'
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
ms.openlocfilehash: 267b7f284ccac5b535a72dab425c035b6c689361
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784966"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="42add-103">ICLRTask::ExitTask 메서드</span><span class="sxs-lookup"><span data-stu-id="42add-103">ICLRTask::ExitTask Method</span></span>

<span data-ttu-id="42add-104">현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업이 종료 되 고 작업을 정상적으로 종료 하려고 시도 하는 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="42add-104">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42add-105">구문</span><span class="sxs-lookup"><span data-stu-id="42add-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="42add-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="42add-106">Return Value</span></span>  
  
|<span data-ttu-id="42add-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42add-107">HRESULT</span></span>|<span data-ttu-id="42add-108">설명</span><span class="sxs-lookup"><span data-stu-id="42add-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42add-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="42add-109">S_OK</span></span>|<span data-ttu-id="42add-110">`ExitTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-110">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="42add-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42add-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42add-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42add-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42add-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42add-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-114">The call timed out.</span></span>|  
|<span data-ttu-id="42add-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42add-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42add-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42add-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42add-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42add-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42add-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42add-119">E_FAIL</span></span>|<span data-ttu-id="42add-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42add-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42add-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42add-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42add-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42add-123">설명</span><span class="sxs-lookup"><span data-stu-id="42add-123">Remarks</span></span>  

 <span data-ttu-id="42add-124">`ExitTask` 관리 되지 않는 형식 라이브러리에서 스레드를 분리 하는 것과 비슷한 방식으로 작업의 완전 한 종료를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="42add-124">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42add-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42add-125">Requirements</span></span>  

 <span data-ttu-id="42add-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42add-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42add-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="42add-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42add-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42add-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42add-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42add-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42add-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42add-130">See also</span></span>

- [<span data-ttu-id="42add-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42add-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="42add-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42add-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="42add-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42add-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="42add-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42add-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
