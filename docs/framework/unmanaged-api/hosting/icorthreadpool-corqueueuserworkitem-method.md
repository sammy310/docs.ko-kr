---
title: ICorThreadpool::CorQueueUserWorkItem 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 249571cbe49fdce720630e31d2da1641aa979624
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218695"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="e8204-102">ICorThreadpool::CorQueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e8204-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="e8204-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8204-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8204-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8204-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e8204-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8204-105">Requirements</span></span>  
 <span data-ttu-id="e8204-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8204-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8204-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8204-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8204-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e8204-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e8204-109">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e8204-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8204-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8204-110">See also</span></span>

- [<span data-ttu-id="e8204-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8204-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
