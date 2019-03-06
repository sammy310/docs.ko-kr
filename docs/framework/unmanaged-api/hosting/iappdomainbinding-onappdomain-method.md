---
title: IAppDomainBinding::OnAppDomain 메서드
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 798ef6a9b058d9d49019554feba63627360e6a0e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480041"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="c3ebe-102">IAppDomainBinding::OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="c3ebe-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="c3ebe-103">CLR (공용 언어 런타임) 응용 프로그램 도메인이 만들어졌는지 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3ebe-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ebe-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3ebe-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ebe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3ebe-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="c3ebe-106">[in] 에 대 한 포인터를 [IUnknown](/cpp/atl/iunknown) 새 응용 프로그램 도메인을 나타내는 인터페이스 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ebe-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ebe-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3ebe-107">Requirements</span></span>  
 <span data-ttu-id="c3ebe-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3ebe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ebe-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3ebe-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3ebe-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c3ebe-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3ebe-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ebe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ebe-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3ebe-112">See also</span></span>
- [<span data-ttu-id="c3ebe-113">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3ebe-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
