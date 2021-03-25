---
title: '호환성이 손상되는 변경: CA1416: 플랫폼 호환성'
description: 코드 분석 규칙 CA1416 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/29/2020
ms.openlocfilehash: fa03e1f0bfa8438b3b2899aaf7c97f42533c7c02
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477553"
---
# <a name="warning-ca1416-platform-compatibility"></a><span data-ttu-id="e9919-103">경고 CA1416: 플랫폼 호환성</span><span class="sxs-lookup"><span data-stu-id="e9919-103">Warning CA1416: Platform compatibility</span></span>

<span data-ttu-id="e9919-104">.NET 코드 분석기 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-104">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="e9919-105">운영 체제를 확인하지 않는 호출 사이트에서 플랫폼별 API에 대한 호출의 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-105">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

## <a name="change-description"></a><span data-ttu-id="e9919-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e9919-106">Change description</span></span>

<span data-ttu-id="e9919-107">.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="e9919-108">[CA1416](/visualstudio/code-quality/ca1416)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-108">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="e9919-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="e9919-110">규칙 CA1416은 플랫폼 컨텍스트가 확인되지 않는 위치에서 플랫폼별 API를 사용하는 경우 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-110">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="e9919-111">규칙 [CA1416](/visualstudio/code-quality/ca1416), 플랫폼 호환성 분석기는 .NET 5.0에 새로 도입된 다른 일부 기능과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-111">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="e9919-112">.NET 5에는 API를 ‘지원’하거나 ‘지원하지 않는’ 플랫폼을 지정할 수 있는 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>가 도입되었습니다. </span><span class="sxs-lookup"><span data-stu-id="e9919-112">.NET 5 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="e9919-113">이러한 특성이 없으면 API는 모든 플랫폼에서 지원되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-113">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="e9919-114">해당 특성은 핵심 .NET 라이브러리의 플랫폼별 API에 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-114">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="e9919-115">해당 API를 사용할 수 없는 플랫폼을 대상으로 하는 프로젝트에서 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 플랫폼 컨텍스트가 확인되지 않는 플랫폼별 API 호출을 플래그로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-115">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="e9919-116">현재 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> 특성으로 데코레이트된 대부분의 API는 지원되지 않는 운영 체제에서 호출되는 경우 <xref:System.PlatformNotSupportedException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-116">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="e9919-117">이러한 API는 플랫폼별로 표시되어 있으므로 규칙 [CA1416](/visualstudio/code-quality/ca1416)을 사용하면 호출 사이트에 OS 검사를 추가하여 런타임 <xref:System.PlatformNotSupportedException> 예외를 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-117">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

## <a name="examples"></a><span data-ttu-id="e9919-118">예제</span><span class="sxs-lookup"><span data-stu-id="e9919-118">Examples</span></span>

