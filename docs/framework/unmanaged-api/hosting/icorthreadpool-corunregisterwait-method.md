---
title: ICorThreadpool::CorUnregisterWait 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9ab5ca0a007422a2193d84a4915e2c0c67d855d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753190"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="a7485-102">ICorThreadpool::CorUnregisterWait 메서드</span><span class="sxs-lookup"><span data-stu-id="a7485-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="a7485-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7485-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7485-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7485-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a7485-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7485-105">Requirements</span></span>  
 <span data-ttu-id="a7485-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7485-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7485-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7485-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7485-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a7485-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7485-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7485-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7485-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7485-110">See also</span></span>

- [<span data-ttu-id="a7485-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7485-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
