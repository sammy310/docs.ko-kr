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
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501596"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="3f24c-102">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f24c-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="3f24c-103">호스트가 CLR (공용 언어 런타임) 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f24c-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f24c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3f24c-104">Methods</span></span>  
  
|<span data-ttu-id="3f24c-105">방법</span><span class="sxs-lookup"><span data-stu-id="3f24c-105">Method</span></span>|<span data-ttu-id="3f24c-106">설명</span><span class="sxs-lookup"><span data-stu-id="3f24c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f24c-107">GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="3f24c-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="3f24c-108">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f24c-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="3f24c-109">GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="3f24c-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="3f24c-110">호스트에서 CLR을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f24c-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f24c-111">설명</span><span class="sxs-lookup"><span data-stu-id="3f24c-111">Remarks</span></span>  
 <span data-ttu-id="3f24c-112">호스트는 또는를 구현할 필요가 없습니다 `IHostAssemblyManager` `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="3f24c-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="3f24c-113">호스트에서를 구현 하는 경우 `IHostAssemblyManager` 도 구현 해야 `IHostAssemblyStore` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f24c-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="3f24c-114">런타임은 `IHostAssemblyManager` IID_IHostAssemblyManager의를 사용 하 여 초기화할 때 [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) 를 호출 하 여에 대해 쿼리 합니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="3f24c-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f24c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f24c-115">Requirements</span></span>  
 <span data-ttu-id="3f24c-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f24c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f24c-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3f24c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f24c-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f24c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f24c-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f24c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f24c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f24c-120">See also</span></span>

- [<span data-ttu-id="3f24c-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f24c-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3f24c-122">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f24c-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="3f24c-123">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f24c-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="3f24c-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f24c-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