- <span data-ttu-id="e9919-119"><xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> 메서드는 Windows에서만 지원되고 `[SupportedOSPlatform("windows")]`으로 데코레이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-119">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows and is decorated with `[SupportedOSPlatform("windows")]`.</span></span> <span data-ttu-id="e9919-120">다음 코드는 프로젝트가 `net5.0-windows`가 아닌 `net5.0`을 [대상](../../../../standard/frameworks.md)으로 하는 경우 빌드 시 CA1416 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-120">The following code will produce a CA1416 warning at build time if the project [targets](../../../../standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="e9919-121">경고를 방지하기 위해 수행할 수 있는 작업은 [권장 조치](#recommended-action)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9919-121">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="e9919-122"><xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> 메서드는 브라우저에서 지원되지 않으며 `[UnsupportedOSPlatform("browser")]`으로 데코레이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-122">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser and is decorated with `[UnsupportedOSPlatform("browser")]`.</span></span> <span data-ttu-id="e9919-123">다음 코드는 프로젝트가 브라우저 플랫폼을 지원하는 경우 빌드 시 CA1416 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-123">The following code will produce a CA1416 warning at build time if the project supports the browser platform.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - <span data-ttu-id="e9919-124">Blazor WebAssembly 프로젝트 및 Razor 클래스 라이브러리 프로젝트에는 브라우저 지원이 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-124">Blazor WebAssembly projects and Razor class library projects include browser support automatically.</span></span>
  > - <span data-ttu-id="e9919-125">프로젝트에 지원되는 플랫폼으로 수동으로 브라우저를 추가하려면 프로젝트 파일에 다음 항목을 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="e9919-125">To manually add the browser as a supported platform for your project, add the following entry to your project file:</span></span>
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

## <a name="version-introduced"></a><span data-ttu-id="e9919-126">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e9919-126">Version introduced</span></span>

<span data-ttu-id="e9919-127">5.0</span><span class="sxs-lookup"><span data-stu-id="e9919-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e9919-128">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e9919-128">Recommended action</span></span>

<span data-ttu-id="e9919-129">적절한 플랫폼에서 코드가 실행되는 경우에만 플랫폼별 API가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-129">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="e9919-130">플랫폼별 API를 호출하기 전에 <xref:System.OperatingSystem?displayProperty=nameWithType> 클래스에서 `Is<Platform>` 메서드 중 하나(예: <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>)를 사용하여 현재 운영 체제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-130">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="e9919-131">`if` 문의 조건에 `Is<Platform>` 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-131">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="e9919-132">또는 런타임에 추가 `if` 문의 오버헤드를 원하지 않는다면 대신 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-132">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="e9919-133">라이브러리를 제작하는 경우 API를 플랫폼별로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-133">If you're authoring a library, you can mark your API as platform-specific.</span></span> <span data-ttu-id="e9919-134">이 경우 요구 사항을 확인하는 것은 호출자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-134">In this case, the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="e9919-135">특정 메서드나 유형 또는 전체 어셈블리를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-135">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="e9919-136">모든 호출 사이트를 수정하지는 않으려면 다음 옵션 중 하나를 선택하여 경고를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-136">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="e9919-137">규칙 CA1416을 중지하려면 `#pragma` 또는 [**DisabledWarnings**](../../../../csharp/language-reference/compiler-options/errors-warnings.md#disabledwarnings) 컴파일러 플래그를 사용하거나 editorconfig 파일에서 [규칙의 심각도](../../../../fundamentals/code-analysis/configuration-options.md#severity-level)를 `none`으로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-137">To suppress rule CA1416, you can do so using `#pragma` or the [**DisabledWarnings**](../../../../csharp/language-reference/compiler-options/errors-warnings.md#disabledwarnings) compiler flag, or by [setting the rule's severity](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="e9919-138">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9919-138">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="e9919-139">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9919-139">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e9919-140">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e9919-140">Affected APIs</span></span>

<span data-ttu-id="e9919-141">Windows 플랫폼:</span><span class="sxs-lookup"><span data-stu-id="e9919-141">For Windows platform:</span></span>

- <span data-ttu-id="e9919-142"><https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>에 나열된 모든 API</span><span class="sxs-lookup"><span data-stu-id="e9919-142">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="e9919-143">Blazor WebAssembly 플랫폼:</span><span class="sxs-lookup"><span data-stu-id="e9919-143">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="e9919-144"><https://github.com/dotnet/runtime/issues/41087>에 나열된 모든 API</span><span class="sxs-lookup"><span data-stu-id="e9919-144">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

### Affected APIs

- ``

### Category

- Code analysis
- Core .NET libraries

-->

## <a name="see-also"></a><span data-ttu-id="e9919-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9919-145">See also</span></span>

- [<span data-ttu-id="e9919-146">CA1416: 플랫폼 호환성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e9919-146">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="e9919-147">.NET API 분석기</span><span class="sxs-lookup"><span data-stu-id="e9919-147">.NET API analyzer</span></span>](../../../../standard/analyzers/api-analyzer.md)
