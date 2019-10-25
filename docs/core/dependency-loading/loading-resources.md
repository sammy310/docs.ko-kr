---
title: 위성 어셈블리 로드 알고리즘 - .NET Core
description: .NET Core에서 위성 어셈블리 로드 알고리즘의 세부 정보 설명
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2019
ms.locfileid: "72303625"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="4c68c-103">위성 어셈블리 로드 알고리즘</span><span class="sxs-lookup"><span data-stu-id="4c68c-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="4c68c-104">위성 어셈블리는 언어 및 문화권에 맞게 사용자 지정된 지역화된 리소스를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="4c68c-105">위성 어셈블리는 일반적인 관리 어셈블리와 다른 로드 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="4c68c-106">위성 어셈블리는 언제 로드되나요?</span><span class="sxs-lookup"><span data-stu-id="4c68c-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="4c68c-107">위성 어셈블리는 지역화된 리소스를 로드할 때 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="4c68c-108">지역화된 리소스를 로드하는 기본 API는 <xref:System.Resources.ResourceManager?displayProperty=fullName> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="4c68c-109">궁극적으로 <xref:System.Resources.ResourceManager> 클래스는 각 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>에 대해 <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="4c68c-110">상위 수준 API는 하위 수준 API를 추상화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="4c68c-111">알고리즘</span><span class="sxs-lookup"><span data-stu-id="4c68c-111">Algorithm</span></span>

<span data-ttu-id="4c68c-112">.NET Core 리소스 대체 프로세스에는 다음 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="4c68c-113">`active` <xref:System.Runtime.Loader.AssemblyLoadContext> 인스턴스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="4c68c-114">모든 경우에 `active` 인스턴스는 실행 중인 어셈블리의 <xref:System.Runtime.Loader.AssemblyLoadContext>입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="4c68c-115">`active` 인스턴스는 요청된 문화권에 대한 위성 어셈블리를 우선순위에 따라 다음과 같이 로드하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="4c68c-116">해당 캐시를 확인하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-116">Checking its cache.</span></span>
    - <span data-ttu-id="4c68c-117">요청된 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>(예:`es-MX`)과 일치하는 하위 디렉터리에 대해 현재 실행 중인 어셈블리의 디렉터리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="4c68c-118">이 기능은 3.0 이전의 .NET Core에서 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="4c68c-119">Linux 및 macOS에서 하위 디렉터리는 대/소문자를 구분하며 다음 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        > - <span data-ttu-id="4c68c-120">대/소문자 구분이 정확히 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-120">Exactly match case.</span></span>
        > - <span data-ttu-id="4c68c-121">소문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-121">Be in lower case.</span></span>

    - <span data-ttu-id="4c68c-122">`active`가 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> 인스턴스인 경우 [기본 위성(리소스) 어셈블리 검색](default-probing.md#satellite-resource-assembly-probing) 논리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="4c68c-123"><xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 함수를 호출 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="4c68c-124"><xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트가 발생 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="4c68c-125"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트가 발생 중입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="4c68c-126">위성 어셈블리가 로드된 경우:</span><span class="sxs-lookup"><span data-stu-id="4c68c-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="4c68c-127"><xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="4c68c-128">어셈블리에서 요청된 리소스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="4c68c-129">런타임이 어셈블리에서 리소스를 찾으면 해당 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="4c68c-130">리소스를 찾지 못하면 검색을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c68c-131">위성 어셈블리 내의 리소스를 찾기 위해 런타임은 <xref:System.Resources.ResourceManager>에서 현재 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>에 대해 요청한 리소스 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4c68c-132">리소스 파일 내에서 요청된 리소스 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="4c68c-133">둘 중 하나라도 찾지 못하면 리소스가 찾을 수 없는 것으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="4c68c-134">런타임은 다음에 여러 잠재적인 수준에서 부모 문화권 어셈블리를 검색하며 매번 2-3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="4c68c-135">각 문화권에는 <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> 속성으로 정의되는 하나의 부모만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="4c68c-136">문화권의 <xref:System.Globalization.CultureInfo.Parent%2A> 속성이 <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>이면 부모 문화권 검색이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="4c68c-137"><xref:System.Globalization.CultureInfo.InvariantCulture>의 경우 2-3 단계로 돌아가지 않고 5단계로 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="4c68c-138">여전히 리소스를 찾을 수 없는 경우 기본(대체) 문화권에 대한 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="4c68c-139">일반적으로 기본 문화권의 리소스는 주 애플리케이션 어셈블리에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="4c68c-140">그러나 <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> 속성에 대해 <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType>을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4c68c-141">이 값은 리소스의 최종 대체 위치가 주 어셈블리가 아닌 위성 어셈블리임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c68c-142">기본 문화권이 최종 대체(fallback)입니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="4c68c-143">따라서 기본 리소스 파일에 완전한 리소스 세트를 항상 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="4c68c-144">이렇게 하면 예외가 throw되지 않도록 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="4c68c-145">전체 집합을 통해 모든 리소스에 대한 대체를 제공하고 사용자에게 항상 리소스가 하나 이상 제공되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="4c68c-146">마지막으로</span><span class="sxs-lookup"><span data-stu-id="4c68c-146">Finally,</span></span>
   - <span data-ttu-id="4c68c-147">런타임이 기본(대체) 문화권에 대한 리소스 파일을 찾지 못하면 <xref:System.Resources.MissingManifestResourceException> 또는 <xref:System.Resources.MissingSatelliteAssemblyException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="4c68c-148">리소스 파일이 있지만 요청된 리소스가 없는 경우 요청에서 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c68c-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
