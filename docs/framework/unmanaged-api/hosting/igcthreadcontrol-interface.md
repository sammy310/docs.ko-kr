---
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
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134796"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="315d8-102">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="315d8-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="315d8-103">가비지 컬렉션에 대해 차단 될 스레드의 예약에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="315d8-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="315d8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="315d8-104">Methods</span></span>  
  
|<span data-ttu-id="315d8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="315d8-105">Method</span></span>|<span data-ttu-id="315d8-106">설명</span><span class="sxs-lookup"><span data-stu-id="315d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="315d8-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="315d8-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="315d8-108">가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="315d8-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="315d8-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="315d8-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="315d8-110">런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="315d8-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="315d8-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="315d8-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="315d8-112">호출 하는 스레드가 가비지 수집 또는 기타 일시 중단 등을 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="315d8-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="315d8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="315d8-113">Requirements</span></span>  
 <span data-ttu-id="315d8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="315d8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="315d8-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="315d8-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="315d8-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="315d8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="315d8-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="315d8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315d8-118">참조</span><span class="sxs-lookup"><span data-stu-id="315d8-118">See also</span></span>

- [<span data-ttu-id="315d8-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="315d8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
