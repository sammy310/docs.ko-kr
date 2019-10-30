---
title: ICLRControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: 914a2f6103fb0ffb9a7b9fcb895ecf0cd62f3c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126602"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="41847-102">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-102">ICLRControl Interface</span></span>
<span data-ttu-id="41847-103">호스트가 CLR (공용 언어 런타임)에 대 한 참조를 가져오고의 측면을 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41847-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41847-104">메서드</span><span class="sxs-lookup"><span data-stu-id="41847-104">Methods</span></span>  
  
|<span data-ttu-id="41847-105">메서드</span><span class="sxs-lookup"><span data-stu-id="41847-105">Method</span></span>|<span data-ttu-id="41847-106">설명</span><span class="sxs-lookup"><span data-stu-id="41847-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41847-107">GetCLRManager 메서드</span><span class="sxs-lookup"><span data-stu-id="41847-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="41847-108">호스트가 CLR을 구성 하는 데 사용할 수 있는 관리자 형식의 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41847-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="41847-109">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="41847-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="41847-110"><xref:System.AppDomainManager>에서 파생 된 형식을 응용 프로그램 도메인 관리자의 형식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41847-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41847-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41847-111">Requirements</span></span>  
 <span data-ttu-id="41847-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41847-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41847-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="41847-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41847-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41847-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41847-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41847-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41847-116">참조</span><span class="sxs-lookup"><span data-stu-id="41847-116">See also</span></span>

- [<span data-ttu-id="41847-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="41847-118">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="41847-119">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="41847-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="41847-121">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="41847-122">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="41847-123">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="41847-124">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="41847-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41847-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
