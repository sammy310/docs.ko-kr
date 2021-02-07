---
description: '자세히 알아보기: ICorThreadpool:: Corget Threads 메서드'
title: ICorThreadpool::CorGetAvailableThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
ms.openlocfilehash: ca6b476a00ce781e10c0708f5132b398b4c85398
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760591"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="479e1-103">ICorThreadpool::CorGetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="479e1-103">ICorThreadpool::CorGetAvailableThreads Method</span></span>

<span data-ttu-id="479e1-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="479e1-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="479e1-105">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="479e1-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="479e1-106">Requirements</span></span>  

 <span data-ttu-id="479e1-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="479e1-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479e1-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="479e1-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="479e1-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="479e1-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="479e1-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479e1-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479e1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="479e1-111">See also</span></span>

- [<span data-ttu-id="479e1-112">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="479e1-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
