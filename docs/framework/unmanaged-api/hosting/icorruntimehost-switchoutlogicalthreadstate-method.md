---
title: ICorRuntimeHost::SwitchOutLogicalThreadState 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: 8151531e470b149012b2dd4fca918c8937f13918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133346"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="cb782-102">ICorRuntimeHost::SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="cb782-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="cb782-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb782-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb782-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb782-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb782-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb782-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="cb782-106">제한이 전환 중인 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="cb782-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb782-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb782-107">Requirements</span></span>  
 <span data-ttu-id="cb782-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb782-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb782-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cb782-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb782-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb782-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb782-111">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="cb782-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb782-112">참조</span><span class="sxs-lookup"><span data-stu-id="cb782-112">See also</span></span>

- [<span data-ttu-id="cb782-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb782-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
