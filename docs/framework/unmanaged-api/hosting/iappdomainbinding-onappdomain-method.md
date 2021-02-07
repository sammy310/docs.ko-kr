---
description: '자세히 알아보기: IAppDomainBinding:: OnAppDomain 메서드'
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
ms.openlocfilehash: de7f37152261a6fe829026607cf135f3ea0b4a84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760604"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="87d54-103">IAppDomainBinding::OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="87d54-103">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="87d54-104">응용 프로그램 도메인이 생성 되었음을 호스트에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d54-104">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d54-105">구문</span><span class="sxs-lookup"><span data-stu-id="87d54-105">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d54-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87d54-106">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="87d54-107">진행 새 응용 프로그램 도메인을 나타내는 [IUnknown](/cpp/atl/iunknown) 인터페이스 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87d54-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d54-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87d54-108">Requirements</span></span>  

 <span data-ttu-id="87d54-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87d54-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d54-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87d54-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87d54-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d54-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87d54-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d54-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d54-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87d54-113">See also</span></span>

- [<span data-ttu-id="87d54-114">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d54-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
