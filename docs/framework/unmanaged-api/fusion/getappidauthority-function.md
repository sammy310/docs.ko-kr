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
ms.openlocfilehash: 274b91793cd51348c42661bf12a4e4385e17f630
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093971"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="04f4e-102">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="04f4e-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="04f4e-103">포인터를 가져는 [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) 응용 프로그램 id 및 참조에 대 한 키를 관리 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="04f4e-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="04f4e-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f4e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04f4e-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="04f4e-106">[out] 반환 된 `IAppIdAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04f4e-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f4e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04f4e-107">Requirements</span></span>  
 <span data-ttu-id="04f4e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="04f4e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f4e-109">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="04f4e-109">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="04f4e-110">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="04f4e-110">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04f4e-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="04f4e-111">See also</span></span>

- [<span data-ttu-id="04f4e-112">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04f4e-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="04f4e-113">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="04f4e-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
