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
ms.openlocfilehash: e9631211993afbfe968c7122828251746f15c3f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732128"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="ffc0b-102">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="ffc0b-102">GetIdentityAuthority Function</span></span>

<span data-ttu-id="ffc0b-103">코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0b-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ffc0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffc0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffc0b-105">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="ffc0b-106">제한이 반환 된 `IIdentityAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc0b-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc0b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffc0b-107">Requirements</span></span>  

 <span data-ttu-id="ffc0b-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc0b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc0b-109">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="ffc0b-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ffc0b-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc0b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc0b-111">참조</span><span class="sxs-lookup"><span data-stu-id="ffc0b-111">See also</span></span>

- [<span data-ttu-id="ffc0b-112">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffc0b-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="ffc0b-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ffc0b-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
