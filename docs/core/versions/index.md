---
title: .NET Core 런타임 및 SDK의 버전 관리 방법
description: 이 문서에서는 .NET Core SDK 및 런타임의 버전 관리 방법을 설명합니다(유의적 버전과 유사함).
ms.date: 07/26/2018
ms.openlocfilehash: c85a2112b439768068663688947960ac814de824
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777324"
---
# <a name="overview-of-how-net-core-is-versioned"></a><span data-ttu-id="56486-103">.NET Core의 버전 관리 방법 개요</span><span class="sxs-lookup"><span data-stu-id="56486-103">Overview of how .NET Core is versioned</span></span>

<span data-ttu-id="56486-104">.NET core는 애플리케이션을 개발하는 데 필요한 도구를 포함하는 .NET Core 런타임 및 .NET Core SDK를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="56486-104">.NET Core refers to the .NET Core Runtime and the .NET Core SDK, which contains the tools you need to develop applications.</span></span> <span data-ttu-id="56486-105">.NET Core SDK는 이전 버전의 .NET Core 런타임에서 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-105">.NET Core SDKs are designed to work with any previous version of the .NET Core Runtime.</span></span> <span data-ttu-id="56486-106">이 문서에서는 런타임 및 SDK 버전 전략을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-106">This article explains the runtime and the SDK version strategy.</span></span> <span data-ttu-id="56486-107">.NET Standard의 버전 번호에 대한 설명은 [.NET Standard](../../standard/net-standard.md#net-implementation-support)를 소개하는 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-107">An explanation of version numbers for .NET Standard can be found in the article introducing [.NET Standard](../../standard/net-standard.md#net-implementation-support).</span></span>

<span data-ttu-id="56486-108">.NET Core 런타임 및.NET Core SDK는 다른 속도로 새 기능을 추가합니다. 일반적으로 .NET Core SDK는 .NET Core 런타임이 프로덕션 환경에서 사용하는 런타임을 변경하는 것보다 신속하게 업데이트된 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-108">The .NET Core Runtime and .NET Core SDK add new features at a different rate - in general the .NET Core SDK provides updated tools more quickly than the .NET Core Runtime changes the runtime you use in production.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="56486-109">버전 관리 정보</span><span class="sxs-lookup"><span data-stu-id="56486-109">Versioning details</span></span>

<span data-ttu-id="56486-110">".NET Core 2.1"은 .NET Core 런타임 버전 번호를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="56486-110">".NET Core 2.1" refers to the .NET Core Runtime version number.</span></span> <span data-ttu-id="56486-111">.NET Core 런타임에는 [유의적 버전](#semantic-versioning)을 따르는 버전 관리에 대한 주/부/패치 접근 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-111">The .NET Core Runtime has a major/minor/patch approach to versioning that follows [semantic versioning](#semantic-versioning).</span></span>

<span data-ttu-id="56486-112">.NET Core SDK는 유의적 버전을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-112">The .NET Core SDK doesn't follow semantic versioning.</span></span> <span data-ttu-id="56486-113">.NET Core SDK는 더 빠르게 릴리스되며 해당 버전은 정렬된 런타임과 SDK의 자체 보조 및 패치 릴리스 모두를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-113">The .NET Core SDK releases faster and its versions must communicate both the aligned runtime and the SDK's own minor and patch releases.</span></span> <span data-ttu-id="56486-114">.NET Core SDK 버전의 처음 두 위치는 릴리스된 .NET Core 런타임에 고정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-114">The first two positions of the .NET Core SDK version are locked to the .NET Core Runtime it released with.</span></span> <span data-ttu-id="56486-115">SDK의 각 버전은 이 런타임 또는 다른 하위 버전에 대한 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-115">Each version of the SDK can create applications for this runtime or any lower version.</span></span>

<span data-ttu-id="56486-116">SDK 버전 번호의 세 번째 위치는 보조 및 패치 번호를 모두 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-116">The third position of the SDK version number communicates both the minor and patch number.</span></span> <span data-ttu-id="56486-117">부 버전에는 100이 곱해집니다.</span><span class="sxs-lookup"><span data-stu-id="56486-117">The minor version is multiplied by 100.</span></span> <span data-ttu-id="56486-118">부 버전 1, 패치 버전 2는 102로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-118">Minor version 1, patch version 2 would be represented as 102.</span></span> <span data-ttu-id="56486-119">마지막 두 자리는 패치 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56486-119">The final two digits represent the patch number.</span></span> <span data-ttu-id="56486-120">예를 들어 .NET Core 2.2의 릴리스에서는 다음 표와 같은 릴리스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-120">For example, the release of .NET Core 2.2 may create releases like the following table:</span></span>

| <span data-ttu-id="56486-121">변화</span><span class="sxs-lookup"><span data-stu-id="56486-121">Change</span></span>                | <span data-ttu-id="56486-122">.NET Core 런타임</span><span class="sxs-lookup"><span data-stu-id="56486-122">.NET Core Runtime</span></span> | <span data-ttu-id="56486-123">.NET Core SDK(\*)</span><span class="sxs-lookup"><span data-stu-id="56486-123">.NET Core SDK (\*)</span></span> |
|-----------------------|-------------------|-------------------|
| <span data-ttu-id="56486-124">초기 릴리스</span><span class="sxs-lookup"><span data-stu-id="56486-124">Initial release</span></span>       | <span data-ttu-id="56486-125">2.2.0</span><span class="sxs-lookup"><span data-stu-id="56486-125">2.2.0</span></span>             | <span data-ttu-id="56486-126">2.2.100</span><span class="sxs-lookup"><span data-stu-id="56486-126">2.2.100</span></span>           |
| <span data-ttu-id="56486-127">SDK 패치</span><span class="sxs-lookup"><span data-stu-id="56486-127">SDK Patch</span></span>             | <span data-ttu-id="56486-128">2.2.0</span><span class="sxs-lookup"><span data-stu-id="56486-128">2.2.0</span></span>             | <span data-ttu-id="56486-129">2.2.101</span><span class="sxs-lookup"><span data-stu-id="56486-129">2.2.101</span></span>           |
| <span data-ttu-id="56486-130">런타임 및 SDK 패치</span><span class="sxs-lookup"><span data-stu-id="56486-130">Runtime and SDK Patch</span></span> | <span data-ttu-id="56486-131">2.2.1</span><span class="sxs-lookup"><span data-stu-id="56486-131">2.2.1</span></span>             | <span data-ttu-id="56486-132">2.2.102</span><span class="sxs-lookup"><span data-stu-id="56486-132">2.2.102</span></span>           |
| <span data-ttu-id="56486-133">SDK 기능 변경</span><span class="sxs-lookup"><span data-stu-id="56486-133">SDK Feature change</span></span>    | <span data-ttu-id="56486-134">2.2.1</span><span class="sxs-lookup"><span data-stu-id="56486-134">2.2.1</span></span>             | <span data-ttu-id="56486-135">2.2.200</span><span class="sxs-lookup"><span data-stu-id="56486-135">2.2.200</span></span>           |

<span data-ttu-id="56486-136">(\*) 기록 아티팩트에 따라 .NET Core 2.1의 첫 번째 SDK가 2.1.300이기 때문에 이 차트는 2.2 .NET Core Runtime을 예제로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-136">(\*) This chart uses the 2.2 .NET Core Runtime as the example because a historic artifact meant the first SDK for .NET Core 2.1 is 2.1.300.</span></span> <span data-ttu-id="56486-137">자세한 내용은 [.NET Core 버전 선택](selection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56486-137">For more information, See the [.NET Core version selection](selection.md).</span></span>

<span data-ttu-id="56486-138">참고:</span><span class="sxs-lookup"><span data-stu-id="56486-138">NOTES:</span></span>

- <span data-ttu-id="56486-139">런타임 기능 업데이트 전에 SDK에 10개의 기능 업데이트가 있는 경우 버전 번호는 2.2.900 이후의 기능 릴리스로 2.2.1000과 같은 숫자를 가진 1000 시리즈로 롤링됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-139">If the SDK has 10 feature updates before a runtime feature update, version numbers roll into the 1000 series with numbers like 2.2.1000 as the feature release following 2.2.900.</span></span> <span data-ttu-id="56486-140">이 상황은 발생할 것으로 예상되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-140">This situation isn't expected to occur.</span></span>
- <span data-ttu-id="56486-141">기능 릴리스가 없는 99 패치 릴리스는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-141">99 patch releases without a feature release won't occur.</span></span> <span data-ttu-id="56486-142">릴리스가 이 숫자에 가까워지면 기능 릴리스가 강제 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-142">If a release approaches this number, it forces a feature release.</span></span>

<span data-ttu-id="56486-143">[dotnet/designs](https://github.com/dotnet/designs/pull/29) 리포지토리에서 초기 제안서에 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-143">You can see more details in the initial proposal at the [dotnet/designs](https://github.com/dotnet/designs/pull/29) repository.</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="56486-144">유의적 버전</span><span class="sxs-lookup"><span data-stu-id="56486-144">Semantic versioning</span></span>

<span data-ttu-id="56486-145">.NET Core *런타임*은 [유의적 버전(SemVer)](https://semver.org/)을 대략적으로 준수하며, `MAJOR.MINOR.PATCH` 버전 관리를 사용하고, 버전 번호의 다양한 부분으로 변경의 수준 및 종류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-145">The .NET Core *Runtime* roughly adheres to [Semantic Versioning (SemVer)](https://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="56486-146">선택 사항인 `PRERELEASE` 및 `BUILDNUMBER` 부분은 지원되는 릴리스에 포함되지 않으며, 야간 빌드, 소스 대상에서의 로컬 빌드 및 지원되지 않는 미리 보기 릴리스에만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-146">The optional `PRERELEASE` and `BUILDNUMBER` parts are never part of supported releases and only exist on nightly builds, local builds from source targets, and unsupported preview releases.</span></span>

### <a name="understand-runtime-version-number-changes"></a><span data-ttu-id="56486-147">런타임 버전 번호 변경 이해</span><span class="sxs-lookup"><span data-stu-id="56486-147">Understand runtime version number changes</span></span>

<span data-ttu-id="56486-148">다음 경우에는 `MAJOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-148">`MAJOR` is incremented when:</span></span>

- <span data-ttu-id="56486-149">제품 또는 새 제품 방향에 중대한 변경이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-149">Significant changes occur to the product, or a new product direction.</span></span>
- <span data-ttu-id="56486-150">주요 변경 내용이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-150">Breaking changes were taken.</span></span> <span data-ttu-id="56486-151">주요 변경 내용을 받아들이는 데는 높은 장벽이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-151">There's a high bar to accepting breaking changes.</span></span>
- <span data-ttu-id="56486-152">이전 버전이 더 이상 지원되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="56486-152">An old version is no longer supported.</span></span>
- <span data-ttu-id="56486-153">기존 종속성의 최신 `MAJOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-153">A newer `MAJOR` version of an existing dependency is adopted.</span></span>

<span data-ttu-id="56486-154">다음 경우에는 `MINOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-154">`MINOR` is incremented when:</span></span>

- <span data-ttu-id="56486-155">공용 API 노출 영역이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-155">Public API surface area is added.</span></span>
- <span data-ttu-id="56486-156">새 동작이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-156">A new behavior is added.</span></span>
- <span data-ttu-id="56486-157">기존 종속성의 최신 `MINOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-157">A newer `MINOR` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="56486-158">새 종속성이 도입된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-158">A new dependency is introduced.</span></span>

<span data-ttu-id="56486-159">다음 경우에는 `PATCH`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-159">`PATCH` is incremented when:</span></span>

- <span data-ttu-id="56486-160">버그 수정이 이루어진 경우</span><span class="sxs-lookup"><span data-stu-id="56486-160">Bug fixes are made.</span></span>
- <span data-ttu-id="56486-161">최신 플랫폼에 대한 지원이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-161">Support for a newer platform is added.</span></span>
- <span data-ttu-id="56486-162">기존 종속성의 최신 `PATCH` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="56486-162">A newer `PATCH` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="56486-163">위 경우 중 하나에 해당하지 않는 다른 변경 내용이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="56486-163">Any other change doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="56486-164">여러 가지 변경이 이루어진 경우에는 개별 변경의 영향을 받는 가장 높은 요소가 증가되고 다음은 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-164">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="56486-165">예를 들어 `MAJOR`가 증가하면 `MINOR` 및 `PATCH`는 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-165">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="56486-166">`MINOR`가 증가하면 `PATCH`는 0으로 다시 설정되지만 `MAJOR`는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-166">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

## <a name="version-numbers-in-file-names"></a><span data-ttu-id="56486-167">파일 이름의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="56486-167">Version numbers in file names</span></span>

<span data-ttu-id="56486-168">.NET Core용으로 다운로드 한 파일에는 버전(예: `dotnet-sdk-2.1.300-win10-x64.exe`)이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-168">The files downloaded for .NET Core carry the version, for example, `dotnet-sdk-2.1.300-win10-x64.exe`.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="56486-169">미리 보기 버전</span><span class="sxs-lookup"><span data-stu-id="56486-169">Preview versions</span></span>

<span data-ttu-id="56486-170">미리 보기 버전에는 `-preview[number]-([build]|"final")`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-170">Preview versions have a `-preview[number]-([build]|"final")` appended to the version.</span></span> <span data-ttu-id="56486-171">예: `2.0.0-preview1-final`.</span><span class="sxs-lookup"><span data-stu-id="56486-171">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="56486-172">서비스 버전</span><span class="sxs-lookup"><span data-stu-id="56486-172">Servicing versions</span></span>

<span data-ttu-id="56486-173">릴리스가 출시된 후에 릴리스 분기는 일반적으로 매일 빌드 만들기를 중지하고 대신 서비스 빌드를 만들기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-173">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="56486-174">서비스 버전에는 `-servicing-[number]`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-174">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="56486-175">예: `2.0.1-servicing-006924`.</span><span class="sxs-lookup"><span data-stu-id="56486-175">For example, `2.0.1-servicing-006924`.</span></span>

## <a name="relationship-to-net-standard-versions"></a><span data-ttu-id="56486-176">.NET Standard 버전과의 관계</span><span class="sxs-lookup"><span data-stu-id="56486-176">Relationship to .NET Standard versions</span></span>

<span data-ttu-id="56486-177">.NET Standard는 .NET 참조 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56486-177">.NET Standard consists of a .NET reference assembly.</span></span> <span data-ttu-id="56486-178">각 플랫폼마다 여러 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-178">There are multiple implementations specific to each platform.</span></span> <span data-ttu-id="56486-179">참조 어셈블리에는 지정된 .NET Standard 버전의 일부인 .NET API의 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-179">The reference assembly contains the definition of .NET APIs which are part of a given .NET Standard version.</span></span> <span data-ttu-id="56486-180">각 구현은 특정 플랫폼의 .NET Standard 계약을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-180">Each implementation fulfills the .NET Standard contract on the specific platform.</span></span> <span data-ttu-id="56486-181">.NET 가이드의 [.NET Standard](../../standard/net-standard.md)에 대한 문서에서 .NET Standard에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-181">You can learn more about .NET Standard in the article on [.NET Standard](../../standard/net-standard.md) in the .NET Guide.</span></span>

<span data-ttu-id="56486-182">.NET Standard 참조 어셈블리는 `MAJOR.MINOR` 버전 관리 체계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-182">The .NET Standard reference assembly uses a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="56486-183">`PATCH` 수준은 .NET Standard에서 유용하지 않습니다. 이는 API 사양(구현 없음)만 노출하고 정의에 따라 API를 변경하면 기능 집합의 변경 내용을 나타내며, 따라서 새 `MINOR` 버전이 변경되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="56486-183">`PATCH` level isn't useful for .NET Standard because it exposes only an API specification (no implementation) and by definition any change to the API would represent a change in the feature set, and thus a new `MINOR` version.</span></span>

<span data-ttu-id="56486-184">각 플랫폼의 구현은 일반적으로 플랫폼 릴리스의 일부로 업데이트될 수 있으므로, 해당 플랫폼에서 .NET Standard를 사용하는 프로그래머에게는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56486-184">The implementations on each platform may be updated, typically as part of the platform release, and thus not evident to the programmers using .NET Standard on that platform.</span></span>

<span data-ttu-id="56486-185">.NET Core의 각 버전은 .NET Standard의 버전을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-185">Each version of .NET Core implements a version of .NET Standard.</span></span> <span data-ttu-id="56486-186">.NET Standard의 버전을 구현하면 이전 버전의 .NET Standard를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-186">Implementing a version of .NET Standard implies support for previous versions of .NET Standard.</span></span> <span data-ttu-id="56486-187">.NET standard 및 .NET Core 버전을 독립적으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-187">.NET Standard and .NET Core version independently.</span></span> <span data-ttu-id="56486-188">.NET Core 2.0이 .NET Standard 2.0을 구현한 것은 우연의 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="56486-188">It's a coincidence that .NET Core 2.0 implements .NET Standard 2.0.</span></span> <span data-ttu-id="56486-189">.NET Core 2.1은 또한 .NET Standard 2.0을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-189">.NET Core 2.1 also implements .NET Standard 2.0.</span></span> <span data-ttu-id="56486-190">.NET Core는 .NET Standard의 향후 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="56486-190">.NET Core will support future versions of .NET Standard as they become available.</span></span>

| <span data-ttu-id="56486-191">.NET Core</span><span class="sxs-lookup"><span data-stu-id="56486-191">.NET Core</span></span> | <span data-ttu-id="56486-192">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="56486-192">.NET Standard</span></span> |
|-----------|---------------|
| <span data-ttu-id="56486-193">1.0</span><span class="sxs-lookup"><span data-stu-id="56486-193">1.0</span></span>       | <span data-ttu-id="56486-194">최대 1.6</span><span class="sxs-lookup"><span data-stu-id="56486-194">up to 1.6</span></span>     |
| <span data-ttu-id="56486-195">2.0</span><span class="sxs-lookup"><span data-stu-id="56486-195">2.0</span></span>       | <span data-ttu-id="56486-196">최대 2.0</span><span class="sxs-lookup"><span data-stu-id="56486-196">up to 2.0</span></span>     |
| <span data-ttu-id="56486-197">2.1</span><span class="sxs-lookup"><span data-stu-id="56486-197">2.1</span></span>       | <span data-ttu-id="56486-198">최대 2.0</span><span class="sxs-lookup"><span data-stu-id="56486-198">up to 2.0</span></span>     |
| <span data-ttu-id="56486-199">2.2</span><span class="sxs-lookup"><span data-stu-id="56486-199">2.2</span></span>       | <span data-ttu-id="56486-200">최대 2.0</span><span class="sxs-lookup"><span data-stu-id="56486-200">up to 2.0</span></span>     |
| <span data-ttu-id="56486-201">3.0</span><span class="sxs-lookup"><span data-stu-id="56486-201">3.0</span></span>       | <span data-ttu-id="56486-202">최대 2.1</span><span class="sxs-lookup"><span data-stu-id="56486-202">up to 2.1</span></span>     |

## <a name="see-also"></a><span data-ttu-id="56486-203">참조</span><span class="sxs-lookup"><span data-stu-id="56486-203">See also</span></span>

- [<span data-ttu-id="56486-204">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="56486-204">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="56486-205">.NET Core 배포 패키징</span><span class="sxs-lookup"><span data-stu-id="56486-205">.NET Core distribution packaging</span></span>](../build/distribution-packaging.md)
- <span data-ttu-id="56486-206">[.NET Core Support Lifecycle Fact Sheet](https://dotnet.microsoft.com/platform/support/policy)(.NET Core 지원 수명 주기 팩트 시트)</span><span class="sxs-lookup"><span data-stu-id="56486-206">[.NET Core Support Lifecycle Fact Sheet](https://dotnet.microsoft.com/platform/support/policy)</span></span>
- [<span data-ttu-id="56486-207">.NET Core 2+ 버전 바인딩</span><span class="sxs-lookup"><span data-stu-id="56486-207">.NET Core 2+ Version Binding</span></span>](https://github.com/dotnet/designs/issues/3)
- [<span data-ttu-id="56486-208">.NET Core용 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="56486-208">Docker images for .NET Core</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
