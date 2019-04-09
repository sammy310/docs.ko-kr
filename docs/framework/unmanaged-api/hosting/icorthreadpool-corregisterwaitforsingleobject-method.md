---
title: ICorThreadpool::CorRegisterWaitForSingleObject 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorRegisterWaitForSingleObject
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegisterWaitForSingleObject
helpviewer_keywords:
- ICorThreadpool::CorRegisterWaitForSingleObject method [.NET Framework hosting]
- CorRegisterWaitForSingleObject method [.NET Framework hosting]
ms.assetid: cade1feb-71d2-43ed-85ca-7b2e9da12994
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a94673b4be4d15edaaf54c22f90723216c8bc10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141299"
---
# <a name="icorthreadpoolcorregisterwaitforsingleobject-method"></a><span data-ttu-id="0a1c6-102">ICorThreadpool::CorRegisterWaitForSingleObject 메서드</span><span class="sxs-lookup"><span data-stu-id="0a1c6-102">ICorThreadpool::CorRegisterWaitForSingleObject Method</span></span>
<span data-ttu-id="0a1c6-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a1c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a1c6-104">Syntax</span></span>  
  
```  
HRESULT CorRegisterWaitForSingleObject (  
    [in]  HANDLE*             phNewWaitObject,  
    [in]  HANDLE              hWaitObject,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Context,  
    [in]  ULONG               timeout,  
    [in]  BOOL                executeOnlyOnce,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0a1c6-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a1c6-105">Requirements</span></span>  
 <span data-ttu-id="0a1c6-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a1c6-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a1c6-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a1c6-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0a1c6-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0a1c6-109">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0a1c6-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a1c6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a1c6-110">See also</span></span>

- [<span data-ttu-id="0a1c6-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a1c6-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
