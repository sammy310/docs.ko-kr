---
title: 전역 어셈블리 캐시에서 서비스되는 구성 요소 사용
description: 서비스되는 구성 요소(관리 코드 COM+ 구성 요소)를 .NET의 전역 어셈블리 캐시와 함께 사용합니다. CLR 및 COM+ 서비스가 비 GAC 구성 요소를 처리할 수 있는지 확인합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
ms.openlocfilehash: 314f804dfcaee64ef364cc881ae76651961294d7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254586"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="7e37f-104">전역 어셈블리 캐시에서 서비스되는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="7e37f-104">Using Serviced Components with the Global Assembly Cache</span></span>

<span data-ttu-id="7e37f-105">서비스되는 구성 요소(관리 코드 COM+ 구성 요소)는 전역 어셈블리 캐시에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-105">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="7e37f-106">일부 시나리오에서 공용 언어 런타임과 COM+ 서비스에서 전역 어셈블리 캐시에 없는 서비스되는 구성 요소를 처리할 수 있지만, 다른 시나리오에서는 그렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-106">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="7e37f-107">다음 시나리오에서 이러한 예에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-107">The following scenarios illustrate this:</span></span>  
  
- <span data-ttu-id="7e37f-108">COM+ 서버 애플리케이션에 있는 서비스되는 구성 요소의 경우, 서비스되는 구성 요소가 포함된 디렉터리와 동일한 디렉터리에서 Dllhost.exe가 실행되지 않기 때문에 구성 요소가 포함된 어셈블리는 전역 어셈블리 캐시에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-108">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
- <span data-ttu-id="7e37f-109">COM+ 라이브러리 애플리케이션에 있는 서비스되는 구성 요소의 경우 런타임 및 COM+ 서비스에서 현재 디렉터리를 검색하여 구성 요소가 포함된 어셈블리에 대한 참조를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-109">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="7e37f-110">이 경우 어셈블리가 전역 어셈블리 캐시에 있을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-110">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
- <span data-ttu-id="7e37f-111">ASP.NET 애플리케이션에 있는 서비스되는 구성 요소의 경우 상황이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-111">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="7e37f-112">서비스되는 구성 요소가 포함된 어셈블리를 애플리케이션 기준 위치의 bin 디렉터리에 저장하고 요청 시 등록을 사용하는 경우, ASP.NET에서 런타임의 섀도 기능을 사용하므로 다운로드 캐시에 어셈블리를 섀도 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7e37f-112">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e37f-113">참조</span><span class="sxs-lookup"><span data-stu-id="7e37f-113">See also</span></span>

- [<span data-ttu-id="7e37f-114">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="7e37f-114">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="7e37f-115">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="7e37f-115">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
