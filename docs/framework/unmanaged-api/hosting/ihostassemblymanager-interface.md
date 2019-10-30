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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124517"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="4814a-102">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4814a-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="4814a-103">호스트가 CLR (공용 언어 런타임) 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4814a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4814a-104">Methods</span></span>  
  
|<span data-ttu-id="4814a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4814a-105">Method</span></span>|<span data-ttu-id="4814a-106">설명</span><span class="sxs-lookup"><span data-stu-id="4814a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4814a-107">GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="4814a-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="4814a-108">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="4814a-109">GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="4814a-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="4814a-110">호스트에서 CLR을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4814a-111">주의</span><span class="sxs-lookup"><span data-stu-id="4814a-111">Remarks</span></span>  
 <span data-ttu-id="4814a-112">호스트는 `IHostAssemblyManager` 또는 `IHostAssemblyStore`를 구현 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="4814a-113">호스트에서 `IHostAssemblyManager`를 구현 하는 경우 `IHostAssemblyStore`도 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="4814a-114">런타임은 IID_IHostAssemblyManager의 `IID`를 사용 하 여 초기화할 때 [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 를 호출 하 여 `IHostAssemblyManager`를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4814a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4814a-115">Requirements</span></span>  
 <span data-ttu-id="4814a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4814a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4814a-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4814a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4814a-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4814a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4814a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4814a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4814a-120">참조</span><span class="sxs-lookup"><span data-stu-id="4814a-120">See also</span></span>

- [<span data-ttu-id="4814a-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4814a-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4814a-122">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4814a-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="4814a-123">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4814a-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="4814a-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4814a-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
