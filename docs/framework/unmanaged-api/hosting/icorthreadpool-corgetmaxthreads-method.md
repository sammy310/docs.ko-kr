---
title: ICorThreadpool::CorGetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf5c02972a8331b3dd5e35ffcc4213e094e532d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700100"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="f20ef-102">ICorThreadpool::CorGetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f20ef-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="f20ef-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f20ef-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f20ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="f20ef-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f20ef-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f20ef-105">Requirements</span></span>  
 <span data-ttu-id="f20ef-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f20ef-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f20ef-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f20ef-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f20ef-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f20ef-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f20ef-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f20ef-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20ef-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="f20ef-110">See also</span></span>

- [<span data-ttu-id="f20ef-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f20ef-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
