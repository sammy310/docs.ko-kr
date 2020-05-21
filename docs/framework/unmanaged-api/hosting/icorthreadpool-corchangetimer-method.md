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
ms.openlocfilehash: e2174afe0ee96bd153b7b40c73c0185d9058a0dc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760342"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="54f7e-102">ICorThreadpool::CorChangeTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="54f7e-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="54f7e-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54f7e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="54f7e-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="54f7e-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54f7e-105">Requirements</span></span>  
 <span data-ttu-id="54f7e-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54f7e-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f7e-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="54f7e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54f7e-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f7e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54f7e-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f7e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f7e-110">참조</span><span class="sxs-lookup"><span data-stu-id="54f7e-110">See also</span></span>

- [<span data-ttu-id="54f7e-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54f7e-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
