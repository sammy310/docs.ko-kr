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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90af015de4428f75330de89978a7fc0a4b26750b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144198"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="21e3b-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="21e3b-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="21e3b-103">현재 스레드에 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e3b-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="21e3b-104">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21e3b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e3b-105">구문</span><span class="sxs-lookup"><span data-stu-id="21e3b-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21e3b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21e3b-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="21e3b-107">[out] 현재 스레드에 있는 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="21e3b-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e3b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21e3b-108">Requirements</span></span>  
 <span data-ttu-id="21e3b-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21e3b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e3b-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21e3b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21e3b-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="21e3b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21e3b-112">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="21e3b-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e3b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="21e3b-113">See also</span></span>

- [<span data-ttu-id="21e3b-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21e3b-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
