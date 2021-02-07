---
description: '자세히 알아보기: GetIdentityAuthority 함수'
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
ms.openlocfilehash: 5126aa9b319af41f7ecd30845a9f74ba69016588
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760998"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="97fe4-103">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="97fe4-103">GetIdentityAuthority Function</span></span>

<span data-ttu-id="97fe4-104">코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97fe4-104">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97fe4-105">구문</span><span class="sxs-lookup"><span data-stu-id="97fe4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="97fe4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97fe4-106">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="97fe4-107">제한이 반환 된 `IIdentityAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97fe4-107">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97fe4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97fe4-108">Requirements</span></span>  

 <span data-ttu-id="97fe4-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97fe4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97fe4-110">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="97fe4-110">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="97fe4-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97fe4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97fe4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97fe4-112">See also</span></span>

- [<span data-ttu-id="97fe4-113">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97fe4-113">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="97fe4-114">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="97fe4-114">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
