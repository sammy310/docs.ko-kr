---
description: '자세히 알아보기: IGCThreadControl 인터페이스'
title: IGCThreadControl 인터페이스
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 07c76848668b1525f4ff45ba5de746beefe0e004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709284"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="05e80-103">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05e80-103">IGCThreadControl Interface</span></span>

<span data-ttu-id="05e80-104">가비지 컬렉션에 대해 차단 될 스레드의 예약에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e80-104">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05e80-105">메서드</span><span class="sxs-lookup"><span data-stu-id="05e80-105">Methods</span></span>  
  
|<span data-ttu-id="05e80-106">메서드</span><span class="sxs-lookup"><span data-stu-id="05e80-106">Method</span></span>|<span data-ttu-id="05e80-107">설명</span><span class="sxs-lookup"><span data-stu-id="05e80-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05e80-108">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="05e80-108">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="05e80-109">가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="05e80-109">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="05e80-110">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="05e80-110">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="05e80-111">런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="05e80-111">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="05e80-112">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="05e80-112">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="05e80-113">호출 하는 스레드가 가비지 수집 또는 기타 일시 중단 등을 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="05e80-113">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05e80-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05e80-114">Requirements</span></span>  

 <span data-ttu-id="05e80-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05e80-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e80-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="05e80-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05e80-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05e80-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05e80-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e80-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e80-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05e80-119">See also</span></span>

- [<span data-ttu-id="05e80-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05e80-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
