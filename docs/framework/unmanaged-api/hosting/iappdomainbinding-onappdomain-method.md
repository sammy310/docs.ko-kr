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
ms.openlocfilehash: 2d5dbd003d0ea5decae0025d47e6bd5c1fb1ed4a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617076"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="1e948-102">IAppDomainBinding::OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="1e948-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="1e948-103">응용 프로그램 도메인이 생성 되었음을 호스트에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e948-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e948-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e948-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e948-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e948-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="1e948-106">진행 새 응용 프로그램 도메인을 나타내는 [IUnknown](/cpp/atl/iunknown) 인터페이스 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e948-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e948-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e948-107">Requirements</span></span>  
 <span data-ttu-id="1e948-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e948-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e948-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1e948-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e948-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e948-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e948-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e948-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e948-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e948-112">See also</span></span>

- [<span data-ttu-id="1e948-113">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e948-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
