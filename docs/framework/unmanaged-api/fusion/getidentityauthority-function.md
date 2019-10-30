---
title: GetIdentityAuthority 함수
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127139"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="c2cb4-102">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="c2cb4-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="c2cb4-103">코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2cb4-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2cb4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2cb4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2cb4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2cb4-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="c2cb4-106">제한이 반환 된 `IIdentityAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cb4-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2cb4-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2cb4-107">Requirements</span></span>  
 <span data-ttu-id="c2cb4-108">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cb4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cb4-109">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="c2cb4-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c2cb4-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cb4-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cb4-111">참조</span><span class="sxs-lookup"><span data-stu-id="c2cb4-111">See also</span></span>

- [<span data-ttu-id="c2cb4-112">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2cb4-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="c2cb4-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="c2cb4-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
