---
title: ICorRuntimeHost::LocksHeldByLogicalThread 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: f6ef7e06d94cb22d266949927cb15105b1602d3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139533"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="39ea8-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="39ea8-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="39ea8-103">현재 스레드가 보유 하 고 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ea8-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="39ea8-104">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="39ea8-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ea8-105">구문</span><span class="sxs-lookup"><span data-stu-id="39ea8-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39ea8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39ea8-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="39ea8-107">제한이 현재 스레드에 포함 된 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="39ea8-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ea8-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39ea8-108">Requirements</span></span>  
 <span data-ttu-id="39ea8-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ea8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39ea8-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39ea8-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39ea8-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ea8-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39ea8-112">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="39ea8-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ea8-113">참조</span><span class="sxs-lookup"><span data-stu-id="39ea8-113">See also</span></span>

- [<span data-ttu-id="39ea8-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39ea8-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
