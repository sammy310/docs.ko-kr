---
title: GetAppIdAuthority 함수
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8471610008bee02c7cc4e7654b21d6aca5dcf53a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796277"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="56c68-102">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="56c68-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="56c68-103">응용 프로그램 id 및 참조에 대 한 키를 관리 하는 [Iappidauthority](iappidauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56c68-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c68-104">구문</span><span class="sxs-lookup"><span data-stu-id="56c68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="56c68-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56c68-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="56c68-106">제한이 반환 `IAppIdAuthority` 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="56c68-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56c68-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56c68-107">Requirements</span></span>  
 <span data-ttu-id="56c68-108">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="56c68-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c68-109">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="56c68-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="56c68-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56c68-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c68-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="56c68-111">See also</span></span>

- [<span data-ttu-id="56c68-112">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56c68-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="56c68-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="56c68-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
