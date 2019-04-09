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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134266"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="04d93-102">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04d93-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="04d93-103">가비지 컬렉션에 대해 차단 될 수 있는 스레드 예약에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d93-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04d93-104">메서드</span><span class="sxs-lookup"><span data-stu-id="04d93-104">Methods</span></span>  
  
|<span data-ttu-id="04d93-105">메서드</span><span class="sxs-lookup"><span data-stu-id="04d93-105">Method</span></span>|<span data-ttu-id="04d93-106">설명</span><span class="sxs-lookup"><span data-stu-id="04d93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04d93-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="04d93-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="04d93-108">런타임 스레드를 다시 시작 가비지 수집 또는 기타 일시 중단 한 후 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="04d93-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="04d93-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="04d93-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="04d93-110">가비지 수집 스레드 일시 중단 또는 다른 일시 중단 런타임에서 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="04d93-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="04d93-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="04d93-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="04d93-112">아마도 다른 일시 중단 또는 가비지 컬렉션에 대 한 차단 하 려 호출을 수행 하는 스레드는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="04d93-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04d93-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04d93-113">Requirements</span></span>  
 <span data-ttu-id="04d93-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d93-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d93-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04d93-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04d93-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="04d93-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="04d93-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="04d93-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04d93-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="04d93-118">See also</span></span>

- [<span data-ttu-id="04d93-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04d93-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
