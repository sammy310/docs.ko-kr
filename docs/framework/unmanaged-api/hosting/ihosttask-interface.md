---
description: '자세한 정보: IHostTask 인터페이스'
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
ms.openlocfilehash: c46bbdd2e881c20d1ffd634bec8ddfa3b70b0f82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784667"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="6fd39-103">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fd39-103">IHostTask Interface</span></span>

<span data-ttu-id="6fd39-104">CLR (공용 언어 런타임)이 호스트와 통신 하 여 작업을 관리 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-104">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fd39-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-105">Methods</span></span>  
  
|<span data-ttu-id="6fd39-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-106">Method</span></span>|<span data-ttu-id="6fd39-107">설명</span><span class="sxs-lookup"><span data-stu-id="6fd39-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fd39-108">Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-108">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="6fd39-109">호스트가 현재 인스턴스로 표시 된 작업의 절전 모드를 해제 `IHostTask` 하도록 요청 하므로 작업이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-109">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="6fd39-110">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-110">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="6fd39-111">현재 인스턴스가 나타내는 작업의 스레드 우선 순위 수준을 가져옵니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="6fd39-111">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6fd39-112">Join 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-112">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="6fd39-113">현재 인스턴스가 나타내는 작업이 `IHostTask` 완료 되거나 지정 된 시간 간격이 경과 되거나 [IHostTask:: Alert](ihosttask-alert-method.md) 이 호출 될 때까지 호출 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-113">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="6fd39-114">SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-114">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="6fd39-115">[ICLRTask 인터페이스](iclrtask-interface.md) 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-115">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6fd39-116">SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-116">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="6fd39-117">호스트가 현재 인스턴스로 표시 되는 작업에 대 한 스레드 우선 순위 수준을 조정 하도록 요청 합니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="6fd39-117">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6fd39-118">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="6fd39-118">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="6fd39-119">현재 인스턴스가 나타내는 작업을 `IHostTask` 일시 중단 상태에서 활성 상태로 전환 하 여 코드를 실행할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-119">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fd39-120">설명</span><span class="sxs-lookup"><span data-stu-id="6fd39-120">Remarks</span></span>  

 <span data-ttu-id="6fd39-121">CLR은에 의해 정의 된 메서드를 호출 `IHostTask` 하 여 작업을 시작 하 고, 스레드 우선 순위 수준을 설정 하는 등의 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-121">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd39-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fd39-122">Requirements</span></span>  

 <span data-ttu-id="6fd39-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd39-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd39-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6fd39-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fd39-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fd39-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fd39-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd39-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd39-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fd39-127">See also</span></span>

- [<span data-ttu-id="6fd39-128">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fd39-128">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6fd39-129">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fd39-129">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6fd39-130">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fd39-130">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6fd39-131">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fd39-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
