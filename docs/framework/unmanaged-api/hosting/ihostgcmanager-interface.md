---
description: '자세히 알아보기: IHostGCManager 인터페이스'
title: IHostGCManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: da229c04eb5f5a27c34c133b5c88183d00f47c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708660"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="9534f-103">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-103">IHostGCManager Interface</span></span>

<span data-ttu-id="9534f-104">CLR (공용 언어 런타임)에서 구현 하는 가비지 수집 메커니즘에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9534f-104">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="9534f-105">구성원</span><span class="sxs-lookup"><span data-stu-id="9534f-105">Members</span></span>  
  
|<span data-ttu-id="9534f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9534f-106">Member</span></span>|<span data-ttu-id="9534f-107">설명</span><span class="sxs-lookup"><span data-stu-id="9534f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9534f-108">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="9534f-108">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="9534f-109">CLR이 가비지 컬렉션에 대해 일시 중단 된 스레드의 작업 실행을 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9534f-109">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="9534f-110">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="9534f-110">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="9534f-111">가비지 수집을 수행 하기 위해 CLR이 태스크의 실행을 일시 중단 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9534f-111">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="9534f-112">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="9534f-112">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="9534f-113">메서드 호출이 수행 된 스레드가 가비지 컬렉션에 대해 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9534f-113">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9534f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9534f-114">Requirements</span></span>  

 <span data-ttu-id="9534f-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9534f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9534f-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9534f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9534f-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9534f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9534f-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9534f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9534f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9534f-119">See also</span></span>

- [<span data-ttu-id="9534f-120">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-120">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9534f-121">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-121">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9534f-122">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-122">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9534f-123">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-123">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="9534f-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9534f-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
