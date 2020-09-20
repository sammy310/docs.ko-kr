---
title: 트리밍 옵션
description: 자체 포함 앱의 트리밍을 제어하는 방법을 알아봅니다.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 89bd195a97c2f1bbbba9199fea51c917c4e4836b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515834"
---
# <a name="trimming-options"></a><span data-ttu-id="5e82e-103">트리밍 옵션</span><span class="sxs-lookup"><span data-stu-id="5e82e-103">Trimming options</span></span>

<span data-ttu-id="5e82e-104">다음 MSBuild 속성 및 항목은 [트리밍된 자체 포함 배포](trim-self-contained.md)의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="5e82e-105">일부 옵션에는 트리밍을 구현하는 기본 도구의 이름인 `ILLink`가 언급됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="5e82e-106">기본 도구에 대한 자세한 내용은 [링커 설명서](https://github.com/mono/linker/tree/master/docs)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-106">More information about the underlying tool can be found at the [Linker documentation](https://github.com/mono/linker/tree/master/docs).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="5e82e-107">트리밍 사용</span><span class="sxs-lookup"><span data-stu-id="5e82e-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="5e82e-108">SDK에서 정의한 기본 설정을 사용하여 게시 중에 트리밍을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="5e82e-109">`Microsoft.NET.Sdk`를 사용하는 경우 netcoreapp 런타임 팩에서 프레임워크 어셈블리의 어셈블리 수준 트리밍을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="5e82e-110">애플리케이션 코드와 프레임워크가 아닌 라이브러리는 트리밍되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="5e82e-111">다른 SDK는 서로 다른 기본값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="5e82e-112">트리밍 세분성</span><span class="sxs-lookup"><span data-stu-id="5e82e-112">Trimming granularity</span></span>

<span data-ttu-id="5e82e-113">다음 세분성 설정은 적극적으로 사용되지 않는 IL을 삭제하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="5e82e-114">해당 항목은 속성으로 설정하거나 [개별 어셈블리](#trimmed-assemblies)에서 메타데이터로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-114">This can be set as a property, or as metadata on an [individual assembly](#trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="5e82e-115">어셈블리 수준 트리밍을 사용하면 어셈블리의 일부가 정적으로 인식되는 방식으로 사용되는 경우 전체 어셈블리가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="5e82e-116">멤버 수준 트리밍을 사용하면 형식에서 사용되지 않는 멤버가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="5e82e-117">`<IsTrimmable>true</IsTrimmable>` 메타데이터가 있지만 명시적 `TrimMode`가 없는 어셈블리는 전역 `TrimMode`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="5e82e-118">`Microsoft.NET.Sdk`의 기본값 `TrimMode`는 `copyused`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="5e82e-119">트리밍된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="5e82e-119">Trimmed assemblies</span></span>

<span data-ttu-id="5e82e-120">트리밍된 앱을 게시하면 SDK는 트리밍을 위해 처리할 파일 세트를 나타내는 `ManagedAssemblyToLink`라는 `ItemGroup`을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="5e82e-121">`ManagedAssemblyToLink`에는 어셈블리별로 트리밍 동작을 제어하는 메타데이터가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="5e82e-122">해당 메타데이터를 설정하려면 기본 제공 `PrepareForILLink` 대상 전에 실행되는 대상을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="5e82e-123">다음 예제에서는 `MyAssembly` 트리밍을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-123">The following example shows how to enable trimming of `MyAssembly`.</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="5e82e-124">SDK는 게시 중에 해당 세트를 계산하고 변경하지 않을 것으로 예상하기 때문에 `ManagedAssemblyToLink`에서 항목을 추가하거나 제거하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="5e82e-125">지원되는 메타데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="5e82e-126">지정된 어셈블리가 트리밍되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="5e82e-127">`<TrimMode>copyused</TrimMode>` 또는 `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="5e82e-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="5e82e-128">해당 어셈블리의 [트리밍 세분성](#trimming-granularity)을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-128">Control the [trimming granularity](#trimming-granularity) of this assembly.</span></span> <span data-ttu-id="5e82e-129">이 옵션은 전역 `TrimMode`보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="5e82e-130">어셈블리에서 `TrimMode`를 설정하는 것은 `<IsTrimmable>true</IsTrimmable>`을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="5e82e-131">루트 어셈블리</span><span class="sxs-lookup"><span data-stu-id="5e82e-131">Root assemblies</span></span>

<span data-ttu-id="5e82e-132">`<IsTrimmable>true</IsTrimmable>`이 없는 모든 어셈블리는 분석의 루트로 고려됩니다. 즉, 모든 어셈블리와 정적으로 인식되는 모든 종속성이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-132">All assemblies that do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="5e82e-133">추가 어셈블리는 이름(`.dll` 확장명이 없음)으로 “루트로 지정” 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="5e82e-134">루트 설명자</span><span class="sxs-lookup"><span data-stu-id="5e82e-134">Root descriptors</span></span>

<span data-ttu-id="5e82e-135">분석을 위한 루트를 지정하는 또 다른 방법은 링커 [설명자 형식](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format)을 사용하는 XML 파일을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="5e82e-136">이렇게 하면 전체 어셈블리가 아닌 특정 멤버를 루트로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="5e82e-137">예를 들어 `MyRoots.xml`은 애플리케이션에서 동적으로 액세스하는 특정 메서드를 루트로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="5e82e-138">분석 경고</span><span class="sxs-lookup"><span data-stu-id="5e82e-138">Analysis warnings</span></span>

<span data-ttu-id="5e82e-139">트리밍은 정적으로 연결할 수 없는 IL을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="5e82e-140">리플렉션을 사용하는 앱 또는 동적 종속성을 만드는 다른 패턴은 트리밍을 통해 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="5e82e-141">해당 패턴에 관해 경고하려면:</span><span class="sxs-lookup"><span data-stu-id="5e82e-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="5e82e-142">트리밍 분석 경고를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="5e82e-143">여기에는 고유한 코드, 라이브러리 코드 및 프레임워크 코드를 비롯한 전체 앱에 관한 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="5e82e-144">경고 버전</span><span class="sxs-lookup"><span data-stu-id="5e82e-144">Warning versions</span></span>

<span data-ttu-id="5e82e-145">트리밍 분석은 SDK에서 분석 경고 버전을 제어하는 [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) 속성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="5e82e-146">트리밍 분석 경고의 버전을 독립적으로 제어하는 또 다른 속성이 있습니다(컴파일러의 `WarningLevel`과 비슷함).</span><span class="sxs-lookup"><span data-stu-id="5e82e-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="5e82e-147">지정된 수준 이하의 경고만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="5e82e-148">모든 경고 버전을 포함하려면 `9999`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="5e82e-149">경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="5e82e-149">Suppressing warnings</span></span>

<span data-ttu-id="5e82e-150">`NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` 및 `TreatWarningsAsErrors`를 포함하여 도구 체인에서 적용하는 일반적인 MSBuild 속성을 사용하여 개별 [경고 코드](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes)를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="5e82e-151">ILLink 오류로 경고 동작을 독립적으로 제어하는 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="5e82e-152">ILLink 경고를 오류로 처리하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="5e82e-153">이렇게 하면 전역으로 컴파일러 경고를 오류로 처리할 때 트리밍 분석 경고를 오류로 전환하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="5e82e-154">기호 제거</span><span class="sxs-lookup"><span data-stu-id="5e82e-154">Removing symbols</span></span>

<span data-ttu-id="5e82e-155">기호는 일반적으로 어셈블리와 일치하도록 트리밍됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="5e82e-156">모든 기호를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="5e82e-157">포함된 PDB 및 별도 PDB 파일을 포함하여 트리밍된 애플리케이션에서 기호를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="5e82e-158">이는 애플리케이션 코드 및 기호와 함께 제공되는 모든 종속성 둘 다에 다 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="5e82e-159">SDK를 사용하여 `DebuggerSupport` 속성을 통해 디버거 지원을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="5e82e-160">디버거 지원이 사용되지 않으면 트리밍은 기호를 자동으로 제거합니다(`TrimmerRemoveSymbols`가 기본적으로 true로 설정됨).</span><span class="sxs-lookup"><span data-stu-id="5e82e-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>

## <a name="trimming-framework-library-features"></a><span data-ttu-id="5e82e-161">프레임워크 라이브러리 기능 트리밍</span><span class="sxs-lookup"><span data-stu-id="5e82e-161">Trimming framework library features</span></span>

<span data-ttu-id="5e82e-162">프레임워크 라이브러리의 여러 기능 영역은 사용할 수 없는 기능의 코드를 제거할 수 있도록 설정하는 링커 지시문과 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-162">Several feature areas of the framework libraries come with linker directives that make it possible to remove the code for disabled features.</span></span>

- `<DebuggerSupport>false</DebuggerSupport>`

    <span data-ttu-id="5e82e-163">더 나은 디버깅 환경을 가능하게 하는 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-163">Remove code that enables better debugging experiences.</span></span> <span data-ttu-id="5e82e-164">이렇게 하면 [기호도 제거](#removing-symbols)됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-164">This will also [remove symbols](#removing-symbols).</span></span>

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    <span data-ttu-id="5e82e-165">BinaryFormatter serialization 지원을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-165">Remove BinaryFormatter serialization support.</span></span> <span data-ttu-id="5e82e-166">자세한 내용은 [BinaryFormatter serialization 메서드가 사용되지 않음](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-166">For more information, see [BinaryFormatter serialization methods are obsolete](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps).</span></span>

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    <span data-ttu-id="5e82e-167">안전하지 않은 UTF-7 인코딩 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-167">Remove insecure UTF-7 encoding code.</span></span> <span data-ttu-id="5e82e-168">자세한 내용은 [UTF-7 코드 경로가 사용되지 않음](../compatibility/corefx.md#utf-7-code-paths-are-obsolete)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-168">For more information, see [UTF-7 code paths are obsolete](../compatibility/corefx.md#utf-7-code-paths-are-obsolete).</span></span>

- `<EventSourceSupport>false</EventSourceSupport>`

    <span data-ttu-id="5e82e-169">EventSource 관련 코드 또는 논리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-169">Remove EventSource related code or logic.</span></span>

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    <span data-ttu-id="5e82e-170">System.Net.Http의 진단 지원과 관련된 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-170">Remove code related to diagnostics support for System.Net.Http.</span></span>

- `<InvariantGlobalization>true</InvariantGlobalization>`

    <span data-ttu-id="5e82e-171">세계화 특정 코드 및 데이터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-171">Remove globalization specific code and data.</span></span> <span data-ttu-id="5e82e-172">자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-172">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    <span data-ttu-id="5e82e-173">`System.*` 어셈블리에 대한 예외 메시지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-173">Strip exception messages for `System.*` assemblies.</span></span> <span data-ttu-id="5e82e-174">`System.*` 어셈블리에서 예외가 throw되면 메시지는 전체 메시지가 아니라 단순화된 리소스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-174">When an exception is thrown from a `System.*` assembly, the message will be a simplified resource ID instead of the full message.</span></span>

 <span data-ttu-id="5e82e-175">해당 속성은 관련 코드가 트리밍되도록 하며 [runtimeconfig](../run-time-config/index.md) 파일을 통해 기능도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-175">These properties will cause the related code to be trimmed and will also disable features via the [runtimeconfig](../run-time-config/index.md) file.</span></span> <span data-ttu-id="5e82e-176">해당 runtimeconfig 옵션을 포함하여 해당 속성에 대한 자세한 내용은 [기능 스위치](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e82e-176">For more information about these properties, including the corresponding runtimeconfig options, see [feature switches](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span></span> <span data-ttu-id="5e82e-177">일부 SDK에는 해당 속성의 기본값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e82e-177">Some SDKs may have default values for these properties.</span></span>
