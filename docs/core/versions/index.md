---
title: .NET 런타임 및 SDK의 버전 관리 방법
description: 이 문서에서는 .NET SDK 및 런타임의 버전 관리 방법을 설명합니다(유의적 버전과 유사함).
ms.date: 12/07/2020
ms.openlocfilehash: 2fbc2775f31b4eab1c9883282c58accd9bb2b9f5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633626"
---
# <a name="overview-of-how-net-is-versioned"></a><span data-ttu-id="f91ae-103">.NET의 버전 관리 방법 개요</span><span class="sxs-lookup"><span data-stu-id="f91ae-103">Overview of how .NET is versioned</span></span>

<span data-ttu-id="f91ae-104">[.NET 런타임과 .NET SDK](../introduction.md#sdk-and-runtimes)는 다른 빈도로 새 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-104">The [.NET Runtime and the .NET SDK](../introduction.md#sdk-and-runtimes) add new features at different frequencies.</span></span> <span data-ttu-id="f91ae-105">일반적으로 SDK는 런타임보다 더 자주 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-105">In general, the SDK is updated more frequently than the Runtime.</span></span> <span data-ttu-id="f91ae-106">이 문서에서는 런타임 및 SDK 버전 번호를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-106">This article explains the runtime and the SDK version numbers.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="f91ae-107">버전 관리 정보</span><span class="sxs-lookup"><span data-stu-id="f91ae-107">Versioning details</span></span>

<span data-ttu-id="f91ae-108">.NET 런타임에는 [유의적 버전](#semantic-versioning)을 따르는 버전 관리에 대한 주/부/패치 접근 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-108">The .NET Runtime has a major/minor/patch approach to versioning that follows [semantic versioning](#semantic-versioning).</span></span>

<span data-ttu-id="f91ae-109">.NET SDK는 유의적 버전을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-109">The .NET SDK doesn't follow semantic versioning.</span></span> <span data-ttu-id="f91ae-110">.NET SDK는 더 빠르게 릴리스되며 해당 버전 번호는 정렬된 런타임과 SDK의 자체 부 릴리스 및 패치 릴리스를 모두 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-110">The .NET SDK releases faster and its version numbers must communicate both the aligned runtime and the SDK's own minor and patch releases.</span></span>

<span data-ttu-id="f91ae-111">.NET SDK 버전 번호의 처음 두 위치는 릴리스된 .NET 런타임 버전에 고정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-111">The first two positions of the .NET SDK version number are locked to the .NET Runtime version it released with.</span></span> <span data-ttu-id="f91ae-112">SDK의 각 버전은 이 런타임 또는 다른 하위 버전에 대한 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-112">Each version of the SDK can create applications for this runtime or any lower version.</span></span>

<span data-ttu-id="f91ae-113">SDK 버전 번호의 세 번째 위치는 보조 및 패치 번호를 모두 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-113">The third position of the SDK version number communicates both the minor and patch number.</span></span> <span data-ttu-id="f91ae-114">부 버전에는 100이 곱해집니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-114">The minor version is multiplied by 100.</span></span> <span data-ttu-id="f91ae-115">마지막 두 자리는 패치 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-115">The final two digits represent the patch number.</span></span> <span data-ttu-id="f91ae-116">부 버전 1, 패치 버전 2는 102로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-116">Minor version 1, patch version 2 would be represented as 102.</span></span> <span data-ttu-id="f91ae-117">예를 들어 다음과 같은 런타임 및 SDK 버전 번호 시퀀스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-117">For example, here's a possible sequence of runtime and SDK version numbers:</span></span>

| <span data-ttu-id="f91ae-118">변경</span><span class="sxs-lookup"><span data-stu-id="f91ae-118">Change</span></span>                | <span data-ttu-id="f91ae-119">.NET 런타임</span><span class="sxs-lookup"><span data-stu-id="f91ae-119">.NET Runtime</span></span>      | <span data-ttu-id="f91ae-120">.NET SDK(\*)</span><span class="sxs-lookup"><span data-stu-id="f91ae-120">.NET SDK (\*)</span></span>     |
|-----------------------|-------------------|-------------------|
| <span data-ttu-id="f91ae-121">초기 릴리스</span><span class="sxs-lookup"><span data-stu-id="f91ae-121">Initial release</span></span>       | <span data-ttu-id="f91ae-122">2.2.0</span><span class="sxs-lookup"><span data-stu-id="f91ae-122">2.2.0</span></span>             | <span data-ttu-id="f91ae-123">2.2.100</span><span class="sxs-lookup"><span data-stu-id="f91ae-123">2.2.100</span></span>           |
| <span data-ttu-id="f91ae-124">SDK 패치</span><span class="sxs-lookup"><span data-stu-id="f91ae-124">SDK patch</span></span>             | <span data-ttu-id="f91ae-125">2.2.0</span><span class="sxs-lookup"><span data-stu-id="f91ae-125">2.2.0</span></span>             | <span data-ttu-id="f91ae-126">2.2.101</span><span class="sxs-lookup"><span data-stu-id="f91ae-126">2.2.101</span></span>           |
| <span data-ttu-id="f91ae-127">런타임 및 SDK 패치</span><span class="sxs-lookup"><span data-stu-id="f91ae-127">Runtime and SDK patch</span></span> | <span data-ttu-id="f91ae-128">2.2.1</span><span class="sxs-lookup"><span data-stu-id="f91ae-128">2.2.1</span></span>             | <span data-ttu-id="f91ae-129">2.2.102</span><span class="sxs-lookup"><span data-stu-id="f91ae-129">2.2.102</span></span>           |
| <span data-ttu-id="f91ae-130">SDK 기능 변경</span><span class="sxs-lookup"><span data-stu-id="f91ae-130">SDK feature change</span></span>    | <span data-ttu-id="f91ae-131">2.2.1</span><span class="sxs-lookup"><span data-stu-id="f91ae-131">2.2.1</span></span>             | <span data-ttu-id="f91ae-132">2.2.200</span><span class="sxs-lookup"><span data-stu-id="f91ae-132">2.2.200</span></span>           |

<span data-ttu-id="f91ae-133">참고:</span><span class="sxs-lookup"><span data-stu-id="f91ae-133">NOTES:</span></span>

- <span data-ttu-id="f91ae-134">런타임 기능 업데이트 전에 SDK에 10개의 기능 업데이트가 있는 경우 버전 번호는 2.2.900 이후의 기능 릴리스로 2.2.1000과 같은 숫자를 가진 1000 시리즈로 롤링됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-134">If the SDK has 10 feature updates before a runtime feature update, version numbers roll into the 1000 series with numbers like 2.2.1000 as the feature release following 2.2.900.</span></span> <span data-ttu-id="f91ae-135">이 상황은 발생할 것으로 예상되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-135">This situation isn't expected to occur.</span></span>
- <span data-ttu-id="f91ae-136">기능 릴리스가 없는 99 패치 릴리스는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-136">99 patch releases without a feature release won't occur.</span></span> <span data-ttu-id="f91ae-137">릴리스가 이 숫자에 가까워지면 기능 릴리스가 강제 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-137">If a release approaches this number, it forces a feature release.</span></span>

<span data-ttu-id="f91ae-138">[dotnet/designs](https://github.com/dotnet/designs/pull/29) 리포지토리에서 초기 제안서에 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-138">You can see more details in the initial proposal at the [dotnet/designs](https://github.com/dotnet/designs/pull/29) repository.</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="f91ae-139">유의적 버전</span><span class="sxs-lookup"><span data-stu-id="f91ae-139">Semantic versioning</span></span>

<span data-ttu-id="f91ae-140">.NET *런타임* 은 [유의적 버전(SemVer)](https://semver.org/)을 대략적으로 준수하며, `MAJOR.MINOR.PATCH` 버전 관리를 사용하고, 버전 번호의 다양한 부분으로 변경의 수준 및 종류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-140">The .NET *Runtime* roughly adheres to [Semantic Versioning (SemVer)](https://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="f91ae-141">선택 사항인 `PRERELEASE` 및 `BUILDNUMBER` 부분은 지원되는 릴리스에 포함되지 않으며, 야간 빌드, 소스 대상에서의 로컬 빌드 및 지원되지 않는 미리 보기 릴리스에만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-141">The optional `PRERELEASE` and `BUILDNUMBER` parts are never part of supported releases and only exist on nightly builds, local builds from source targets, and unsupported preview releases.</span></span>

### <a name="understand-runtime-version-number-changes"></a><span data-ttu-id="f91ae-142">런타임 버전 번호 변경 이해</span><span class="sxs-lookup"><span data-stu-id="f91ae-142">Understand runtime version number changes</span></span>

<span data-ttu-id="f91ae-143">다음 경우에는 `MAJOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-143">`MAJOR` is incremented when:</span></span>

- <span data-ttu-id="f91ae-144">제품 또는 새 제품 방향에 중대한 변경이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-144">Significant changes occur to the product, or a new product direction.</span></span>
- <span data-ttu-id="f91ae-145">주요 변경 내용이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-145">Breaking changes were taken.</span></span> <span data-ttu-id="f91ae-146">주요 변경 내용을 받아들이는 데는 높은 장벽이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-146">There's a high bar to accepting breaking changes.</span></span>
- <span data-ttu-id="f91ae-147">이전 버전이 더 이상 지원되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-147">An old version is no longer supported.</span></span>
- <span data-ttu-id="f91ae-148">기존 종속성의 최신 `MAJOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-148">A newer `MAJOR` version of an existing dependency is adopted.</span></span>

<span data-ttu-id="f91ae-149">다음 경우에는 `MINOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-149">`MINOR` is incremented when:</span></span>

- <span data-ttu-id="f91ae-150">공용 API 노출 영역이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-150">Public API surface area is added.</span></span>
- <span data-ttu-id="f91ae-151">새 동작이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-151">A new behavior is added.</span></span>
- <span data-ttu-id="f91ae-152">기존 종속성의 최신 `MINOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-152">A newer `MINOR` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="f91ae-153">새 종속성이 도입된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-153">A new dependency is introduced.</span></span>

<span data-ttu-id="f91ae-154">다음 경우에는 `PATCH`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-154">`PATCH` is incremented when:</span></span>

- <span data-ttu-id="f91ae-155">버그 수정이 이루어진 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-155">Bug fixes are made.</span></span>
- <span data-ttu-id="f91ae-156">최신 플랫폼에 대한 지원이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-156">Support for a newer platform is added.</span></span>
- <span data-ttu-id="f91ae-157">기존 종속성의 최신 `PATCH` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-157">A newer `PATCH` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="f91ae-158">위 경우 중 하나에 해당하지 않는 다른 변경 내용이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="f91ae-158">Any other change doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="f91ae-159">여러 가지 변경이 이루어진 경우에는 개별 변경의 영향을 받는 가장 높은 요소가 증가되고 다음은 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-159">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="f91ae-160">예를 들어 `MAJOR`가 증가하면 `MINOR` 및 `PATCH`는 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-160">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="f91ae-161">`MINOR`가 증가하면 `PATCH`는 0으로 다시 설정되지만 `MAJOR`는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-161">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

## <a name="version-numbers-in-file-names"></a><span data-ttu-id="f91ae-162">파일 이름의 버전 번호</span><span class="sxs-lookup"><span data-stu-id="f91ae-162">Version numbers in file names</span></span>

<span data-ttu-id="f91ae-163">.NET용으로 다운로드한 파일에는 버전(예: `dotnet-sdk-2.1.300-win10-x64.exe`)이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-163">The files downloaded for .NET carry the version, for example, `dotnet-sdk-2.1.300-win10-x64.exe`.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="f91ae-164">미리 보기 버전</span><span class="sxs-lookup"><span data-stu-id="f91ae-164">Preview versions</span></span>

<span data-ttu-id="f91ae-165">미리 보기 버전에는 버전 번호에 `-preview[number]-([build]|"final")`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-165">Preview versions have a `-preview[number]-([build]|"final")` appended to the version number.</span></span> <span data-ttu-id="f91ae-166">예: `2.0.0-preview1-final`.</span><span class="sxs-lookup"><span data-stu-id="f91ae-166">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="f91ae-167">서비스 버전</span><span class="sxs-lookup"><span data-stu-id="f91ae-167">Servicing versions</span></span>

<span data-ttu-id="f91ae-168">릴리스가 출시된 후에 릴리스 분기는 일반적으로 매일 빌드 만들기를 중지하고 대신 서비스 빌드를 만들기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-168">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="f91ae-169">서비스 버전에는 `-servicing-[number]`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-169">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="f91ae-170">예: `2.0.1-servicing-006924`.</span><span class="sxs-lookup"><span data-stu-id="f91ae-170">For example, `2.0.1-servicing-006924`.</span></span>

## <a name="relationship-to-net-standard-versions"></a><span data-ttu-id="f91ae-171">.NET Standard 버전과의 관계</span><span class="sxs-lookup"><span data-stu-id="f91ae-171">Relationship to .NET Standard versions</span></span>

<span data-ttu-id="f91ae-172">.NET Standard는 .NET 참조 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-172">.NET Standard consists of a .NET reference assembly.</span></span> <span data-ttu-id="f91ae-173">각 플랫폼마다 여러 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-173">There are multiple implementations specific to each platform.</span></span> <span data-ttu-id="f91ae-174">참조 어셈블리에는 지정된 .NET Standard 버전의 일부인 .NET API의 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-174">The reference assembly contains the definition of .NET APIs which are part of a given .NET Standard version.</span></span> <span data-ttu-id="f91ae-175">각 구현은 특정 플랫폼의 .NET Standard 계약을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-175">Each implementation fulfills the .NET Standard contract on the specific platform.</span></span>

<span data-ttu-id="f91ae-176">.NET Standard 참조 어셈블리는 `MAJOR.MINOR` 버전 관리 체계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-176">The .NET Standard reference assembly uses a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="f91ae-177">`PATCH` 수준은 .NET Standard에서 유용하지 않습니다. 이는 API 사양(구현 없음)만 노출하고 정의에 따라 API를 변경하면 기능 집합의 변경 내용을 나타내며, 따라서 새 `MINOR` 버전이 변경되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-177">`PATCH` level isn't useful for .NET Standard because it exposes only an API specification (no implementation) and by definition any change to the API would represent a change in the feature set, and thus a new `MINOR` version.</span></span>

<span data-ttu-id="f91ae-178">각 플랫폼의 구현은 일반적으로 플랫폼 릴리스의 일부로 업데이트될 수 있으므로, 해당 플랫폼에서 .NET Standard를 사용하는 프로그래머에게는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91ae-178">The implementations on each platform may be updated, typically as part of the platform release, and thus not evident to the programmers using .NET Standard on that platform.</span></span>

<span data-ttu-id="f91ae-179">자세한 내용은 [.NET 표준](../../standard/net-standard.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f91ae-179">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f91ae-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f91ae-180">See also</span></span>

- [<span data-ttu-id="f91ae-181">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="f91ae-181">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="f91ae-182">.NET 배포 패키징</span><span class="sxs-lookup"><span data-stu-id="f91ae-182">.NET distribution packaging</span></span>](../distribution-packaging.md)
- [<span data-ttu-id="f91ae-183">.NET 지원 수명 주기 팩트 시트</span><span class="sxs-lookup"><span data-stu-id="f91ae-183">.NET Support Lifecycle Fact Sheet</span></span>](https://dotnet.microsoft.com/platform/support/policy)
- [<span data-ttu-id="f91ae-184">.NET용 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="f91ae-184">Docker images for .NET</span></span>](https://hub.docker.com/_/microsoft-dotnet/)
