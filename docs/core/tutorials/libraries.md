---
title: .NET CLI를 사용하여 라이브러리 개발
description: .NET CLI를 사용하여 .NET 라이브러리를 만드는 방법을 알아봅니다. 여러 프레임워크를 지원하는 라이브러리를 만듭니다.
author: cartermp
ms.topic: how-to
ms.date: 12/14/2020
ms.openlocfilehash: 6f4c1feac7630a6a0250e4b0b39ef01152f5a400
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633678"
---
# <a name="develop-libraries-with-the-net-cli"></a><span data-ttu-id="47821-104">.NET CLI를 사용하여 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="47821-104">Develop libraries with the .NET CLI</span></span>

<span data-ttu-id="47821-105">이 문서에서는 .NET CLI를 사용하여 .NET용 라이브러리를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-105">This article covers how to write libraries for .NET using the .NET CLI.</span></span> <span data-ttu-id="47821-106">CLI는 지원되는 운영 체제에서 작동하는 효율적인 하위 수준 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="47821-107">Visual Studio로 라이브러리를 빌드할 수 있습니다. 그러한 환경을 선호하는 경우 [Visual Studio 설명서를 참조하세요](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="47821-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](library-with-visual-studio.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47821-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="47821-108">Prerequisites</span></span>

<span data-ttu-id="47821-109">머신에 [.NET SDK 및 CLI](https://dotnet.microsoft.com/download)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-109">You need [the .NET SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="47821-110">.NET Framework 버전을 다루는 이 문서의 섹션에서는 [.NET Framework](https://dotnet.microsoft.com)가 설치된 Windows 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="47821-111">또한 이전 .NET Framework 대상을 지원하려는 경우 [.NET 다운로드 보관 페이지](https://dotnet.microsoft.com/download/archives)에서 타기팅 팩 또는 개발자 팩을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting packs or developer packs from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="47821-112">다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-112">Refer to this table:</span></span>

| <span data-ttu-id="47821-113">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="47821-113">.NET Framework version</span></span> | <span data-ttu-id="47821-114">다운로드할 파일</span><span class="sxs-lookup"><span data-stu-id="47821-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="47821-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="47821-115">4.6.1</span></span>                  | <span data-ttu-id="47821-116">.NET Framework 4.6.1 타기팅 팩</span><span class="sxs-lookup"><span data-stu-id="47821-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="47821-117">4.6</span><span class="sxs-lookup"><span data-stu-id="47821-117">4.6</span></span>                    | <span data-ttu-id="47821-118">.NET framework 4.6 타기팅 팩</span><span class="sxs-lookup"><span data-stu-id="47821-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="47821-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="47821-119">4.5.2</span></span>                  | <span data-ttu-id="47821-120">.NET framework 4.5.2 개발자 팩</span><span class="sxs-lookup"><span data-stu-id="47821-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="47821-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="47821-121">4.5.1</span></span>                  | <span data-ttu-id="47821-122">.NET framework 4.5.1 개발자 팩</span><span class="sxs-lookup"><span data-stu-id="47821-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="47821-123">4.5</span><span class="sxs-lookup"><span data-stu-id="47821-123">4.5</span></span>                    | <span data-ttu-id="47821-124">Windows 8용 Windows 소프트웨어 개발 키트</span><span class="sxs-lookup"><span data-stu-id="47821-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="47821-125">4.0</span><span class="sxs-lookup"><span data-stu-id="47821-125">4.0</span></span>                    | <span data-ttu-id="47821-126">Windows 7 및 .NET Framework 4용 Windows SDK</span><span class="sxs-lookup"><span data-stu-id="47821-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="47821-127">2.0, 3.0 및 3.5</span><span class="sxs-lookup"><span data-stu-id="47821-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="47821-128">.NET Framework 3.5 SP1 런타임(또는 Windows 8 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="47821-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-net-50-or-net-standard"></a><span data-ttu-id="47821-129">.NET 5.0 또는 .NET Standard를 대상으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="47821-129">How to target .NET 5.0 or .NET Standard</span></span>

<span data-ttu-id="47821-130">프로젝트의 대상 프레임워크를 제어하려면 프로젝트 파일에 해당 값( *.csproj* 또는 *fsproj*)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-130">You control your project's target framework by adding it to your project file (*.csproj* or *.fsproj*).</span></span> <span data-ttu-id="47821-131">.NET 5.0 또는 .NET Standard 중 대상을 선택하는 방법에 대한 지침은 [.NET 5 및 .NET Standard](../../standard/net-standard.md#net-5-and-net-standard)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-131">For guidance on how to choose between targeting .NET 5.0 or .NET Standard see [.NET 5 and .NET Standard](../../standard/net-standard.md#net-5-and-net-standard).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="47821-132">.NET Framework 버전 4.0 이하를 대상으로 하거나 .NET Framework에서는 사용 가능하지만 .NET Standard에서는 사용할 수 없는 API를 사용하려는 경우(예: `System.Drawing`) 다음 섹션을 읽어보고 멀티 타기팅 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="47821-132">If you want to target .NET Framework versions 4.0 or below, or you wish to use an API available in .NET Framework but not in .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-net-framework"></a><span data-ttu-id="47821-133">.NET Framework를 대상으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="47821-133">How to target .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="47821-134">다음 지침은 컴퓨터에 .NET Framework가 설치된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-134">These instructions assume you have .NET Framework installed on your machine.</span></span> <span data-ttu-id="47821-135">설치된 종속성을 알아보려면 [필수 조건](#prerequisites)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-135">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="47821-136">여기서 사용된 .NET Framework 버전 중 일부는 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-136">Keep in mind that some of the .NET Framework versions used here are no longer supported.</span></span> <span data-ttu-id="47821-137">지원되지 않는 버전은 [.NET Framework Support Lifecycle Policy FAQ(.NET Framework 지원 수명 주기 정책 FAQ)](https://support.microsoft.com/gp/framework_faq/en-us)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-137">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="47821-138">가장 많은 수의 개발자 및 프로젝트에 도달하려면 기준 대상으로 .NET Framework 4.0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-138">If you want to reach the maximum number of developers and projects, use .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="47821-139">.NET Framework를 대상으로 하려면 지원할 .NET Framework 버전에 해당하는 올바른 TFM(대상 프레임워크 모니커)을 사용하여 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-139">To target .NET Framework, begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="47821-140">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="47821-140">.NET Framework version</span></span> | <span data-ttu-id="47821-141">TFM</span><span class="sxs-lookup"><span data-stu-id="47821-141">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="47821-142">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="47821-142">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="47821-143">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="47821-143">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="47821-144">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="47821-144">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="47821-145">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="47821-145">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="47821-146">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="47821-146">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="47821-147">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="47821-147">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="47821-148">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="47821-148">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="47821-149">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="47821-149">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="47821-150">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="47821-150">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="47821-151">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="47821-151">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="47821-152">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="47821-152">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="47821-153">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="47821-153">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="47821-154">그런 다음 이 TFM을 프로젝트 파일의 `TargetFramework` 섹션에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-154">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="47821-155">예를 들어 .NET Framework 4.0을 대상으로 하는 라이브러리의 작성 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-155">For example, here's how you would write a library that targets .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="47821-156">정말 간단하죠!</span><span class="sxs-lookup"><span data-stu-id="47821-156">And that's it!</span></span> <span data-ttu-id="47821-157">이는 .NET Framework 4에 대해서만 컴파일되지만 이후 버전의 .NET Framework에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-157">Although this compiled only for .NET Framework 4, you can use the library on newer versions of .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="47821-158">멀티 타기팅 방법</span><span class="sxs-lookup"><span data-stu-id="47821-158">How to multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="47821-159">다음 지침에서는 컴퓨터에 .NET Framework가 설치된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-159">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="47821-160">설치해야 할 종속성 및 다운로드할 위치에 대해 알아보려면 [필수 조건](#prerequisites) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-160">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="47821-161">프로젝트가 .NET Framework 및 .NET을 모두 지원하는 경우 이전 버전의 .NET Framework를 대상으로 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-161">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET.</span></span> <span data-ttu-id="47821-162">이 시나리오에서, 최신 대상에 최신 API 및 언어 구조를 사용하려는 경우 코드에 `#if` 지시문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-162">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="47821-163">각각의 경우에 필요한 API를 포함하기 위해 대상으로 지정하는 각 플랫폼마다 서로 다른 패키지와 종속성을 추가해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-163">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="47821-164">예를 들어 HTTP를 통해 네트워킹 작업을 수행하는 라이브러리가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-164">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="47821-165">.NET 표준 및 .NET Framework 버전 4.5 이상 경우 `System.Net.Http` 네임스페이스의 `HttpClient` 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-165">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="47821-166">그러나 이전 버전의 .NET Framework에는 `HttpClient` 클래스가 없으므로, 이에 대해 `System.Net` 네임스페이스의 `WebClient` 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-166">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="47821-167">프로젝트 파일이 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-167">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard2.0;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="47821-168">여기서 다음 세 가지 주요 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-168">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="47821-169">`TargetFramework` 노드가 `TargetFrameworks`로 대체되었으며, 세 개의 TFM이 내부에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-169">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="47821-170">`net40` 대상에는 .NET Framework 참조 하나를 끌어오는 `<ItemGroup>` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-170">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="47821-171">`net45` 대상에는 .NET Framework 참조 두 개를 끌어오는 `<ItemGroup>` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-171">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="47821-172">빌드 시스템은 `#if` 지시문에 사용된 다음의 전처리기 기호를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-172">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="47821-173">대상당 조건부 컴파일을 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-173">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET Framework 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="47821-174">`dotnet build`를 사용하여 이 프로젝트를 빌드하면 `bin/` 폴더 아래에 다음 3개의 디렉터리가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-174">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard2.0/
```

<span data-ttu-id="47821-175">각 디렉터리에는 각 대상의 `.dll` 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-175">Each of these contains the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net"></a><span data-ttu-id="47821-176">.NET에서 라이브러리를 테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="47821-176">How to test libraries on .NET</span></span>

<span data-ttu-id="47821-177">플랫폼 간에 테스트할 수 있는 기능이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-177">It's important to be able to test across platforms.</span></span> <span data-ttu-id="47821-178">기본적으로 [xUnit](https://xunit.net/) 또는 MSTest를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-178">You can use either [xUnit](https://xunit.net/) or MSTest out of the box.</span></span> <span data-ttu-id="47821-179">둘 다 .NET에서 라이브러리를 유닛 테스트하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-179">Both are perfectly suitable for unit testing your library on .NET.</span></span> <span data-ttu-id="47821-180">테스트 프로젝트로 솔루션을 설정하는 방법은 [솔루션 구조](#structuring-a-solution)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="47821-180">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="47821-181">다음 예제에서는 테스트 및 원본 디렉터리가 동일한 최상위 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-181">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="47821-182">일부 [.NET CLI](../tools/index.md) 명령이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-182">This uses some [.NET CLI](../tools/index.md) commands.</span></span> <span data-ttu-id="47821-183">자세한 내용은 [dotnet new](../tools/dotnet-new.md) 및 [dotnet sln](../tools/dotnet-sln.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47821-183">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="47821-184">솔루션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-184">Set up your solution.</span></span> <span data-ttu-id="47821-185">다음 명령을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-185">You can do so with the following commands:</span></span>

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="47821-186">그러면 프로젝트가 생성되고 솔루션에서 함께 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-186">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="47821-187">`SolutionWithSrcAndTest` 디렉터리가 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-187">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="47821-188">테스트 프로젝트의 디렉터리로 이동한 다음 `MyProject`의 `MyProject.Test`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-188">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="47821-189">패키지를 복원하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-189">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

1. <span data-ttu-id="47821-190">`dotnet test` 명령을 실행하여 xUnit가 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-190">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="47821-191">MSTest를 사용하도록 선택한 경우 MSTest 콘솔 실행기가 대신 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-191">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="47821-192">정말 간단하죠!</span><span class="sxs-lookup"><span data-stu-id="47821-192">And that's it!</span></span> <span data-ttu-id="47821-193">이제 명령줄 도구를 사용하여 모든 플랫폼 라이브러리를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-193">You can now test your library across all platforms using command-line tools.</span></span> <span data-ttu-id="47821-194">이제 모든 것이 설정되어 계속해서 테스트하려는 경우 라이브러리 테스트는 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-194">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="47821-195">라이브러리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-195">Make changes to your library.</span></span>
1. <span data-ttu-id="47821-196">명령줄의 테스트 디렉터리에서 `dotnet test` 명령으로 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-196">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="47821-197">`dotnet test` 명령을 호출하면 자동으로 코드가 다시 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-197">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="47821-198">여러 프로젝트를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="47821-198">How to use multiple projects</span></span>

<span data-ttu-id="47821-199">더 큰 라이브러리의 경우 일반적으로 서로 다른 프로젝트에 기능을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-199">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="47821-200">자연스러운 C# 및 F#에 사용할 수 있는 라이브러리를 빌드하려 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-200">Imagine you want to build a library that could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="47821-201">다시 말해 라이브러리의 소비자가 C# 및 F#에 자연스러운 방식으로 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-201">That would mean that consumers of your library consume it in ways that are natural to C# or F#.</span></span> <span data-ttu-id="47821-202">예를 들어 C#에서 다음과 같이 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-202">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="47821-203">F#에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-203">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="47821-204">이와 같은 사용 시나리오는, 액세스하는 API가 C# 및 F#에 대해 다른 구조를 가지고 있어야 한다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="47821-204">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="47821-205">이를 수행하는 일반적인 방법은 Core 프로젝트로 호출하는 API 계층을 정의하는 C# 및 F# 프로젝트에서 라이브러리의 모든 논리를 해당 Core 프로젝트로 팩터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47821-205">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="47821-206">섹션의 나머지 부분에서는 다음 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-206">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="47821-207">**AwesomeLibrary.Core** - 라이브러리에 대한 모든 논리를 포함하는 Core 프로젝트</span><span class="sxs-lookup"><span data-stu-id="47821-207">**AwesomeLibrary.Core** - A core project that contains all logic for the library</span></span>
* <span data-ttu-id="47821-208">**AwesomeLibrary.CSharp** - C#에서 사용하기 위한 공용 API가 포함된 프로젝트</span><span class="sxs-lookup"><span data-stu-id="47821-208">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="47821-209">**AwesomeLibrary.FSharp** - F#에서 사용하기 위한 공용 API가 포함된 프로젝트</span><span class="sxs-lookup"><span data-stu-id="47821-209">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="47821-210">터미널에서 다음 명령을 실행하면 이 가이드와 동일한 구조를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-210">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="47821-211">그러면 위의 세 가지 프로젝트와 프로젝트를 함께 연결하는 솔루션 파일 하나가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="47821-211">This will add the three projects above and a solution file that links them together.</span></span> <span data-ttu-id="47821-212">솔루션 파일을 만들고 프로젝트를 연결하면 최상위 수준에서 프로젝트를 복원하고 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-212">Creating the solution file and linking projects will allow you to restore and build projects from a top level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="47821-213">프로젝트 간 참조</span><span class="sxs-lookup"><span data-stu-id="47821-213">Project-to-project referencing</span></span>

<span data-ttu-id="47821-214">프로젝트를 참조하는 가장 좋은 방법은 .NET CLI를 사용하여 프로젝트 참조를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47821-214">The best way to reference a project is to use the .NET CLI to add a project reference.</span></span> <span data-ttu-id="47821-215">**AwesomeLibrary.CSharp** 및 **AwesomeLibrary.FSharp** 프로젝트 디렉터리에서 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-215">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="47821-216">이제 **AwesomeLibrary.CSharp** 및 **AwesomeLibrary.FSharp** 둘 다의 프로젝트 파일에서 **AwesomeLibrary.Core** 를 `ProjectReference` 대상으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="47821-216">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="47821-217">프로젝트 파일을 검사하고 파일에서 다음을 통해 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-217">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="47821-218">.NET CLI를 사용하지 않으려는 경우 이 섹션을 각 프로젝트 파일에 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-218">You can add this section to each project file manually if you prefer not to use the .NET CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="47821-219">솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="47821-219">Structuring a solution</span></span>

<span data-ttu-id="47821-220">다중 프로젝트 솔루션의 또 다른 중요한 측면은 전체 프로젝트 구조를 올바르게 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47821-220">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="47821-221">코드를 원하는 대로 구성할 수 있으며, `dotnet sln add`를 사용하여 각 프로젝트를 솔루션 파일에 연결하기만 하면 솔루션 수준에서 `dotnet restore` 및 `dotnet build`를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47821-221">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
