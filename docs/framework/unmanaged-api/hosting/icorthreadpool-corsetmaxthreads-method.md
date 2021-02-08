---
description: '자세히 알아보기: ICorThreadpool:: CorSetMaxThreads 메서드'
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
ms.openlocfilehash: 5eb55604b55da58ffb4b5b2806aa3e340274a6b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789543"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="5a300-103">ICorThreadpool::CorSetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="5a300-103">ICorThreadpool::CorSetMaxThreads Method</span></span>

<span data-ttu-id="5a300-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a300-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a300-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a300-105">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5a300-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a300-106">Requirements</span></span>  

 <span data-ttu-id="5a300-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a300-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a300-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5a300-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a300-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a300-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a300-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a300-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a300-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a300-111">See also</span></span>

- [<span data-ttu-id="5a300-112">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a300-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
