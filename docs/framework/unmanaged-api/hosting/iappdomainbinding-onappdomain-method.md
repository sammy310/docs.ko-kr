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
ms.openlocfilehash: 37c02b878cd52034603ab6cafe4d8aaca594cbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126883"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="ca6ac-102">IAppDomainBinding::OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="ca6ac-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="ca6ac-103">응용 프로그램 도메인이 생성 되었음을 호스트에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6ac-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca6ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca6ac-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca6ac-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca6ac-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="ca6ac-106">진행 새 응용 프로그램 도메인을 나타내는 [IUnknown](/cpp/atl/iunknown) 인터페이스 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6ac-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca6ac-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca6ac-107">Requirements</span></span>  
 <span data-ttu-id="ca6ac-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca6ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca6ac-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ca6ac-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca6ac-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6ac-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca6ac-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca6ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6ac-112">참조</span><span class="sxs-lookup"><span data-stu-id="ca6ac-112">See also</span></span>

- [<span data-ttu-id="ca6ac-113">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca6ac-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
