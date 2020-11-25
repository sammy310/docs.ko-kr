---
title: IHostTask 인터페이스
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699224"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="1dcd8-102">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dcd8-102">IHostTask Interface</span></span>

<span data-ttu-id="1dcd8-103">CLR (공용 언어 런타임)이 호스트와 통신 하 여 작업을 관리 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1dcd8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-104">Methods</span></span>  
  
|<span data-ttu-id="1dcd8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-105">Method</span></span>|<span data-ttu-id="1dcd8-106">설명</span><span class="sxs-lookup"><span data-stu-id="1dcd8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1dcd8-107">Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="1dcd8-108">호스트가 현재 인스턴스로 표시 된 작업의 절전 모드를 해제 `IHostTask` 하도록 요청 하므로 작업이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="1dcd8-109">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="1dcd8-110">현재 인스턴스가 나타내는 작업의 스레드 우선 순위 수준을 가져옵니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="1dcd8-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1dcd8-111">Join 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-111">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="1dcd8-112">현재 인스턴스가 나타내는 작업이 `IHostTask` 완료 되거나 지정 된 시간 간격이 경과 되거나 [IHostTask:: Alert](ihosttask-alert-method.md) 이 호출 될 때까지 호출 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="1dcd8-113">SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-113">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="1dcd8-114">[ICLRTask 인터페이스](iclrtask-interface.md) 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1dcd8-115">SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="1dcd8-116">호스트가 현재 인스턴스로 표시 되는 작업에 대 한 스레드 우선 순위 수준을 조정 하도록 요청 합니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="1dcd8-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="1dcd8-117">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="1dcd8-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="1dcd8-118">현재 인스턴스가 나타내는 작업을 `IHostTask` 일시 중단 상태에서 활성 상태로 전환 하 여 코드를 실행할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dcd8-119">설명</span><span class="sxs-lookup"><span data-stu-id="1dcd8-119">Remarks</span></span>  

 <span data-ttu-id="1dcd8-120">CLR은에 의해 정의 된 메서드를 호출 `IHostTask` 하 여 작업을 시작 하 고, 스레드 우선 순위 수준을 설정 하는 등의 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dcd8-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1dcd8-121">Requirements</span></span>  

 <span data-ttu-id="1dcd8-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dcd8-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1dcd8-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1dcd8-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dcd8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dcd8-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dcd8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dcd8-126">참조</span><span class="sxs-lookup"><span data-stu-id="1dcd8-126">See also</span></span>

- [<span data-ttu-id="1dcd8-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dcd8-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1dcd8-128">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dcd8-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1dcd8-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dcd8-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1dcd8-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dcd8-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
