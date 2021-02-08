---
description: '자세히 알아보기: IHostAutoEvent 인터페이스'
title: IHostAutoEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: 4aea282dbe2067d50214b237650ba01fb8bf22a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789491"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="a4bf2-103">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bf2-103">IHostAutoEvent Interface</span></span>

<span data-ttu-id="a4bf2-104">자동 재설정 이벤트의 호스트 구현에 대 한 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf2-104">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4bf2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a4bf2-105">Methods</span></span>  
  
|<span data-ttu-id="a4bf2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a4bf2-106">Method</span></span>|<span data-ttu-id="a4bf2-107">설명</span><span class="sxs-lookup"><span data-stu-id="a4bf2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4bf2-108">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="a4bf2-108">Set Method</span></span>](ihostautoevent-set-method.md)|<span data-ttu-id="a4bf2-109">현재 인스턴스를 `IHostAutoEvent` 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf2-109">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a4bf2-110">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="a4bf2-110">Wait Method</span></span>](ihostautoevent-wait-method.md)|<span data-ttu-id="a4bf2-111">`IHostAutoEvent`이벤트가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 현재 인스턴스가 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf2-111">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4bf2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4bf2-112">Requirements</span></span>  

 <span data-ttu-id="a4bf2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4bf2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4bf2-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a4bf2-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4bf2-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4bf2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4bf2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bf2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4bf2-117">See also</span></span>

- [<span data-ttu-id="a4bf2-118">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bf2-118">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a4bf2-119">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bf2-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="a4bf2-120">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bf2-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="a4bf2-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bf2-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
