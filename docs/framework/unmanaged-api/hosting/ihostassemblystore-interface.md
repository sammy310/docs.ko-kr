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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930041"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="e7afc-102">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7afc-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="e7afc-103">호스트 어셈블리와는 CLR (공용 언어 런타임)와 독립적으로 모듈을 로드 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7afc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e7afc-104">Methods</span></span>  
  
|<span data-ttu-id="e7afc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e7afc-105">Method</span></span>|<span data-ttu-id="e7afc-106">설명</span><span class="sxs-lookup"><span data-stu-id="e7afc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7afc-107">ProvideAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e7afc-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="e7afc-108">참조 되지 않은 어셈블리에 대 한 참조를 가져옵니다 합니다 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에 대 한 호출에서 반환 된 [ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="e7afc-109">ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="e7afc-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="e7afc-110">어셈블리 또는 연결된 (포함된 되지 않은) 리소스 파일 내에서 모듈을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7afc-111">설명</span><span class="sxs-lookup"><span data-stu-id="e7afc-111">Remarks</span></span>  
 <span data-ttu-id="e7afc-112">`IHostAssemblyStore` 어셈블리 id에 따라 효율적으로 어셈블리를 로드 하는 호스트에 대 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="e7afc-113">반환 하 여 어셈블리를 로드 하는 호스트 `IStream` 직접적으로 바이트를 가리키는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e7afc-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="e7afc-114">CLR 호스트에 구현 여부를 결정 `IHostAssemblyStore` 를 호출 하 여 `IHostAssemblyManager::GetNonHostAssemblyStores` 를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="e7afc-115">이렇게 하면 호스트, 예를 들어, 사용자 어셈블리 바인딩을 제어할 수 있지만 런타임에서.NET Framework 어셈블리에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7afc-116">구현을 제공 `IHostAssemblyStore`, 호스트에서 참조 되지 않은 모든 어셈블리를 확인 하도록 지정 합니다 `ICLRAssemblyReferenceList` 에서 반환 된 `IHostAssemblyManager::GetNonHostStoreAssemblies`합니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7afc-117">제공 된 대로.NET Framework 버전 2.0 호스트가 어셈블리의 네이티브 이미지를 로드 하는 데 사용할 방법을 제공 하지 않습니다 합니다 [네이티브 이미지 생성기 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="e7afc-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7afc-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7afc-118">Requirements</span></span>  
 <span data-ttu-id="e7afc-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7afc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7afc-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7afc-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7afc-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e7afc-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7afc-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7afc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7afc-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7afc-123">See also</span></span>

- [<span data-ttu-id="e7afc-124">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7afc-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e7afc-125">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7afc-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="e7afc-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7afc-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
