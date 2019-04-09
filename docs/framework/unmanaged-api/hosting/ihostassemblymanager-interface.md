---
title: IHostAssemblyManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e300d4645939a131ceb8206999d95056b96a678
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118952"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="4b460-102">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b460-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="4b460-103">호스트 또는 호스트의 CLR (공용 언어 런타임)에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b460-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4b460-104">Methods</span></span>  
  
|<span data-ttu-id="4b460-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4b460-105">Method</span></span>|<span data-ttu-id="4b460-106">설명</span><span class="sxs-lookup"><span data-stu-id="4b460-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b460-107">GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="4b460-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="4b460-108">한 인터페이스 포인터를 가져옵니다는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 호스트에 의해 로드 된 어셈블리의 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="4b460-109">GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="4b460-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="4b460-110">한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트 로드 하기 위해 CLR에서 예상 하는 어셈블리의 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b460-111">설명</span><span class="sxs-lookup"><span data-stu-id="4b460-111">Remarks</span></span>  
 <span data-ttu-id="4b460-112">호스트를 구현 하지 않아도 됩니다 `IHostAssemblyManager` 또는 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="4b460-113">호스트에서 구현 하는 경우 `IHostAssemblyManager`를 구현 해야 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="4b460-114">런타임에 쿼리를 `IHostAssemblyManager` 를 호출 하 여 [ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 사용 하 여 초기화 시는 `IID` IID_IHostAssemblyManager의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b460-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b460-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b460-115">Requirements</span></span>  
 <span data-ttu-id="4b460-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b460-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b460-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b460-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b460-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4b460-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4b460-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4b460-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b460-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b460-120">See also</span></span>

- [<span data-ttu-id="4b460-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b460-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4b460-122">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b460-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="4b460-123">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b460-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="4b460-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b460-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
