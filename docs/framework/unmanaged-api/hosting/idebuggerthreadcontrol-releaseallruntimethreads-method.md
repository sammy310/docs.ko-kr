---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 9ae1aa6590366468166916e6a92d0b356eb37c27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133147"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="d72fe-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="d72fe-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="d72fe-103">디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d72fe-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="d72fe-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d72fe-105">주의</span><span class="sxs-lookup"><span data-stu-id="d72fe-105">Remarks</span></span>  
 <span data-ttu-id="d72fe-106">`ReleaseAllRuntimeThreads` 메서드는 런타임 스레드에서 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d72fe-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="d72fe-107">호스트에 차단 된 런타임 스레드가 있으면 지금 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72fe-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72fe-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d72fe-108">Requirements</span></span>  
 <span data-ttu-id="d72fe-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d72fe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72fe-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d72fe-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d72fe-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72fe-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d72fe-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d72fe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72fe-113">참조</span><span class="sxs-lookup"><span data-stu-id="d72fe-113">See also</span></span>

- [<span data-ttu-id="d72fe-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d72fe-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
