---
description: '자세히 알아보기: ICorThreadpool:: CorChangeTimer 메서드'
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
ms.openlocfilehash: 259974d7c04f0bf0b4cc6b93234b35ab2c96e2ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671999"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="5f42a-103">ICorThreadpool::CorChangeTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="5f42a-103">ICorThreadpool::CorChangeTimer Method</span></span>

<span data-ttu-id="5f42a-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f42a-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f42a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f42a-105">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5f42a-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f42a-106">Requirements</span></span>  

 <span data-ttu-id="5f42a-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f42a-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f42a-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f42a-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f42a-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f42a-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f42a-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f42a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f42a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f42a-111">See also</span></span>

- [<span data-ttu-id="5f42a-112">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f42a-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
