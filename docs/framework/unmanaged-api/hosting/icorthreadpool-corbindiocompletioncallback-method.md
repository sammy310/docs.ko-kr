---
title: ICorThreadpool::CorBindIoCompletionCallback 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
ms.openlocfilehash: 7baf144f5d14a8757101bdb29a8bc81ff3a05231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690059"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="65a8d-102">ICorThreadpool::CorBindIoCompletionCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="65a8d-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>

<span data-ttu-id="65a8d-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65a8d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65a8d-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="65a8d-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65a8d-105">Requirements</span></span>  

 <span data-ttu-id="65a8d-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65a8d-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a8d-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="65a8d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65a8d-108">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a8d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65a8d-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a8d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a8d-110">참조</span><span class="sxs-lookup"><span data-stu-id="65a8d-110">See also</span></span>

- [<span data-ttu-id="65a8d-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65a8d-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
