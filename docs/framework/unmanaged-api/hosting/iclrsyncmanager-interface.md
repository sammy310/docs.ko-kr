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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3e4affa363083ce55ac3764c26412a0d60ba3f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203095"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="ffd75-102">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffd75-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="ffd75-103">요청 된 작업에 대 한 정보를 가져오려면 호스트가 동기화 구현에서 교착 상태를 감지 하는 데 사용할 수 있는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd75-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffd75-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-104">Methods</span></span>  
  
|<span data-ttu-id="ffd75-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-105">Method</span></span>|<span data-ttu-id="ffd75-106">설명</span><span class="sxs-lookup"><span data-stu-id="ffd75-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffd75-107">CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="ffd75-108">CLR (공용 언어 런타임)에서 판독기-기록기 잠금을 대기 하는 태스크 집합을 결정 하는 데 호스트에 대 한 반복기를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd75-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="ffd75-109">DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="ffd75-110">CLR 삭제를 호출 하 여 생성 된 반복기는 요청 `CreateRWLockOwnerIterator`합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd75-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="ffd75-111">GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="ffd75-112">지정 된 모니터를 소유 하는 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffd75-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="ffd75-113">GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="ffd75-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="ffd75-114">현재 판독기-기록기 잠금을 기다리고 있는 다음 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffd75-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffd75-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffd75-115">Requirements</span></span>  
 <span data-ttu-id="ffd75-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ffd75-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffd75-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffd75-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffd75-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ffd75-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ffd75-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ffd75-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ffd75-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ffd75-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="ffd75-121">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffd75-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="ffd75-122">관리되는 스레딩과 관리되지 않는 스레딩</span><span class="sxs-lookup"><span data-stu-id="ffd75-122">Managed and Unmanaged Threading</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [<span data-ttu-id="ffd75-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffd75-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
