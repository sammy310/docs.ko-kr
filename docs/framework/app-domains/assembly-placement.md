---
title: 어셈블리 배치
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 5eb7b5c35bb40d5a58390ccbd4619cbed4e06c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119966"
---
# <a name="assembly-placement"></a><span data-ttu-id="eae16-102">어셈블리 배치</span><span class="sxs-lookup"><span data-stu-id="eae16-102">Assembly Placement</span></span>
<span data-ttu-id="eae16-103">대부분의 .NET Framework 애플리케이션의 경우 해당 애플리케이션을 구성하는 어셈블리는 애플리케이션 디렉터리, 애플리케이션 디렉터리의 하위 디렉터리 또는 전역 어셈블리 캐시(어셈블리가 공유된 경우)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="eae16-104">구성 파일에 있는 [\<codeBase> 요소](../configure-apps/file-schema/runtime/codebase-element.md)를 사용하면 공용 언어 런타임에서 어셈블리를 검색하는 위치를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="eae16-105">어셈블리에 강력한 이름이 없는 경우, [\<codeBase&gt; 요소](../configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 지정한 위치는 애플리케이션 디렉터리와 그 하위 디렉터리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="eae16-106">반면, 강력한 이름의 어셈블리인 경우에는 [\<codeBase> 요소](../configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 컴퓨터 또는 네트워크상의 모든 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-106">If the assembly has a strong name, the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="eae16-107">비관리 코드나 COM interop 애플리케이션에 대해 어셈블리의 위치를 검색할 때도 이와 비슷한 규칙이 적용됩니다. 여러 애플리케이션에서 해당 어셈블리를 공유해야 하는 경우에는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="eae16-108">비관리 코드에 사용되는 어셈블리는 형식 라이브러리로 내보낸 후 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="eae16-109">COM interop에 사용되는 어셈블리는 카달로그에 등록해야 하는데, 경우에 따라서는 어셈블리가 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae16-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae16-110">참조</span><span class="sxs-lookup"><span data-stu-id="eae16-110">See also</span></span>

- [<span data-ttu-id="eae16-111">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="eae16-111">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="eae16-112">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="eae16-112">Configuring Apps</span></span>](../configure-apps/index.md)
- [<span data-ttu-id="eae16-113">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="eae16-113">Interoperating with unmanaged code</span></span>](../interop/index.md)
- [<span data-ttu-id="eae16-114">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="eae16-114">Assemblies in .NET</span></span>](index.md)
