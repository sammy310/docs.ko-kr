---
description: '다음에 대 한 자세한 정보: ICLRTask:: Dedeabort 메서드'
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
ms.openlocfilehash: f152f11ce41018b458ed2cb4df255e486ad54da0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636886"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="cee4e-103">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="cee4e-103">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="cee4e-104">현재 [ICLRTask 인터페이스](iclrtask-interface.md) 인스턴스로 표시 되는 작업을 즉시 중단 하도록 CLR (공용 언어 런타임)에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-104">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="cee4e-105">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="cee4e-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="cee4e-106">Return Value</span></span>  
  
|<span data-ttu-id="cee4e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cee4e-107">HRESULT</span></span>|<span data-ttu-id="cee4e-108">설명</span><span class="sxs-lookup"><span data-stu-id="cee4e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cee4e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="cee4e-109">S_OK</span></span>|<span data-ttu-id="cee4e-110">`RudeAbort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-110">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="cee4e-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cee4e-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cee4e-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cee4e-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cee4e-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cee4e-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-114">The call timed out.</span></span>|  
|<span data-ttu-id="cee4e-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cee4e-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cee4e-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cee4e-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cee4e-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cee4e-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cee4e-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cee4e-119">E_FAIL</span></span>|<span data-ttu-id="cee4e-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cee4e-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cee4e-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cee4e-123">설명</span><span class="sxs-lookup"><span data-stu-id="cee4e-123">Remarks</span></span>  

 <span data-ttu-id="cee4e-124">호스트는 `RudeAbort` 를 호출 하 여 작업을 즉시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-124">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="cee4e-125">종료자 및 예외 처리 루틴은 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-125">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee4e-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cee4e-126">Requirements</span></span>  

 <span data-ttu-id="cee4e-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee4e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cee4e-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cee4e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cee4e-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee4e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cee4e-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cee4e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee4e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cee4e-131">See also</span></span>

- [<span data-ttu-id="cee4e-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cee4e-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cee4e-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cee4e-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cee4e-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cee4e-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="cee4e-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cee4e-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
