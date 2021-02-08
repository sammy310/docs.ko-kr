---
description: '자세히 알아보기: ICorRuntimeHost:: LocksHeldByLogicalThread 메서드'
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
ms.openlocfilehash: bd64151bdc0c6aa0235192f0fc7f4badd8b0bbd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789647"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="65861-103">ICorRuntimeHost::LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="65861-103">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="65861-104">현재 스레드가 보유 하 고 있는 잠금 수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="65861-104">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="65861-105">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65861-105">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65861-106">구문</span><span class="sxs-lookup"><span data-stu-id="65861-106">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65861-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65861-107">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="65861-108">제한이 현재 스레드에 포함 된 잠금 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="65861-108">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65861-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65861-109">Requirements</span></span>  

 <span data-ttu-id="65861-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65861-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65861-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="65861-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65861-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65861-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65861-113">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="65861-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65861-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65861-114">See also</span></span>

- [<span data-ttu-id="65861-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65861-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
