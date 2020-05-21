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
ms.openlocfilehash: f32381dc40a744157e46780e59b83efd63e58dcb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762645"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="56500-102">ICorRuntimeHost::SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="56500-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="56500-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56500-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56500-104">구문</span><span class="sxs-lookup"><span data-stu-id="56500-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56500-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56500-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="56500-106">제한이 전환 중인 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="56500-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56500-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56500-107">Requirements</span></span>  
 <span data-ttu-id="56500-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56500-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56500-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="56500-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56500-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56500-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56500-111">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="56500-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56500-112">참조</span><span class="sxs-lookup"><span data-stu-id="56500-112">See also</span></span>

- [<span data-ttu-id="56500-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56500-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
