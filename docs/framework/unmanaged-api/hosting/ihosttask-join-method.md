---
title: IHostTask::Join 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: 20919bd9889408821cf57817082e3c7d5cebc240
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503923"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="fb3cb-102">IHostTask::Join 메서드</span><span class="sxs-lookup"><span data-stu-id="fb3cb-102">IHostTask::Join Method</span></span>
<span data-ttu-id="fb3cb-103">현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 되는 작업이 완료 되거나 지정 된 시간 간격이 경과 되거나 [IHostTask:: Alert](ihosttask-alert-method.md) 이 호출 될 때까지 호출 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-103">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb3cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb3cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb3cb-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="fb3cb-106">진행 태스크가 종료 될 때까지 대기 하는 시간 간격 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="fb3cb-107">작업이 종료 되기 전에이 간격이 경과 하면 호출 하는 작업이 차단 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="fb3cb-108">진행 [WAIT_OPTION](wait-option-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="fb3cb-109">WAIT_ALERTABLE 값은 `Alert` 가 경과 하기 전에가 호출 되 면 호스트에 게 작업을 절전 모드 해제 하도록 지시 합니다 `milliseconds` .</span><span class="sxs-lookup"><span data-stu-id="fb3cb-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb3cb-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb3cb-110">Return Value</span></span>  
  
|<span data-ttu-id="fb3cb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb3cb-111">HRESULT</span></span>|<span data-ttu-id="fb3cb-112">설명</span><span class="sxs-lookup"><span data-stu-id="fb3cb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb3cb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb3cb-113">S_OK</span></span>|<span data-ttu-id="fb3cb-114">`Join`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="fb3cb-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb3cb-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb3cb-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb3cb-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb3cb-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb3cb-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-118">The call timed out.</span></span>|  
|<span data-ttu-id="fb3cb-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb3cb-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb3cb-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb3cb-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb3cb-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb3cb-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트가 취소 되었거나 현재 `IHostTask` 인스턴스가 태스크와 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="fb3cb-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb3cb-123">E_FAIL</span></span>|<span data-ttu-id="fb3cb-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb3cb-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb3cb-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb3cb-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb3cb-127">Requirements</span></span>  
 <span data-ttu-id="fb3cb-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb3cb-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb3cb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb3cb-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb3cb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb3cb-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3cb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3cb-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb3cb-132">See also</span></span>

- [<span data-ttu-id="fb3cb-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb3cb-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fb3cb-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb3cb-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fb3cb-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb3cb-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fb3cb-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb3cb-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="fb3cb-137">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="fb3cb-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
