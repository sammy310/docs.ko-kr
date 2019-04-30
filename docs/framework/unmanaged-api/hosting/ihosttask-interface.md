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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992838"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="ac188-102">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac188-102">IHostTask Interface</span></span>
<span data-ttu-id="ac188-103">CLR (공용 언어 런타임) 작업을 관리 하는 호스트와 통신할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac188-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac188-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-104">Methods</span></span>  
  
|<span data-ttu-id="ac188-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-105">Method</span></span>|<span data-ttu-id="ac188-106">설명</span><span class="sxs-lookup"><span data-stu-id="ac188-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac188-107">Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="ac188-108">현재 작업의 시작을 호스트 하는 요청 `IHostTask` 인스턴스 작업을 중단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac188-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="ac188-109">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="ac188-110">현재 태스크의 스레드 우선 순위 수준을 가져옵니다 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ac188-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="ac188-111">Join 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="ac188-112">현재 작업까지 호출 작업을 차단 `IHostTask` 인스턴스가 완료 되 면 지정 된 시간 간격이 경과 하면 또는 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac188-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="ac188-113">SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="ac188-114">연결 프로그램 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 현재 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ac188-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="ac188-115">SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="ac188-116">현재 태스크에 대 한 호스트에서 스레드 우선 순위를 조정 하도록 요청 수준 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ac188-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="ac188-117">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="ac188-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="ac188-118">호스트 작업 요청 현재 `IHostTask` 코드를 실행할 수 있는 라이브 상태로 일시 중단 된에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ac188-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac188-119">설명</span><span class="sxs-lookup"><span data-stu-id="ac188-119">Remarks</span></span>  
 <span data-ttu-id="ac188-120">정의한 메서드를 호출 하는 CLR `IHostTask` 수준 등 작업을 시작 하려면 해당 스레드 우선 순위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac188-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac188-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac188-121">Requirements</span></span>  
 <span data-ttu-id="ac188-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac188-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac188-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac188-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac188-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ac188-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac188-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac188-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac188-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac188-126">See also</span></span>

- [<span data-ttu-id="ac188-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac188-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ac188-128">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac188-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ac188-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac188-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ac188-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac188-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
