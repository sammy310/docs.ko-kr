---
title: ICorThreadpool::CorChangeTimer 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: 330adf6ca2445f7307671d5531ce49a9d46e0fbb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133319"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="b2ed2-102">ICorThreadpool::CorChangeTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="b2ed2-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="b2ed2-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ed2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2ed2-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b2ed2-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2ed2-105">Requirements</span></span>  
 <span data-ttu-id="b2ed2-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ed2-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b2ed2-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2ed2-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ed2-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2ed2-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ed2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ed2-110">참조</span><span class="sxs-lookup"><span data-stu-id="b2ed2-110">See also</span></span>

- [<span data-ttu-id="b2ed2-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2ed2-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
