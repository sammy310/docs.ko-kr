---
title: ICorRuntimeHost::SwitchInLogicalThreadState 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133389"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="ef991-102">ICorRuntimeHost::SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="ef991-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="ef991-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ef991-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef991-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef991-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef991-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef991-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="ef991-106">진행 사용할 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="ef991-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef991-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef991-107">Requirements</span></span>  
 <span data-ttu-id="ef991-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef991-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef991-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ef991-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef991-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef991-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef991-111">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ef991-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef991-112">참조</span><span class="sxs-lookup"><span data-stu-id="ef991-112">See also</span></span>

- [<span data-ttu-id="ef991-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef991-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
