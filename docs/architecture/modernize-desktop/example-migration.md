---
title: .NET 5로의 마이그레이션 예제
description: .NET Framework를 대상으로 하는 샘플 애플리케이션을 .NET 5로 마이그레이션하는 방법을 보여 줍니다.
ms.date: 01/19/2021
ms.openlocfilehash: 02a45859dfca891598e235e3de1ed968aefb5bf4
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605167"
---
# <a name="example-of-migrating-to-net"></a><span data-ttu-id="4153b-103">.NET으로의 마이그레이션 예제</span><span class="sxs-lookup"><span data-stu-id="4153b-103">Example of migrating to .NET</span></span>

<span data-ttu-id="4153b-104">이 장에서는 기존 애플리케이션을 .NET Framework에서 .NET으로 마이그레이션하는 데 도움이 되는 실용적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET.</span></span>

<span data-ttu-id="4153b-105">또한 수행할 수 있는 잘 구성된 프로세스 및 각 단계에서 고려해야 할 가장 중요한 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="4153b-106">다음으로 WinForms 및 WPF 버전의 샘플 데스크톱 애플리케이션에 대한 단계별 마이그레이션 프로세스를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="4153b-107">마이그레이션 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="4153b-107">Migration process overview</span></span>

<span data-ttu-id="4153b-108">마이그레이션 프로세스는 다음과 같은 순차적인 4단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="4153b-109">**준비**: 프로젝트에서 미래를 파악하기 위해 필요한 종속성을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="4153b-110">이 단계에서는 마이그레이션의 시작 지점을 간소화하는 상태로 현재 프로젝트를 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="4153b-111">**프로젝트 파일 마이그레이션:** .NET 프로젝트는 새로운 SDK 스타일 프로젝트 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-111">**Migrate Project File:** .NET projects use the new SDK-style project format.</span></span> <span data-ttu-id="4153b-112">이 형식을 사용하여 새 프로젝트 파일을 만들거나 SDK 스타일을 사용해야 하는 프로젝트 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="4153b-113">**코드 수정 및 빌드:** .NET Framework와 .NET 간의 API 수준 차이를 해결하는 코드를 .NET에서 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-113">**Fix code and build:** Build the code in .NET addressing API-level differences between .NET Framework and .NET.</span></span> <span data-ttu-id="4153b-114">필요한 경우 .NET을 지원하는 패키지로 타사 패키지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-114">If needed, update third-party packages to the ones that support .NET.</span></span>

4. <span data-ttu-id="4153b-115">**실행 및 테스트:** 런타임까지 표시되지 않는 차이점이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="4153b-116">따라서 애플리케이션을 실행하고 모든 항목이 예상대로 작동하는지 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="4153b-117">준비</span><span class="sxs-lookup"><span data-stu-id="4153b-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="4153b-118">packages.config 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4153b-118">Migrate packages.config file</span></span>

<span data-ttu-id="4153b-119">.NET Framework 애플리케이션에서는 외부 패키지에 대한 모든 참조가 *packages.config* 파일에 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="4153b-120">.NET에서는 *packages.config* 파일을 더 이상 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-120">In .NET, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="4153b-121">대신 프로젝트 파일 내에서 [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) 속성을 사용하여 앱에 대한 NuGet 패키지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="4153b-122">따라서 한 형식에서 다른 형식으로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="4153b-123">*packages.config* 파일에 포함된 종속성을 가져와 `PackageReference` 형식으로 프로젝트 파일로 마이그레이션하여 수동으로 업데이트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="4153b-124">또는 *packages.config* 파일을 마우스 오른쪽 단추로 클릭하고 **packages.config를 PackageReference로 마이그레이션** 옵션을 선택하여 Visual Studio에서 작업을 수행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net"></a><span data-ttu-id="4153b-125">.NET의 모든 종속성 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="4153b-125">Verify every dependency compatibility in .NET</span></span>

