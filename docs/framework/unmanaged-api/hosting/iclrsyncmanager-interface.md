---
description: '자세히 알아보기: ICLRSyncManager 인터페이스'
title: ICLRSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: 188d1c913d75666aea09b17244012401d377fa10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785016"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="a883d-103">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a883d-103">ICLRSyncManager Interface</span></span>

<span data-ttu-id="a883d-104">호스트에서 요청 된 작업에 대 한 정보를 가져오고 해당 동기화 구현에서 교착 상태를 검색할 수 있도록 하는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-104">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a883d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-105">Methods</span></span>  
  
|<span data-ttu-id="a883d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-106">Method</span></span>|<span data-ttu-id="a883d-107">설명</span><span class="sxs-lookup"><span data-stu-id="a883d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a883d-108">CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-108">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="a883d-109">CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-109">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="a883d-110">DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-110">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="a883d-111">을 호출 하 여 만든 반복기를 CLR에서 삭제 하도록 요청 `CreateRWLockOwnerIterator` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-111">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="a883d-112">GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-112">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="a883d-113">지정 된 모니터를 소유 하는 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-113">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="a883d-114">GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="a883d-114">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="a883d-115">현재 판독기-작성기 잠금을 기다리는 다음 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-115">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a883d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a883d-116">Requirements</span></span>  

 <span data-ttu-id="a883d-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a883d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a883d-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a883d-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a883d-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a883d-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a883d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a883d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a883d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a883d-121">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="a883d-122">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a883d-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="a883d-123">[관리되는 스레딩과 관리되지 않는 스레딩](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a883d-123">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="a883d-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a883d-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
