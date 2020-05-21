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
ms.openlocfilehash: e3655f77a94da25f65bada2cd4067ef53550e778
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762021"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="0d5e0-102">ICorThreadpool::CorUnregisterWait 메서드</span><span class="sxs-lookup"><span data-stu-id="0d5e0-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="0d5e0-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5e0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d5e0-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0d5e0-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d5e0-105">Requirements</span></span>  
 <span data-ttu-id="0d5e0-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d5e0-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5e0-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0d5e0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d5e0-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d5e0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d5e0-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5e0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5e0-110">참조</span><span class="sxs-lookup"><span data-stu-id="0d5e0-110">See also</span></span>

- [<span data-ttu-id="0d5e0-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d5e0-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
