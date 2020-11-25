---
title: ICorThreadpool::CorCreateTimer 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: 3eac575e18c7371754401da6498d85ba7ed6c8cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717619"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="1ff70-102">ICorThreadpool::CorCreateTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff70-102">ICorThreadpool::CorCreateTimer Method</span></span>

<span data-ttu-id="1ff70-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff70-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ff70-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1ff70-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ff70-105">Requirements</span></span>  

 <span data-ttu-id="1ff70-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff70-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ff70-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1ff70-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ff70-108">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff70-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ff70-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff70-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff70-110">참조</span><span class="sxs-lookup"><span data-stu-id="1ff70-110">See also</span></span>

- [<span data-ttu-id="1ff70-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ff70-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
