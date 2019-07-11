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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44973bcf98eb776735e0144ff1c2747b1445c5d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770889"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="8bb1a-102">ICorRuntimeHost::SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb1a-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="8bb1a-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bb1a-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bb1a-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="8bb1a-106">[in] 사용 하려면 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb1a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bb1a-107">Requirements</span></span>  
 <span data-ttu-id="8bb1a-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb1a-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8bb1a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bb1a-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8bb1a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bb1a-111">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8bb1a-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb1a-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="8bb1a-112">See also</span></span>

- [<span data-ttu-id="8bb1a-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb1a-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
