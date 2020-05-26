---
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
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804850"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="2124d-102">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-102">IHostGCManager Interface</span></span>
<span data-ttu-id="2124d-103">CLR (공용 언어 런타임)에서 구현 하는 가비지 수집 메커니즘에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2124d-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="2124d-104">멤버</span><span class="sxs-lookup"><span data-stu-id="2124d-104">Members</span></span>  
  
|<span data-ttu-id="2124d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2124d-105">Member</span></span>|<span data-ttu-id="2124d-106">설명</span><span class="sxs-lookup"><span data-stu-id="2124d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2124d-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="2124d-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="2124d-108">CLR이 가비지 컬렉션에 대해 일시 중단 된 스레드의 작업 실행을 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2124d-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="2124d-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="2124d-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="2124d-110">가비지 수집을 수행 하기 위해 CLR이 태스크의 실행을 일시 중단 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2124d-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="2124d-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="2124d-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="2124d-112">메서드 호출이 수행 된 스레드가 가비지 컬렉션에 대해 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2124d-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2124d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2124d-113">Requirements</span></span>  
 <span data-ttu-id="2124d-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2124d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2124d-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2124d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2124d-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2124d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2124d-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2124d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2124d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2124d-118">See also</span></span>

- [<span data-ttu-id="2124d-119">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="2124d-120">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="2124d-121">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="2124d-122">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="2124d-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2124d-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
