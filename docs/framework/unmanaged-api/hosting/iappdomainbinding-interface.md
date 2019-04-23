---
title: IAppDomainBinding 인터페이스
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2c3a3057003d0035bfcb096a94c84d610e3056f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134188"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="7a35e-102">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a35e-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="7a35e-103">CLR (공용 언어 런타임) 응용 프로그램 도메인이 만들어졌는지 호스트 응용 프로그램에 알리기 위해 호출 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a35e-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a35e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7a35e-104">Methods</span></span>  
  
|<span data-ttu-id="7a35e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7a35e-105">Method</span></span>|<span data-ttu-id="7a35e-106">설명</span><span class="sxs-lookup"><span data-stu-id="7a35e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a35e-107">OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="7a35e-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="7a35e-108">CLR (공용 언어 런타임) 응용 프로그램 도메인이 만들어졌는지 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a35e-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a35e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a35e-109">Requirements</span></span>  
 <span data-ttu-id="7a35e-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a35e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a35e-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a35e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a35e-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7a35e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a35e-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a35e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a35e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7a35e-114">See also</span></span>

- [<span data-ttu-id="7a35e-115">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a35e-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
