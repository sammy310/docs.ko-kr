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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3090887d3c670b2784b7b40c7d63832715596c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697604"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="d1160-102">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="d1160-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="d1160-103">포인터를 가져는 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) 코드 개체에 대 한 키를 관리 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d1160-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1160-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1160-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1160-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1160-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="d1160-106">[out] 반환 된 `IIdentityAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d1160-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1160-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1160-107">Requirements</span></span>  
 <span data-ttu-id="d1160-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1160-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1160-109">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d1160-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d1160-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1160-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1160-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1160-111">See also</span></span>

- [<span data-ttu-id="d1160-112">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1160-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="d1160-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d1160-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
