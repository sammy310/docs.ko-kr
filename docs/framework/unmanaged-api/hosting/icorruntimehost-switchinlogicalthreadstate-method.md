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
ms.openlocfilehash: a4590bcd96226a713ff5535a8bc802c2116f862a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690137"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="39bb9-102">ICorRuntimeHost::SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="39bb9-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="39bb9-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39bb9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bb9-104">구문</span><span class="sxs-lookup"><span data-stu-id="39bb9-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39bb9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39bb9-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="39bb9-106">진행 사용할 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="39bb9-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39bb9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39bb9-107">Requirements</span></span>  

 <span data-ttu-id="39bb9-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39bb9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bb9-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39bb9-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39bb9-110">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39bb9-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39bb9-111">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="39bb9-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bb9-112">참조</span><span class="sxs-lookup"><span data-stu-id="39bb9-112">See also</span></span>

- [<span data-ttu-id="39bb9-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39bb9-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
