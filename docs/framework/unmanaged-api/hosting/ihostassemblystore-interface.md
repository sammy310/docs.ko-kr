---
title: IHostAssemblyStore 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: d7475e2423d4dc6f57e8928514d7991169eef232
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124496"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="5c632-102">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c632-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="5c632-103">호스트가 CLR (공용 언어 런타임)과 독립적으로 어셈블리 및 모듈을 로드할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c632-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5c632-104">Methods</span></span>  
  
|<span data-ttu-id="5c632-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5c632-105">Method</span></span>|<span data-ttu-id="5c632-106">설명</span><span class="sxs-lookup"><span data-stu-id="5c632-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c632-107">ProvideAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="5c632-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="5c632-108">[IHostAssemblyManager:: Getnonhost 어셈블리](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)에 대 한 호출에서 반환 된 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 가 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="5c632-109">ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="5c632-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="5c632-110">어셈블리 또는 연결 된 (포함 되지 않은) 리소스 파일 내에서 모듈을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c632-111">주의</span><span class="sxs-lookup"><span data-stu-id="5c632-111">Remarks</span></span>  
 <span data-ttu-id="5c632-112">`IHostAssemblyStore`는 호스트가 어셈블리 id를 기반으로 어셈블리를 효율적으로 로드할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="5c632-113">호스트는 바이트를 직접 가리키는 `IStream` 인스턴스를 반환 하 여 어셈블리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="5c632-114">CLR은 초기화 될 때 `IHostAssemblyManager::GetNonHostAssemblyStores`를 호출 하 여 호스트가 `IHostAssemblyStore`를 구현 했는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="5c632-115">이를 통해 호스트는 사용자 어셈블리에 대 한 바인딩을 제어할 수 있을 뿐만 아니라 런타임에 의존 하 여 .NET Framework 어셈블리에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c632-116">`IHostAssemblyStore`의 구현을 제공 하는 경우 호스트는 `IHostAssemblyManager::GetNonHostStoreAssemblies`에서 반환 된 `ICLRAssemblyReferenceList`에서 참조 하지 않는 모든 어셈블리를 확인 하는 의도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c632-117">.NET Framework 버전 2.0에서는 [네이티브 이미지 생성기 (ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 유틸리티에서 제공 하는 것 처럼 호스트에서 어셈블리의 네이티브 이미지를 로드 하는 방법을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c632-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c632-118">Requirements</span></span>  
 <span data-ttu-id="5c632-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c632-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c632-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5c632-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c632-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c632-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c632-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c632-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c632-123">참조</span><span class="sxs-lookup"><span data-stu-id="5c632-123">See also</span></span>

- [<span data-ttu-id="5c632-124">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c632-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5c632-125">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c632-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="5c632-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c632-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
