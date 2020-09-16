---
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
ms.openlocfilehash: b0b9c0b7d178557806a9ab2893bff2d34dc408ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557738"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="29ed5-102">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29ed5-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="29ed5-103">호스트에서 요청 된 작업에 대 한 정보를 가져오고 해당 동기화 구현에서 교착 상태를 검색할 수 있도록 하는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29ed5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-104">Methods</span></span>  
  
|<span data-ttu-id="29ed5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-105">Method</span></span>|<span data-ttu-id="29ed5-106">Description</span><span class="sxs-lookup"><span data-stu-id="29ed5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29ed5-107">CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="29ed5-108">CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="29ed5-109">DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="29ed5-110">을 호출 하 여 만든 반복기를 CLR에서 삭제 하도록 요청 `CreateRWLockOwnerIterator` 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="29ed5-111">GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="29ed5-112">지정 된 모니터를 소유 하는 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="29ed5-113">GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="29ed5-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="29ed5-114">현재 판독기-작성기 잠금을 기다리는 다음 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29ed5-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29ed5-115">Requirements</span></span>  
 <span data-ttu-id="29ed5-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29ed5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ed5-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29ed5-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29ed5-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ed5-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29ed5-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ed5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ed5-120">참조</span><span class="sxs-lookup"><span data-stu-id="29ed5-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="29ed5-121">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29ed5-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="29ed5-122">[관리되는 스레딩과 관리되지 않는 스레딩](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="29ed5-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="29ed5-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29ed5-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
