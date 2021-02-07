---
description: '자세히 알아보기: ICorThreadpool:: CorDeleteTimer 메서드'
title: ICorThreadpool::CorDeleteTimer 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
ms.openlocfilehash: 9096f9969702d522427640b2f881cae4aa23284d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737730"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="e1fc7-103">ICorThreadpool::CorDeleteTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="e1fc7-103">ICorThreadpool::CorDeleteTimer Method</span></span>

<span data-ttu-id="e1fc7-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fc7-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fc7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1fc7-105">Syntax</span></span>  
  
```cpp  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e1fc7-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1fc7-106">Requirements</span></span>  

 <span data-ttu-id="e1fc7-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1fc7-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fc7-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e1fc7-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1fc7-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fc7-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1fc7-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1fc7-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fc7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1fc7-111">See also</span></span>

- [<span data-ttu-id="e1fc7-112">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1fc7-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
