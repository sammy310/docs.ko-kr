---
title: 어셈블리 버전 관리
description: .NET 어셈블리의 버전 관리에 대해 알아봅니다. CLR을 사용하는 어셈블리의 버전 관리는 모두 어셈블리 수준에서 수행됩니다.
ms.date: 08/20/2019
helpviewer_keywords:
- informational versions
- version numbers, assemblies
- assemblies [.NET Framework], versioning
- resolving assembly binding requests
- versioning, assemblies
ms.assetid: 775ad4fb-914f-453c-98ef-ce1089b6f903
ms.openlocfilehash: fdffbcc0bbafed62228cba35e8f85fbec7f7fbab
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380077"
---
# <a name="assembly-versioning"></a><span data-ttu-id="637e5-104">어셈블리 버전 관리</span><span class="sxs-lookup"><span data-stu-id="637e5-104">Assembly versioning</span></span>

<span data-ttu-id="637e5-105">공용 언어 런타임을 사용하는 어셈블리에 대한 모든 버전 관리는 어셈블리 수준에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-105">All versioning of assemblies that use the common language runtime is done at the assembly level.</span></span> <span data-ttu-id="637e5-106">특정 어셈블리의 버전과 해당 종속 어셈블리 버전은 어셈블리 매니페스트에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-106">The specific version of an assembly and the versions of dependent assemblies are recorded in the assembly's manifest.</span></span> <span data-ttu-id="637e5-107">런타임에서의 버전 정책은, 구성 파일(애플리케이션 구성 파일, 게시자 정책 파일 및 컴퓨터의 관리자 구성 파일)의 명시적인 버전 정책에 의해 재정의된 경우를 제외하고는, 처음 빌드되고 테스트될 때 사용된 버전으로만 애플리케이션이 실행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-107">The default version policy for the runtime is that applications run only with the versions they were built and tested with, unless overridden by explicit version policy in configuration files (the application configuration file, the publisher policy file, and the computer's administrator configuration file).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="637e5-108">버전 관리는 강력한 이름이 지정된 어셈블리에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-108">Versioning is done only on assemblies with strong names.</span></span>  
  
<span data-ttu-id="637e5-109">런타임에서는 어셈블리 바인딩 요청을 단계적으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-109">The runtime performs several steps to resolve an assembly binding request:</span></span>  
  
1. <span data-ttu-id="637e5-110">바인딩할 어셈블리의 버전을 결정하기 위해 원래의 어셈블리 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-110">Checks the original assembly reference to determine the version of the assembly to be bound.</span></span>  
  
2. <span data-ttu-id="637e5-111">버전 정책을 적용하기 위해 적용 가능한 모든 구성 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-111">Checks for all applicable configuration files to apply version policy.</span></span>  
  
3. <span data-ttu-id="637e5-112">원래의 어셈블리 참조 및 구성 파일에 지정된 모든 리디렉션으로부터 정확한 어셈블리를 확인한 다음 호출 어셈블리에 바인딩할 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-112">Determines the correct assembly from the original assembly reference and any redirection specified in the configuration files, and determines the version that should be bound to the calling assembly.</span></span>  
  
4. <span data-ttu-id="637e5-113">전역 어셈블리 캐시와 구성 파일에 지정된 코드 베이스를 확인한 다음 [런타임에서 어셈블리를 찾는 방법](../../framework/deployment/how-the-runtime-locates-assemblies.md)에 설명된 규칙에 따라 애플리케이션의 디렉터리 및 하위 디렉터리를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-113">Checks the global assembly cache, codebases specified in configuration files, and then checks the application's directory and subdirectories using the probing rules explained in [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
<span data-ttu-id="637e5-114">다음 예제에서는 이러한 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-114">The following illustration shows these steps:</span></span>  
  
![어셈블리 바인딩 요청 확인의 단계를 보여주는 다이어그램.](./media/versioning/resolve-assembly-binding-request.gif)
  
