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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136dab5c05c310d85a5e18bcdc6da0de901d3ace
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227472"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="82a7e-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="82a7e-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="82a7e-103">디버깅 서비스 차단 되는 모든 스레드를 해제 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="82a7e-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="82a7e-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="82a7e-105">설명</span><span class="sxs-lookup"><span data-stu-id="82a7e-105">Remarks</span></span>  
 <span data-ttu-id="82a7e-106">`ReleaseAllRuntimeThreads` 메서드는 런타임 스레드에서 호출 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82a7e-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="82a7e-107">호스트에는 런타임 스레드를 차단 하는 경우 이제 해제 해야 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a7e-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a7e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82a7e-108">Requirements</span></span>  
 <span data-ttu-id="82a7e-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="82a7e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a7e-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82a7e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82a7e-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="82a7e-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="82a7e-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="82a7e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82a7e-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="82a7e-113">See also</span></span>

- [<span data-ttu-id="82a7e-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a7e-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
