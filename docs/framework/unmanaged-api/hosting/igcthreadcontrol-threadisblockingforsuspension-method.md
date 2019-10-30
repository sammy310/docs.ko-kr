---
title: IGCThreadControl::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: e6534c3085b70b590c2dcc3f50cf0253bd5e6682
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134744"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="2337a-102">IGCThreadControl::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="2337a-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="2337a-103">호출을 수행 하는 스레드가 차단 하려고 함을 호스트에 알립니다 (가비지 수집 또는 기타 일시 중단의 경우).</span><span class="sxs-lookup"><span data-stu-id="2337a-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2337a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2337a-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2337a-105">주의</span><span class="sxs-lookup"><span data-stu-id="2337a-105">Remarks</span></span>  
 <span data-ttu-id="2337a-106">호스트는 `ThreadIsBlockingForSuspension` 콜백 내에서 스레드를 다시 예약할 지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2337a-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2337a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2337a-107">Requirements</span></span>  
 <span data-ttu-id="2337a-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2337a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2337a-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2337a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2337a-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2337a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2337a-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2337a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2337a-112">참조</span><span class="sxs-lookup"><span data-stu-id="2337a-112">See also</span></span>

- [<span data-ttu-id="2337a-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2337a-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
