---
title: 어셈블리 배치
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9b8357be5b9f49569114cbc1c2942eea03696eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180182"
---
# <a name="assembly-placement"></a><span data-ttu-id="a2fcf-102">어셈블리 배치</span><span class="sxs-lookup"><span data-stu-id="a2fcf-102">Assembly Placement</span></span>
<span data-ttu-id="a2fcf-103">대부분의 .NET Framework 애플리케이션의 경우 해당 애플리케이션을 구성하는 어셈블리는 애플리케이션 디렉터리, 애플리케이션 디렉터리의 하위 디렉터리 또는 전역 어셈블리 캐시(어셈블리가 공유된 경우)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="a2fcf-104">구성 파일에 있는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하면 공용 언어 런타임에서 어셈블리를 검색하는 위치를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="a2fcf-105">어셈블리에 강력한 이름이 없는 경우, [\<codeBase&gt; 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 지정한 위치는 애플리케이션 디렉터리와 그 하위 디렉터리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="a2fcf-106">반면, 강력한 이름의 어셈블리인 경우에는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 컴퓨터 또는 네트워크상의 모든 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="a2fcf-107">비관리 코드나 COM interop 애플리케이션에 대해 어셈블리의 위치를 검색할 때도 이와 비슷한 규칙이 적용됩니다. 여러 애플리케이션에서 해당 어셈블리를 공유해야 하는 경우에는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="a2fcf-108">비관리 코드에 사용되는 어셈블리는 형식 라이브러리로 내보낸 후 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="a2fcf-109">COM interop에 사용되는 어셈블리는 카달로그에 등록해야 하는데, 경우에 따라서는 어셈블리가 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2fcf-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fcf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2fcf-110">See also</span></span>

- [<span data-ttu-id="a2fcf-111">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="a2fcf-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="a2fcf-112">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="a2fcf-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="a2fcf-113">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="a2fcf-113">Interoperating with unmanaged code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="a2fcf-114">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="a2fcf-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
