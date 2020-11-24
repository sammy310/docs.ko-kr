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
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680955"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="fdef6-102">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdef6-102">IHostAssemblyStore Interface</span></span>

<span data-ttu-id="fdef6-103">호스트가 CLR (공용 언어 런타임)과 독립적으로 어셈블리 및 모듈을 로드할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdef6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fdef6-104">Methods</span></span>  
  
|<span data-ttu-id="fdef6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fdef6-105">Method</span></span>|<span data-ttu-id="fdef6-106">설명</span><span class="sxs-lookup"><span data-stu-id="fdef6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdef6-107">ProvideAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="fdef6-107">ProvideAssembly Method</span></span>](ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="fdef6-108">[IHostAssemblyManager:: Getnonhost 어셈블리](ihostassemblymanager-getnonhoststoreassemblies-method.md)에 대 한 호출에서 반환 된 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 가 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="fdef6-109">ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="fdef6-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="fdef6-110">어셈블리 또는 연결 된 (포함 되지 않은) 리소스 파일 내에서 모듈을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdef6-111">설명</span><span class="sxs-lookup"><span data-stu-id="fdef6-111">Remarks</span></span>  

 <span data-ttu-id="fdef6-112">`IHostAssemblyStore` 호스트에서 어셈블리 id를 기반으로 어셈블리를 효율적으로 로드할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="fdef6-113">호스트는 `IStream` 바이트를 직접 가리키는 인스턴스를 반환 하 여 어셈블리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="fdef6-114">CLR은 `IHostAssemblyStore` 초기화 시를 호출 하 여 호스트가 구현 되었는지 여부를 확인 `IHostAssemblyManager::GetNonHostAssemblyStores` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="fdef6-115">이를 통해 호스트는 사용자 어셈블리에 대 한 바인딩을 제어할 수 있을 뿐만 아니라 런타임에 의존 하 여 .NET Framework 어셈블리에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdef6-116">의 구현을 제공 하는 `IHostAssemblyStore` 경우 호스트는에서 반환 된에서 참조 하지 않는 모든 어셈블리를 확인 하는 용도를 지정 합니다 `ICLRAssemblyReferenceList` `IHostAssemblyManager::GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="fdef6-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdef6-117">.NET Framework 버전 2.0는 호스트에서 [네이티브 이미지 생성기 (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) 유틸리티에 제공 된 어셈블리의 네이티브 이미지를 로드 하는 방법을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdef6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdef6-118">Requirements</span></span>  

 <span data-ttu-id="fdef6-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdef6-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdef6-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fdef6-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdef6-121">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdef6-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdef6-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdef6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdef6-123">참조</span><span class="sxs-lookup"><span data-stu-id="fdef6-123">See also</span></span>

- [<span data-ttu-id="fdef6-124">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdef6-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fdef6-125">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdef6-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="fdef6-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdef6-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
