---
ms.openlocfilehash: cd7860a5dfff1eb595625665382689733cffc94a
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90721258"
---
### <a name="ca1416-platform-compatibility"></a><span data-ttu-id="0a3af-101">CA1416: 플랫폼 호환성</span><span class="sxs-lookup"><span data-stu-id="0a3af-101">CA1416: Platform compatibility</span></span>

<span data-ttu-id="0a3af-102">.NET 코드 분석기 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-102">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="0a3af-103">운영 체제를 확인하지 않는 호출 사이트에서 플랫폼별 API에 대한 호출의 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-103">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0a3af-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0a3af-104">Change description</span></span>

<span data-ttu-id="0a3af-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="0a3af-106">[CA1416](/visualstudio/code-quality/ca1416)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-106">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="0a3af-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="0a3af-108">규칙 CA1416은 플랫폼 컨텍스트가 확인되지 않는 위치에서 플랫폼별 API를 사용하는 경우 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-108">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="0a3af-109">규칙 [CA1416](/visualstudio/code-quality/ca1416), 플랫폼 호환성 분석기는 .NET 5.0에 새로 도입된 다른 일부 기능과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-109">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="0a3af-110">.NET 5.0에는 API를 ‘지원’하거나 ‘지원하지 않는’ 플랫폼을 지정할 수 있는 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>가 도입되었습니다. </span><span class="sxs-lookup"><span data-stu-id="0a3af-110">.NET 5.0 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="0a3af-111">이러한 특성이 없으면 API는 모든 플랫폼에서 지원되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-111">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="0a3af-112">해당 특성은 핵심 .NET 라이브러리의 플랫폼별 API에 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-112">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="0a3af-113">해당 API를 사용할 수 없는 플랫폼을 대상으로 하는 프로젝트에서 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 플랫폼 컨텍스트가 확인되지 않는 플랫폼별 API 호출을 플래그로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-113">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="0a3af-114">현재 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> 특성으로 데코레이트된 대부분의 API는 지원되지 않는 운영 체제에서 호출되는 경우 <xref:System.PlatformNotSupportedException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-114">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="0a3af-115">이러한 API는 플랫폼별로 표시되어 있으므로 규칙 [CA1416](/visualstudio/code-quality/ca1416)을 사용하면 호출 사이트에 OS 검사를 추가하여 런타임 <xref:System.PlatformNotSupportedException> 예외를 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-115">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

#### <a name="examples"></a><span data-ttu-id="0a3af-116">예제</span><span class="sxs-lookup"><span data-stu-id="0a3af-116">Examples</span></span>

- <span data-ttu-id="0a3af-117"><xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> 메서드는 Windows에서만 지원됩니다(`[SupportedOSPlatform("windows")]`으로 데코레이트됨).</span><span class="sxs-lookup"><span data-stu-id="0a3af-117">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows (it's decorated with `[SupportedOSPlatform("windows")]`).</span></span> <span data-ttu-id="0a3af-118">다음 코드는 프로젝트가 `net5.0-windows`가 아닌 `net5.0`을 [대상](../../../../docs/standard/frameworks.md)으로 하는 경우 빌드 시 CA1416 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-118">The following code will produce a CA1416 warning at build time if the project [targets](../../../../docs/standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="0a3af-119">경고를 방지하기 위해 수행할 수 있는 작업은 [권장 조치](#recommended-action)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a3af-119">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="0a3af-120"><xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> 메서드는 브라우저에서 지원되지 않습니다(`[UnsupportedOSPlatform("browser")]`으로 데코레이트됨).</span><span class="sxs-lookup"><span data-stu-id="0a3af-120">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser (it's decorated with `[UnsupportedOSPlatform("browser")]`).</span></span> <span data-ttu-id="0a3af-121">다음 코드는 프로젝트가 Blazor WebAssembly SDK(`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`)를 사용하거나 프로젝트 파일에서 지원되는 플랫폼(`<SupportedPlatform Include="browser" />`)으로 `browser`를 포함하는 경우 빌드 시 CA1416 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-121">The following code will produce a CA1416 warning at build time if the project uses the Blazor WebAssembly SDK (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) or includes `browser` as a supported platform (`<SupportedPlatform Include="browser" />`) in the project file.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a><span data-ttu-id="0a3af-122">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0a3af-122">Version introduced</span></span>

<span data-ttu-id="0a3af-123">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="0a3af-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0a3af-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0a3af-124">Recommended action</span></span>

<span data-ttu-id="0a3af-125">적절한 플랫폼에서 코드가 실행되는 경우에만 플랫폼별 API가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-125">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="0a3af-126">플랫폼별 API를 호출하기 전에 <xref:System.OperatingSystem?displayProperty=nameWithType> 클래스에서 `Is<Platform>` 메서드 중 하나(예: <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>)를 사용하여 현재 운영 체제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-126">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="0a3af-127">`if` 문의 조건에 `Is<Platform>` 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-127">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="0a3af-128">또는 런타임에 추가 `if` 문의 오버헤드를 원하지 않는다면 대신 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-128">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0a3af-129">API를 플랫폼에 특정한 것으로 표시할 수도 있으며, 이 경우 요구 사항을 검사할 부담은 호출자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-129">You can also mark your API as platform-specific, in which case the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="0a3af-130">특정 메서드나 유형 또는 전체 어셈블리를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-130">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="0a3af-131">모든 호출 사이트를 수정하지는 않으려면 다음 옵션 중 하나를 선택하여 경고를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-131">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="0a3af-132">규칙 CA1416을 중지하려면 `#pragma` 또는 [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) 컴파일러 플래그를 사용하거나 editorconfig 파일에서 [규칙의 심각도](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations)를 `none`으로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-132">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="0a3af-133">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3af-133">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="0a3af-134">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a3af-134">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="0a3af-135">범주</span><span class="sxs-lookup"><span data-stu-id="0a3af-135">Category</span></span>

- <span data-ttu-id="0a3af-136">코드 분석</span><span class="sxs-lookup"><span data-stu-id="0a3af-136">Code analysis</span></span>
- <span data-ttu-id="0a3af-137">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0a3af-137">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0a3af-138">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0a3af-138">Affected APIs</span></span>

<span data-ttu-id="0a3af-139">Windows 플랫폼:</span><span class="sxs-lookup"><span data-stu-id="0a3af-139">For Windows platform:</span></span>

- <span data-ttu-id="0a3af-140"><https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>에 나열된 모든 API</span><span class="sxs-lookup"><span data-stu-id="0a3af-140">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="0a3af-141">Blazor WebAssembly 플랫폼:</span><span class="sxs-lookup"><span data-stu-id="0a3af-141">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="0a3af-142"><https://github.com/dotnet/runtime/issues/41087>에 나열된 모든 API</span><span class="sxs-lookup"><span data-stu-id="0a3af-142">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a><span data-ttu-id="0a3af-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a3af-143">See also</span></span>

- [<span data-ttu-id="0a3af-144">CA1416: 플랫폼 호환성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0a3af-144">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="0a3af-145">.NET API 분석기</span><span class="sxs-lookup"><span data-stu-id="0a3af-145">.NET API analyzer</span></span>](../../../../docs/standard/analyzers/api-analyzer.md)
