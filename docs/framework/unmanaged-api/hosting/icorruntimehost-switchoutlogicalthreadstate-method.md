---
description: '자세히 알아보기: ICorRuntimeHost:: SwitchOutLogicalThreadState 메서드'
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
ms.openlocfilehash: b4190ebe6b2c260f85afd8dd17127d0c63dca6c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799449"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="83cc5-103">ICorRuntimeHost::SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="83cc5-103">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>

<span data-ttu-id="83cc5-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83cc5-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cc5-105">구문</span><span class="sxs-lookup"><span data-stu-id="83cc5-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83cc5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83cc5-106">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="83cc5-107">제한이 전환 중인 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="83cc5-107">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83cc5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83cc5-108">Requirements</span></span>  

 <span data-ttu-id="83cc5-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83cc5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83cc5-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="83cc5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83cc5-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83cc5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83cc5-112">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="83cc5-112">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cc5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83cc5-113">See also</span></span>

- [<span data-ttu-id="83cc5-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83cc5-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
