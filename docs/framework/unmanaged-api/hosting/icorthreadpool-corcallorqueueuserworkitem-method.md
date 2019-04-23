---
title: ICorThreadpool::CorCallOrQueueUserWorkItem 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7dd4589da9b59d7e701ac641c8d45be3735d0b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199169"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="573e0-102">ICorThreadpool::CorCallOrQueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="573e0-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="573e0-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="573e0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="573e0-104">Syntax</span></span>  
  
```  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="573e0-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="573e0-105">Requirements</span></span>  
 <span data-ttu-id="573e0-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="573e0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="573e0-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="573e0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="573e0-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="573e0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="573e0-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="573e0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573e0-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="573e0-110">See also</span></span>

- [<span data-ttu-id="573e0-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="573e0-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