<span data-ttu-id="4153b-126">패키지 참조를 마이그레이션한 다음에는 각 참조에서 호환성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="4153b-127">애플리케이션에서 사용하고 있는 각 NuGet 패키지의 종속성은 [nuget.org](https://www.nuget.org/)에서 확인할 수 있습니다. .NET은 모든 버전의 .NET Standard를 [지원](../../standard/net-standard.md#net-implementation-support)하므로 패키지에 .NET Standard 종속성이 있으면 .NET 5.0에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET 5.0 because .NET [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="4153b-128">다음 이미지는 `Castle.Windsor` 패키지에 대한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Castle.Windsor 패키지에 대한 NuGet 종속성 스크린샷](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="4153b-130">패키지 호환성을 확인하려면 버전 및 종속성에 대한 자세한 정보를 제공하는 <https://fuget.org> 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="4153b-131">프로젝트가 .NET을 지원하지 않는 이전 패키지 버전을 참조하고 있지만 지원하는 최신 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-131">Maybe the project is referencing older package versions that don't support .NET, but you might find newer versions that do support it.</span></span> <span data-ttu-id="4153b-132">따라서 패키지를 최신 버전으로 업데이트하는 것이 일반적으로 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="4153b-133">그러나 패키지 버전을 업데이트하면 몇 가지 호환성이 손상되는 변경이 발생하여 코드를 강제로 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="4153b-134">호환되는 버전을 찾지 못하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="4153b-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="4153b-135">이러한 호환성이 손상되는 변경 때문에 패키지 버전을 업데이트하지 않으려는 경우는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="4153b-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="4153b-136">.NET 애플리케이션의 .NET Framework 패키지에 종속될 수 있기 때문에 걱정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET application.</span></span> <span data-ttu-id="4153b-137">다만 외부 패키지가 .NET에서 사용할 수 없는 API를 호출하는 경우 런타임 오류가 발생할 수 있으므로 광범위하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET.</span></span> <span data-ttu-id="4153b-138">이 방법은 업데이트하지 않으려는 이전 패키지를 사용하고 있고 .NET에서 작동하도록 변경하려는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="4153b-139">API 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="4153b-139">Check for API compatibility</span></span>

<span data-ttu-id="4153b-140">.NET Framework와 .NET의 API 화면은 유사하지만 동일하지는 않으므로 .NET에서 사용할 수 있는 API와 사용할 수 없는 API를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-140">Since the API surface in .NET Framework and .NET is similar but not identical, you must check which APIs are available on .NET and which aren't.</span></span> <span data-ttu-id="4153b-141">.NET 이식성 분석기 도구를 사용하면 .NET에 없는 API를 사용하도록 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET.</span></span> <span data-ttu-id="4153b-142">앱의 이진 수준을 확인하고 호출되는 모든 API를 추출한 다음, 대상 프레임워크(이 경우 .NET 5.0)에서 사용할 수 없는 API를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET 5.0 in this case).</span></span>

<span data-ttu-id="4153b-143">이 도구에 대한 자세한 내용은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="4153b-144">이 도구의 흥미로운 측면은 변경할 수 없는 외부 패키지의 코드가 아니라 사용자 코드의 차이점만 표시한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="4153b-145">이러한 패키지가 .NET에서 작동하도록 하려면 대부분의 패키지를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-145">Remember you should have updated most of these packages to make them work with .NET.</span></span>

### <a name="migrate-with-try-convert-tool"></a><span data-ttu-id="4153b-146">Try Convert 도구를 사용하여 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4153b-146">Migrate with Try Convert tool</span></span>

<span data-ttu-id="4153b-147">[Try Convert](https://github.com/dotnet/try-convert/releases) 도구는 프로젝트를 마이그레이션하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-147">The [Try Convert](https://github.com/dotnet/try-convert/releases) tool is a great way to migrate a project.</span></span> <span data-ttu-id="4153b-148">프로젝트 파일을 이전 스타일에서 새 SDK 스타일로 업그레이드하려고 시도하고 적용 가능한 프로젝트를 .NET 5로 변경하는 글로벌 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-148">It's a global tool that attempts to upgrade your project file from the old style to the new SDK style, and retargets applicable projects to .NET 5.</span></span> <span data-ttu-id="4153b-149">설치되면 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-149">Once installed, you can run the following commands:</span></span>

```dotnetcli
try-convert -p "<path to your project file>"
```

<span data-ttu-id="4153b-150">또는</span><span class="sxs-lookup"><span data-stu-id="4153b-150">Or:</span></span>

```dotnetcli
try-convert -w "<path to your solution>"
```

> [!NOTE]
> <span data-ttu-id="4153b-151">try-convert 도구는 [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)의 일부로 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-151">The try-convert tool is run automatically as part of the [.NET Upgrade Assistant tool](https://aka.ms/dotnet-upgrade-assistant).</span></span> <span data-ttu-id="4153b-152">Try Convert만이 아니라 전체 업그레이드 도우미를 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-152">Consider running the full Upgrade Assistant and not just Try Convert.</span></span>

<span data-ttu-id="4153b-153">도구에서 변환을 시도한 후 Visual Studio에서 파일을 다시 로드하여 실행하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-153">After the tool attempts the conversion, reload your files in Visual Studio to run and test.</span></span> <span data-ttu-id="4153b-154">프로젝트의 세부 사항으로 인해 Try Convert에서 변환하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-154">There's a possibility that Try Convert won't be able to perform the conversion due to the specifics of your project.</span></span> <span data-ttu-id="4153b-155">이런 경우 다음 단계를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-155">In that case, you can refer the below steps.</span></span>

#### <a name="migrate-manually"></a><span data-ttu-id="4153b-156">수동으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4153b-156">Migrate manually</span></span>

1. <span data-ttu-id="4153b-157">새 .NET 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4153b-157">Create the new .NET project</span></span>

<span data-ttu-id="4153b-158">대부분의 경우 기존 프로젝트를 새 .NET 형식으로 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-158">In most cases, you'll want to update your existing project to the new .NET format.</span></span> <span data-ttu-id="4153b-159">그러나 이전 프로젝트를 유지하면서 새 프로젝트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-159">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="4153b-160">이전 프로젝트를 업데이트하는 경우의 주요 단점은 사용자와 개발 팀에 중요할 수 있는 디자이너를 사용할 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-160">The main drawback from updating the old project is that you lose designer support, which may be important to you and your development team.</span></span> <span data-ttu-id="4153b-161">디자이너를 계속 사용하려면 이전 프로젝트를 사용하여 병렬로 새 .NET 프로젝트를 만들고 자산을 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-161">If you want to keep using the designer, you must create a new .NET project in parallel with the old one and share assets.</span></span> <span data-ttu-id="4153b-162">디자이너에서 UI 요소를 수정하려면 이전 프로젝트로 전환하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-162">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="4153b-163">자산은 연결되어 있으므로 .NET 프로젝트에서도 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-163">And since assets are linked, they'll be updated in the .NET project as well.</span></span>

<span data-ttu-id="4153b-164">.NET용 [SDK 스타일 프로젝트](../../core/project-sdk/msbuild-props.md)는 .NET Framework의 프로젝트 형식보다 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-164">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="4153b-165">앞에서 설명한 `PackageReference` 항목과 별개로 훨씬 더 많은 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-165">Apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="4153b-166">새 프로젝트 형식에는 `.cs` 및 `.xaml` 파일과 같이 [기본적으로 특정 확장명을 사용하는 파일이 포함](../../core/project-sdk/overview.md#default-includes-and-excludes)되어 프로젝트 파일에 명시적으로 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-166">The new project format [includes files with certain extensions by default](../../core/project-sdk/overview.md#default-includes-and-excludes), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="4153b-167">AssemblyInfo 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4153b-167">AssemblyInfo considerations</span></span>

<span data-ttu-id="4153b-168">특성은 .NET 프로젝트에서 자동 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-168">Attributes are autogenerated on .NET projects.</span></span> <span data-ttu-id="4153b-169">프로젝트에 *AssemblyInfo.cs* 파일이 포함되어 있으면 정의가 중복되어 컴파일 충돌이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-169">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="4153b-170">.NET 프로젝트 파일에 다음 항목을 추가하여 이전 *AssemblyInfo.cs* 파일을 삭제하거나 자동 생성을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-170">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="4153b-171">리소스</span><span class="sxs-lookup"><span data-stu-id="4153b-171">Resources</span></span>

<span data-ttu-id="4153b-172">포함 리소스는 자동으로 포함되지만 리소스는 포함되지 않으므로 새 프로젝트 파일로 리소스를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-172">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="4153b-173">패키지 참조</span><span class="sxs-lookup"><span data-stu-id="4153b-173">Package references</span></span>

<span data-ttu-id="4153b-174">**packages.config를 PackageReference로 마이그레이션** 옵션을 사용하면 앞에서 설명한 대로 외부 패키지 참조를 새 형식으로 쉽게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-174">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="4153b-175">패키지 참조 업데이트</span><span class="sxs-lookup"><span data-stu-id="4153b-175">Update package references</span></span>

<span data-ttu-id="4153b-176">이전 섹션에 표시된 대로 호환되는 것으로 확인된 패키지의 버전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-176">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="4153b-177">코드 수정 및 빌드</span><span class="sxs-lookup"><span data-stu-id="4153b-177">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="4153b-178">Microsoft.Windows.Compatibility</span><span class="sxs-lookup"><span data-stu-id="4153b-178">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="4153b-179">애플리케이션이 레지스트리, ACL, WCF 등 .NET에서 사용할 수 없는 API에 종속되는 경우 이러한 Windows 관련 API를 추가하려면 `Microsoft.Windows.Compatibility` 패키지에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-179">If your application depends on APIs that aren't available on .NET, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="4153b-180">이러한 API는 플랫폼 간 API가 아니므로 .NET에서 작동은 하지만 포함되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-180">They work on .NET but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="4153b-181">코드와 호환되지 않는 API를 식별하는 데 도움이 되는 API 분석기(<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>)라는 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-181">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="4153b-182">\#if 지시문 사용</span><span class="sxs-lookup"><span data-stu-id="4153b-182">Use \#if directives</span></span>

<span data-ttu-id="4153b-183">.NET Framework 및 .NET을 대상으로 하는 경우 다른 실행 경로가 필요하면 컴파일 상수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-183">If you need different execution paths when targeting .NET Framework and .NET, you should use compilation constants.</span></span> <span data-ttu-id="4153b-184">일부 \#if 지시문을 코드에 추가하여 두 대상에 대해 동일한 코드베이스를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-184">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net"></a><span data-ttu-id="4153b-185">.NET에서 사용할 수 없는 기술</span><span class="sxs-lookup"><span data-stu-id="4153b-185">Technologies not available on .NET</span></span>

<span data-ttu-id="4153b-186">다음과 같은 일부 기술은 .NET에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-186">Some technologies aren't available on .NET, such as:</span></span>

* <span data-ttu-id="4153b-187">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4153b-187">AppDomains</span></span>
* <span data-ttu-id="4153b-188">원격 통신</span><span class="sxs-lookup"><span data-stu-id="4153b-188">Remoting</span></span>
* <span data-ttu-id="4153b-189">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="4153b-189">Code Access Security</span></span>
* <span data-ttu-id="4153b-190">WCF 서버</span><span class="sxs-lookup"><span data-stu-id="4153b-190">WCF Server</span></span>
* <span data-ttu-id="4153b-191">Windows Workflow</span><span class="sxs-lookup"><span data-stu-id="4153b-191">Windows Workflow</span></span>

<span data-ttu-id="4153b-192">따라서 애플리케이션에서 이러한 기술을 사용하고 있는 경우 대체할 기술을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-192">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="4153b-193">자세한 내용은 [.NET Core 및 .NET 5+에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4153b-193">For more information, see the [.NET Framework technologies unavailable on .NET Core and .NET 5+](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="4153b-194">자동 생성된 클라이언트 다시 생성</span><span class="sxs-lookup"><span data-stu-id="4153b-194">Regenerate autogenerated clients</span></span>

<span data-ttu-id="4153b-195">애플리케이션에서 WCF 클라이언트와 같은 자동 생성된 코드를 사용하는 경우 .NET을 대상으로 하도록 이 코드를 다시 생성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-195">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET.</span></span> <span data-ttu-id="4153b-196">경우에 따라 기본 .NET 어셈블리 집합의 일부로 포함되지 않아 일부 참조가 누락된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-196">Sometimes, you can find some missing references since they may not be included as part of the default .NET assemblies set.</span></span> <span data-ttu-id="4153b-197"><https://apisof.net/> 같은 도구를 사용하여 누락된 참조가 있는 어셈블리를 쉽게 찾아 NuGet에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-197">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="4153b-198">패키지 버전 롤백</span><span class="sxs-lookup"><span data-stu-id="4153b-198">Rolling back package versions</span></span>

<span data-ttu-id="4153b-199">일반적으로 모든 단일 패키지 버전을 .NET과 호환되도록 업데이트하는 것이 좋다고 앞에서 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-199">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET.</span></span> <span data-ttu-id="4153b-200">그러나 어셈블리의 업데이트된 버전과 호환되는 버전을 대상으로 하면 효과가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-200">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="4153b-201">변경 비용이 허용되지 않는 경우 패키지 버전을 롤백하여 .NET Framework에서 사용하는 버전을 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-201">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="4153b-202">.NET을 대상으로 하지 않을 수 있지만 지원되지 않는 일부 API를 호출하지 않는 한 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-202">Although they may not be targeting .NET, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="4153b-203">실행 및 테스트</span><span class="sxs-lookup"><span data-stu-id="4153b-203">Run and test</span></span>

<span data-ttu-id="4153b-204">애플리케이션을 오류 없이 빌드했으면 모든 기능을 테스트하여 마이그레이션의 마지막 단계를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-204">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="4153b-205">이 최종 단계에서는 애플리케이션의 복잡성 및 사용 중인 종속성과 API에 따라 여러 가지 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-205">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="4153b-206">예를 들어 구성 파일(*app.config*)을 사용하는 경우 구성 섹션이 없음과 같은 일부 오류가 런타임에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-206">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="4153b-207">`Microsoft.Extensions.Configuration` NuGet 패키지를 사용하여 해당 오류를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-207">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="4153b-208">오류가 발생하는 또 다른 이유는 .NET에서 지원되지 않는 `BeginInvoke` 및 `EndInvoke` 메서드의 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-208">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET.</span></span> <span data-ttu-id="4153b-209">이러한 메서드는 .NET에 없는 원격에 종속성이 있기 때문에 .NET에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-209">They aren't supported on .NET because they have a dependency on Remoting, which doesn't exist on .NET.</span></span> <span data-ttu-id="4153b-210">이 문제를 해결하려면 `await` 키워드(사용 가능한 경우) 또는 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4153b-210">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4153b-211">호환성 분석기를 사용하면 .NET에서 런타임에 문제를 발생시킬 수 있는 API 및 코드 패턴을 코드에서 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-211">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET.</span></span> <span data-ttu-id="4153b-212"><https://github.com/dotnet/platform-compat>으로 이동하여 프로젝트에서 .NET API 분석기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-212">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="4153b-213">Windows Forms 애플리케이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4153b-213">Migrating a Windows Forms application</span></span>

<span data-ttu-id="4153b-214">Windows Forms 애플리케이션의 전체 마이그레이션 프로세스를 보여 주기 위해 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>에서 제공되는 eShop 샘플 애플리케이션을 마이그레이션하도록 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-214">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="4153b-215">마이그레이션의 전체 결과는 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-215">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="4153b-216">이 애플리케이션은 제품 카탈로그를 보여 주고 사용자가 제품을 탐색, 필터링, 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-216">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="4153b-217">아키텍처 관점에서 앱은 백 엔드 데이터베이스의 외관 역할을 하는 외부 WCF 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-217">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="4153b-218">주 애플리케이션 창은 다음 그림과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-218">You can see the main application window in the following picture:</span></span>

![주 애플리케이션 창](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="4153b-220">*.csproj* 프로젝트 파일을 열면 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-220">If you open the *.csproj* project file, you can see something like this:</span></span>

![csproj 파일 내용 스크린샷](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="4153b-222">앞에서 설명한 대로 .NET 프로젝트 스타일은 더 간결하며 프로젝트 구조를 새로운 .NET SDK 스타일로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-222">As previously mentioned, .NET project has a more compact style and you need to migrate the project structure to the new .NET SDK style.</span></span>

<span data-ttu-id="4153b-223">솔루션 탐색기에서 Windows Forms 프로젝트를 마우스 오른쪽 단추로 클릭하고 **프로젝트 언로드** > **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-223">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="4153b-224">이제 .csproj 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-224">Now you can update the .csproj file.</span></span> <span data-ttu-id="4153b-225">전체 내용을 삭제하고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-225">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4153b-226">프로젝트를 저장하고 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-226">Save and reload the project.</span></span> <span data-ttu-id="4153b-227">이제 프로젝트 파일 업데이트가 완료되었으며 프로젝트가 .NET을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-227">You're now done updating the project file and the project is targeting the .NET.</span></span>

<span data-ttu-id="4153b-228">이때 프로젝트를 컴파일하면 WCF 클라이언트 참조와 관련된 몇 가지 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-228">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="4153b-229">이 코드는 자동으로 생성되므로 .NET을 대상으로 하도록 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-229">Since this code is autogenerated, you must regenerate it to target .NET.</span></span>

![오류를 보여 주는 Visual Studio의 오류 목록](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="4153b-231">*Reference.cs* 파일을 삭제하고 새 서비스 클라이언트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-231">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="4153b-232">**연결된 서비스** 를 마우스 오른쪽 단추로 클릭하고 **연결된 서비스 추가** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-232">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![연결된 서비스 추가 옵션이 선택된 연결된 서비스 메뉴의 스크린샷](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="4153b-234">연결된 서비스 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-234">The Connected Services window opens.</span></span> <span data-ttu-id="4153b-235">**Microsoft WCF Web Service** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-235">Select the **Microsoft WCF Web Service** option.</span></span>

![연결된 서비스 창의 스크린샷](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="4153b-237">이 예제와 동일한 솔루션에 WCF 서비스가 있는 경우 서비스 URL을 지정하는 대신 **검색** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-237">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![WCF Web Service Reference 구성 창의 스크린샷](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="4153b-239">서비스가 있으면 서비스에 의해 구현된 API 계약이 도구에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-239">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="4153b-240">다음 이미지와 같이 네임스페이스의 이름을 `eShopServiceReference`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-240">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![API 계약 및 변경된 네임스페이스의 스크린샷](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="4153b-242">**마침** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-242">Select the **Finish** button.</span></span> <span data-ttu-id="4153b-243">잠시 후 생성된 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-243">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="4153b-244">자동 생성된 세 개의 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-244">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="4153b-245">*Getting Started*: WCF에 대한 몇 가지 정보를 제공하는 GitHub에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-245">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="4153b-246">*ConnectedService.json*: 서비스에 연결하는 구성 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-246">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="4153b-247">*Reference.cs*: 실제 WCF 클라이언트 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-247">*Reference.cs*: the actual WCF client code.</span></span>

![자동 생성된 세 개의 파일이 있는 솔루션 탐색기 창의 스크린샷](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="4153b-249">다시 컴파일하면 *Helper* 폴더 내의 *.cs* 파일에서 발생하는 많은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-249">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="4153b-250">이 폴더는 .NET Framework 버전에 있지만 이전 *.csproj* 에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-250">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="4153b-251">그러나 새로운 SDK 스타일 프로젝트를 사용하면 프로젝트 파일 위치 아래에 있는 모든 코드 파일이 기본적으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-251">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="4153b-252">즉, 새 .NET Core 프로젝트는 *Helper* 폴더 내의 파일을 컴파일하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-252">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="4153b-253">해당 폴더는 필요하지 않으므로 삭제해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-253">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="4153b-254">프로젝트를 다시 컴파일하고 실행하면 제품 이미지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-254">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="4153b-255">문제는 파일 경로가 약간 변경되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-255">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="4153b-256">이 문제를 해결하려면 경로에 다른 수준의 깊이를 추가하여 `CatalogView.cs` 파일에서 다음 줄을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-256">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="4153b-257">을</span><span class="sxs-lookup"><span data-stu-id="4153b-257">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="4153b-258">이렇게 변경하면 애플리케이션이 .NET Core에서 예상대로 시작되고 실행되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-258">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="4153b-259">WPF 애플리케이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4153b-259">Migrating a WPF application</span></span>

<span data-ttu-id="4153b-260">`Shop.ClassicWPF` 샘플 애플리케이션을 사용하여 마이그레이션을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-260">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="4153b-261">다음 이미지는 마이그레이션 전의 앱 스크린샷을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-261">The following image shows a screenshot of the app before migration:</span></span>

![마이그레이션 전의 샘플 앱](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="4153b-263">이 애플리케이션은 로컬 SQL Server Express 데이터베이스를 사용하여 제품 카탈로그 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-263">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="4153b-264">이 데이터베이스는 WPF 애플리케이션에서 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-264">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="4153b-265">먼저 *.csproj* 파일을 .NET Core 애플리케이션에서 사용하는 새 SDK 스타일로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-265">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="4153b-266">Windows Forms 마이그레이션에서 설명한 것과 동일한 단계를 수행합니다. 프로젝트를 언로드하고 *.csproj* 파일을 열고 내용을 업데이트하고 프로젝트를 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-266">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="4153b-267">이 경우 *.csproj* 파일의 내용을 모두 삭제하고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-267">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
 <Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWpf>true</UseWpf>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4153b-268">프로젝트를 다시 로드하고 컴파일하면 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-268">If you reload the project and compile it, you'll get the following error:</span></span>

![단일 오류 CS0234를 보여 주는 Visual Studio의 오류 목록](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="4153b-270">*.csproj* 내용을 모두 삭제했으므로 이전 프로젝트에 있던 프로젝트 참조 사양이 손실되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-270">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="4153b-271">프로젝트 참조를 다시 포함하려면 *.csproj* 파일에 다음 줄을 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-271">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="4153b-272">Visual Studio에서 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **프로젝트 참조 추가** 를 클릭하여 도움을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-272">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="4153b-273">솔루션에서 프로젝트를 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-273">Select the project from the solution and click **OK**:</span></span>

![eShop.SqlProvider 프로젝트가 선택된 참조 관리자 대화 상자의 스크린샷](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="4153b-275">누락된 프로젝트 참조를 추가하면 애플리케이션이 .NET에서 예상대로 컴파일되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4153b-275">Once you add the missing project reference, the application compiles and runs as expected on .NET.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4153b-276">[이전](windows-migration.md)
>[다음](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="4153b-276">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>
