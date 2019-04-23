---
title: IHostControl 인터페이스
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122267"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="af17c-102">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af17c-102">IHostControl Interface</span></span>
<span data-ttu-id="af17c-103">어셈블리의 로드를 구성 하 고 호스팅 인터페이스를 호스트 지원 결정 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af17c-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af17c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="af17c-104">Methods</span></span>  
  
|<span data-ttu-id="af17c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="af17c-105">Method</span></span>|<span data-ttu-id="af17c-106">설명</span><span class="sxs-lookup"><span data-stu-id="af17c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af17c-107">GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="af17c-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="af17c-108">지정 된 인터페이스의 호스트의 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID`합니다.</span><span class="sxs-lookup"><span data-stu-id="af17c-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="af17c-109">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="af17c-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="af17c-110">응용 프로그램 도메인이 만들어졌는지 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="af17c-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af17c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af17c-111">Requirements</span></span>  
 <span data-ttu-id="af17c-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="af17c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af17c-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af17c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af17c-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="af17c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af17c-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af17c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af17c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="af17c-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="af17c-117">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af17c-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="af17c-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af17c-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="af17c-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af17c-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
