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
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805121"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="5f033-102">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f033-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="5f033-103">가비지 컬렉션에 대해 차단 될 스레드의 예약에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f033-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f033-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5f033-104">Methods</span></span>  
  
|<span data-ttu-id="5f033-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5f033-105">Method</span></span>|<span data-ttu-id="5f033-106">Description</span><span class="sxs-lookup"><span data-stu-id="5f033-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f033-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="5f033-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="5f033-108">가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5f033-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="5f033-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="5f033-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="5f033-110">런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5f033-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="5f033-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="5f033-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="5f033-112">호출 하는 스레드가 가비지 수집 또는 기타 일시 중단 등을 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5f033-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f033-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f033-113">Requirements</span></span>  
 <span data-ttu-id="5f033-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f033-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f033-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f033-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f033-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f033-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f033-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f033-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f033-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f033-118">See also</span></span>

- [<span data-ttu-id="5f033-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f033-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
