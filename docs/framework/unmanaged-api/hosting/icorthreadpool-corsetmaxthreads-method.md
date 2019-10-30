---
title: ICorThreadpool::CorSetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: e0183ed0f1556afb660ead042dd0d26a63ef75dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133222"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="2fc27-102">ICorThreadpool::CorSetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="2fc27-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="2fc27-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2fc27-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc27-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fc27-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2fc27-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fc27-105">Requirements</span></span>  
 <span data-ttu-id="2fc27-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fc27-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc27-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2fc27-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fc27-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc27-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fc27-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc27-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc27-110">참조</span><span class="sxs-lookup"><span data-stu-id="2fc27-110">See also</span></span>

- [<span data-ttu-id="2fc27-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fc27-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
