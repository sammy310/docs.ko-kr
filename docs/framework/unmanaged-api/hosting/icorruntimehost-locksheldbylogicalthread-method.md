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
ms.openlocfilehash: 16f34d91861f9fcae51691ab13549bdf1ef333a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671501"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="0c007-102">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="0c007-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="0c007-103">현재 스레드가 보유 하 고 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c007-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="0c007-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c007-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c007-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c007-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c007-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c007-106">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="0c007-107">제한이 현재 스레드에 포함 된 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c007-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c007-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c007-108">Requirements</span></span>  

 <span data-ttu-id="0c007-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c007-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c007-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0c007-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c007-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c007-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c007-112">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0c007-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c007-113">참조</span><span class="sxs-lookup"><span data-stu-id="0c007-113">See also</span></span>

- [<span data-ttu-id="0c007-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c007-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