<span data-ttu-id="637e5-116">애플리케이션 구성에 대한 자세한 내용은 [앱 구성](../../framework/configure-apps/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="637e5-116">For more information about configuring applications, see [Configure apps](../../framework/configure-apps/index.md).</span></span> <span data-ttu-id="637e5-117">바인딩 정책에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="637e5-117">For more information about binding policy, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="637e5-118">버전 정보</span><span class="sxs-lookup"><span data-stu-id="637e5-118">Version information</span></span>  

<span data-ttu-id="637e5-119">각 어셈블리는 서로 다른 두 가지 방법으로 버전 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-119">Each assembly has two distinct ways of expressing version information:</span></span>  
  
- <span data-ttu-id="637e5-120">어셈블리의 버전 번호는 어셈블리의 이름 및 문화권 정보와 함께 어셈블리 ID를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-120">The assembly's version number, which, together with the assembly name and culture information, is part of the assembly's identity.</span></span> <span data-ttu-id="637e5-121">이 번호는 런타임에서 버전 정책을 적용하는 데 사용되며 또한 런타임에서의 형식 확인 절차에 중요한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-121">This number is used by the runtime to enforce version policy and plays a key part in the type resolution process at run time.</span></span>  
  
- <span data-ttu-id="637e5-122">정보 버전은 버전에 대한 추가 정보를 나타내는 문자열로서, 정보 제공의 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-122">An informational version, which is a string that represents additional version information included for informational purposes only.</span></span>  
  
### <a name="assembly-version-number"></a><span data-ttu-id="637e5-123">어셈블리 버전 번호</span><span class="sxs-lookup"><span data-stu-id="637e5-123">Assembly version number</span></span>  

<span data-ttu-id="637e5-124">각 어셈블리는 ID의 일부로 버전 정보를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-124">Each assembly has a version number as part of its identity.</span></span> <span data-ttu-id="637e5-125">따라서, 런타임에서는 두 개 어셈블리의 버전 번호가 다르면 이들 어셈블리가 서로 완전히 다른 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-125">As such, two assemblies that differ by version number are considered by the runtime to be completely different assemblies.</span></span> <span data-ttu-id="637e5-126">이 버전 번호는 다음과 같은 네 부분의 문자열로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-126">This version number is physically represented as a four-part string with the following format:</span></span>  
  
<span data-ttu-id="637e5-127">\<*주 버전*>.\<*부 버전*>.\<*빌드 번호*>.\<*수정*></span><span class="sxs-lookup"><span data-stu-id="637e5-127">\<*major version*>.\<*minor version*>.\<*build number*>.\<*revision*></span></span>  
  
<span data-ttu-id="637e5-128">예를 들어, 버전 1.5.1254.0에서 1은 주 버전, 5는 부 버전, 1254는 빌드 번호 그리고 0은 수정 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-128">For example, version 1.5.1254.0 indicates 1 as the major version, 5 as the minor version, 1254 as the build number, and 0 as the revision number.</span></span>  
  
<span data-ttu-id="637e5-129">버전 번호는 다른 ID 정보(어셈블리 이름, 공개 키, 해당 애플리케이션과 연관된 다른 어셈블리의 ID 및 관계 등)와 함께 매니페스트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-129">The version number is stored in the assembly manifest along with other identity information, including the assembly name and public key, as well as information on relationships and identities of other assemblies connected with the application.</span></span>  
  
<span data-ttu-id="637e5-130">어셈블리를 빌드할 때 개발 도구는 참조되는 각 어셈블리에 대한 종속 정보를 어셈블리 매니페스트에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-130">When an assembly is built, the development tool records dependency information for each assembly that is referenced in the assembly manifest.</span></span> <span data-ttu-id="637e5-131">런타임에서는 관리자, 애플리케이션 또는 게시자에서 설정한 구성 정보와 함께 이러한 버전 번호를 사용하여, 참조되는 어셈블리의 올바른 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-131">The runtime uses these version numbers, in conjunction with configuration information set by an administrator, an application, or a publisher, to load the proper version of a referenced assembly.</span></span>  
  
<span data-ttu-id="637e5-132">런타임에서는 버전 관리를 위해 일반 어셈블리와 강력한 이름의 어셈블리를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-132">The runtime distinguishes between regular and strong-named assemblies for the purposes of versioning.</span></span> <span data-ttu-id="637e5-133">버전 확인은 강력한 이름의 어셈블리에 대해서만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-133">Version checking only occurs with strong-named assemblies.</span></span>  
  
<span data-ttu-id="637e5-134">버전 바인딩 정책 지정에 대한 자세한 내용은 [앱 구성](../../framework/configure-apps/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="637e5-134">For information about specifying version binding policies, see [Configure apps](../../framework/configure-apps/index.md).</span></span> <span data-ttu-id="637e5-135">런타임에서 버전 정보를 사용하여 특정 어셈블리를 찾는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="637e5-135">For information about how the runtime uses version information to find a particular assembly, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
### <a name="assembly-informational-version"></a><span data-ttu-id="637e5-136">어셈블리 정보 버전</span><span class="sxs-lookup"><span data-stu-id="637e5-136">Assembly informational version</span></span>  

<span data-ttu-id="637e5-137">정보 버전은 추가적인 버전 정보를 제공하는 문자열로서, 정보 제공의 목적으로만 사용되며 런타임에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-137">The informational version is a string that attaches additional version information to an assembly for informational purposes only; this information is not used at run time.</span></span> <span data-ttu-id="637e5-138">이 텍스트 기반 정보 버전에는 제품의 마케팅 정보, 패키징, 제품 이름 등이 포함되며, 런타임에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-138">The text-based informational version corresponds to the product's marketing literature, packaging, or product name and is not used by the runtime.</span></span> <span data-ttu-id="637e5-139">예를 들어, 정보 버전은 "공용 언어 런타임 버전1.0" 또는 "NET Control SP 2"가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-139">For example, an informational version could be "Common Language Runtime version 1.0" or "NET Control SP 2".</span></span> <span data-ttu-id="637e5-140">Microsoft Windows의 파일 속성 대화 상자에서 버전 탭의 "제품 버전" 항목에 이 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-140">On the Version tab of the file properties dialog in Microsoft Windows, this information appears in the item "Product Version".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="637e5-141">임의의 텍스트를 지정할 수 있지만, 문자열이 어셈블리 버전 번호에서 사용하는 형식이 아니거나 이러한 형식이더라도 와일드카드가 포함된 경우 컴파일할 때 경고 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-141">Although you can specify any text, a warning message appears on compilation if the string is not in the format used by the assembly version number, or if it is in that format but contains wildcards.</span></span> <span data-ttu-id="637e5-142">이 경고는 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-142">This warning is harmless.</span></span>  
  
<span data-ttu-id="637e5-143">정보 버전은 사용자 지정 특성인 <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>를 사용하여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="637e5-143">The informational version is represented using the custom attribute <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="637e5-144">정보 버전 특성에 대한 자세한 내용은 [어셈블리 특성 설정](set-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="637e5-144">For more information about the informational version attribute, see [Set assembly attributes](set-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="637e5-145">참조</span><span class="sxs-lookup"><span data-stu-id="637e5-145">See also</span></span>

- [<span data-ttu-id="637e5-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="637e5-146">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="637e5-147">앱 구성</span><span class="sxs-lookup"><span data-stu-id="637e5-147">Configure apps</span></span>](../../framework/configure-apps/index.md)
- [<span data-ttu-id="637e5-148">어셈블리 특성 설정</span><span class="sxs-lookup"><span data-stu-id="637e5-148">Set assembly attributes</span></span>](set-attributes.md)
- [<span data-ttu-id="637e5-149">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="637e5-149">Assemblies in .NET</span></span>](index.md)
