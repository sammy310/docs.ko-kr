---
title: .NET Core 3.1로의 마이그레이션 예제
description: .NET Framework를 대상으로 하는 샘플 응용 프로그램을 .NET Core 3.1로 마이그레이션하는 방법을 보여 줍니다.
ms.date: 05/12/2020
ms.openlocfilehash: 6a0311e9aaeb25ac39f3394d3a62e17046fe03d8
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "97866655"
---
# <a name="example-of-migrating-to-net-core-31"></a><span data-ttu-id="c54da-103">.NET Core 3.1로의 마이그레이션 예제</span><span class="sxs-lookup"><span data-stu-id="c54da-103">Example of migrating to .NET Core 3.1</span></span>

<span data-ttu-id="c54da-104">이 장에서는 기존 응용 프로그램을 .NET Framework에서 .NET Core로 마이그레이션하는 데 도움이 되는 실용적인 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET Core.</span></span>

<span data-ttu-id="c54da-105">이제는 잘 구성 된 프로세스를 수행 하 고 각 단계에서 고려해 야 할 가장 중요 한 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="c54da-106">그런 다음 WinForms 및 WPF 버전 둘 다에서 샘플 데스크톱 응용 프로그램에 대 한 단계별 마이그레이션 프로세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="c54da-107">마이그레이션 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="c54da-107">Migration process overview</span></span>

<span data-ttu-id="c54da-108">마이그레이션 프로세스는 다음과 같은 4 개의 순차적인 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="c54da-109">**준비**: 프로젝트에 미리 정의 된 종속성을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="c54da-110">이 단계에서는 현재 프로젝트를 마이그레이션 시작 지점을 간소화 하는 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="c54da-111">**프로젝트 파일 마이그레이션:** .net Core 프로젝트는 새로운 SDK 스타일 프로젝트 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-111">**Migrate Project File:** .NET Core projects use the new SDK-style project format.</span></span> <span data-ttu-id="c54da-112">이 형식을 사용 하 여 새 프로젝트 파일을 만들거나 SDK 스타일을 사용 해야 하는 프로젝트 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="c54da-113">**코드 수정 및 빌드:** .NET Framework와 .NET Core 간의 API 수준 차이를 해결 하는 .NET Core의 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-113">**Fix code and build:** Build the code in .NET Core addressing API-level differences between .NET Framework and .NET Core.</span></span> <span data-ttu-id="c54da-114">필요한 경우 .NET Core를 지 원하는 타사 패키지를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-114">If needed, update third-party packages to the ones that support .NET Core.</span></span>

4. <span data-ttu-id="c54da-115">**실행 및 테스트:** 런타임까지 표시 되지 않는 차이점이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="c54da-116">따라서 응용 프로그램을 실행 하 고 모든 것이 예상 대로 작동 하는지 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="c54da-117">준비</span><span class="sxs-lookup"><span data-stu-id="c54da-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="c54da-118">packages.config 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c54da-118">Migrate packages.config file</span></span>

<span data-ttu-id="c54da-119">.NET Framework 응용 프로그램에서는 외부 패키지에 대 한 모든 참조가 *packages.config* 파일에 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="c54da-120">.NET Core에서는 더 이상 *packages.config* 파일을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-120">In .NET Core, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="c54da-121">대신 프로젝트 파일 내에서 [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) 속성을 사용 하 여 앱에 대 한 NuGet 패키지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="c54da-122">따라서 한 형식에서 다른 형식으로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="c54da-123">업데이트를 수동으로 수행 하 고, *packages.config* 파일에 포함 된 종속성을 가져와 형식의 프로젝트 파일로 마이그레이션할 수 있습니다 `PackageReference` .</span><span class="sxs-lookup"><span data-stu-id="c54da-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="c54da-124">또는 *packages.config* 파일을 마우스 오른쪽 단추로 클릭 하 고 **PackageReference로 packages.config 마이그레이션** 옵션을 선택 하 여 Visual Studio에서 작업을 수행 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net-core"></a><span data-ttu-id="c54da-125">.NET Core의 모든 종속성 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="c54da-125">Verify every dependency compatibility in .NET Core</span></span>

<span data-ttu-id="c54da-126">패키지 참조를 마이그레이션한 후에는 각 참조의 호환성을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="c54da-127">응용 프로그램이 [nuget.org](https://www.nuget.org/)에서 사용 하는 각 NuGet 패키지의 종속성을 탐색할 수 있습니다. 패키지에 .NET Standard 종속성이 있는 경우 .NET core 3.1은 모든 버전의 .NET Standard를 [지원](../../standard/net-standard.md#net-implementation-support) 하기 때문에 .net core에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET Core because .NET Core 3.1 [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="c54da-128">다음 이미지는 패키지에 대 한 종속성을 보여 줍니다 `Castle.Windsor` .</span><span class="sxs-lookup"><span data-stu-id="c54da-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Windsor 패키지에 대 한 NuGet 종속성의 스크린샷](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="c54da-130">패키지 호환성을 확인 하려면 <https://fuget.org> 버전 및 종속성에 대 한 자세한 정보를 제공 하는 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="c54da-131">프로젝트가 .NET Core를 지원 하지 않는 이전 패키지 버전을 참조 하지만 지원 되는 최신 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-131">Maybe the project is referencing older package versions that don't support .NET Core, but you might find newer versions that do support it.</span></span> <span data-ttu-id="c54da-132">따라서 패키지를 최신 버전으로 업데이트 하는 것이 일반적으로 좋은 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="c54da-133">그러나 패키지 버전을 업데이트 하면 코드를 업데이트 하는 데 적용 되는 몇 가지 주요 변경 사항이 발생할 수 있다는 점을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="c54da-134">호환 되는 버전을 찾지 못하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="c54da-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="c54da-135">이러한 주요 변경 내용으로 인해 패키지 버전을 업데이트 하지 않으려는 경우는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="c54da-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="c54da-136">.NET Core 응용 프로그램에서 .NET Framework 패키지에 의존할 수 있으므로 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET Core application.</span></span> <span data-ttu-id="c54da-137">외부 패키지가 .NET Core에서 사용할 수 없는 API를 호출 하는 경우 런타임 오류가 발생할 수 있으므로 광범위 하 게 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET Core.</span></span> <span data-ttu-id="c54da-138">업데이트 하지 않을 이전 패키지를 사용 하 고 .NET Core에서 작업을 대상으로 지정할 수 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET Core.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="c54da-139">API 호환성 확인</span><span class="sxs-lookup"><span data-stu-id="c54da-139">Check for API compatibility</span></span>

<span data-ttu-id="c54da-140">.NET Framework와 .NET Core의 API 화면은 동일 하지만 동일 하지 않기 때문에 .NET Core에서 사용할 수 있는 Api와이 아닌 Api를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-140">Since the API surface in .NET Framework and .NET Core is similar but not identical, you must check which APIs are available on .NET Core and which aren't.</span></span> <span data-ttu-id="c54da-141">.Net 이식성 분석기 도구를 사용 하 여 .NET Core에 없는 Api를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET Core.</span></span> <span data-ttu-id="c54da-142">앱의 이진 수준을 확인 하 고, 호출 되는 모든 Api를 추출한 다음 대상 프레임 워크에서 사용할 수 없는 Api를 나열 합니다 (이 경우 .NET Core 3.1).</span><span class="sxs-lookup"><span data-stu-id="c54da-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET Core 3.1 in this case).</span></span>

<span data-ttu-id="c54da-143">이 도구에 대 한 자세한 내용은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="c54da-144">이 도구의 흥미로운 측면은 사용자가 변경할 수 없는 외부 패키지의 코드가 아닌 사용자 고유의 코드에서 발생 하는 차이를 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="c54da-145">이러한 패키지는 대부분 .NET Core에서 작동 하도록 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-145">Remember you should have updated most of these packages to make them work with .NET Core.</span></span>

### <a name="migrate-project-file"></a><span data-ttu-id="c54da-146">프로젝트 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c54da-146">Migrate project file</span></span>

#### <a name="create-the-new-net-core-project"></a><span data-ttu-id="c54da-147">새 .NET Core 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="c54da-147">Create the new .NET Core project</span></span>

<span data-ttu-id="c54da-148">대부분의 경우 기존 프로젝트를 새 .NET Core 형식으로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-148">In most of the cases, you'll want to update your existing project to the new .NET Core format.</span></span> <span data-ttu-id="c54da-149">그러나 기존 프로젝트를 유지 하면서 새 프로젝트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-149">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="c54da-150">이전 프로젝트를 업데이트 하는 경우의 주요 단점은 디자이너 지원이 손실 된다는 것입니다 .이는 사용자에 게 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-150">The main drawback from updating the old project is that you lose designer support, which may be important for you.</span></span> <span data-ttu-id="c54da-151">디자이너를 계속 사용 하려는 경우 기존 .NET Core 프로젝트를 사용 하 여 새 .NET Core 프로젝트를 만들고 자산을 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-151">If you want to keep using the designer, you must create a new .NET Core project in parallel with the old one and share assets.</span></span> <span data-ttu-id="c54da-152">디자이너에서 UI 요소를 수정 해야 하는 경우 이전 프로젝트로 전환 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-152">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="c54da-153">자산은 연결 되어 있으므로 .NET Core 프로젝트 에서도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-153">And since assets are linked, they'll be updated in the .NET Core project as well.</span></span>

<span data-ttu-id="c54da-154">.NET Core에 대 한 [SDK 스타일 프로젝트](../../core/project-sdk/msbuild-props.md) 는 .NET Framework의 프로젝트 형식 보다 훨씬 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-154">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET Core is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="c54da-155">앞에서 언급 한 항목과는 별도로 `PackageReference` 더 많은 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-155">And apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="c54da-156">새 프로젝트 형식에는 및 파일과 같이 [기본적으로](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects) `.cs` `.xaml` 프로젝트 파일에 명시적으로 포함할 필요 없이 특정 파일 확장명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-156">The new project format includes certain file extensions [by default](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="c54da-157">Assembly.info 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c54da-157">Assembly.info considerations</span></span>

<span data-ttu-id="c54da-158">특성은 .NET Core 프로젝트에서 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-158">Attributes are autogenerated on .NET Core projects.</span></span> <span data-ttu-id="c54da-159">프로젝트에 *AssemblyInfo.cs* 파일이 포함 되어 있으면 정의가 중복 되어 컴파일 충돌이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-159">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="c54da-160">.NET Core 프로젝트 파일에 다음 항목을 추가 하 여 이전 *AssemblyInfo.cs* 파일을 삭제 하거나 자동 생성을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-160">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET Core project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="c54da-161">리소스</span><span class="sxs-lookup"><span data-stu-id="c54da-161">Resources</span></span>

<span data-ttu-id="c54da-162">포함 리소스는 자동으로 포함 되지만 리소스는 아니지만 리소스를 새 프로젝트 파일로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-162">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="c54da-163">패키지 참조</span><span class="sxs-lookup"><span data-stu-id="c54da-163">Package references</span></span>

<span data-ttu-id="c54da-164">**PackageReference로 packages.config 마이그레이션** 옵션을 사용 하면 앞에서 설명한 대로 외부 패키지 참조를 새 형식으로 쉽게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-164">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="c54da-165">패키지 참조 업데이트</span><span class="sxs-lookup"><span data-stu-id="c54da-165">Update package references</span></span>

<span data-ttu-id="c54da-166">이전 섹션에 나와 있는 것 처럼 호환 되는 것으로 확인 된 패키지의 버전을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-166">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="c54da-167">코드 수정 및 빌드</span><span class="sxs-lookup"><span data-stu-id="c54da-167">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="c54da-168">Microsoft. Windows 호환성</span><span class="sxs-lookup"><span data-stu-id="c54da-168">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="c54da-169">응용 프로그램이 레지스트리, Acl 또는 WCF와 같이 .NET Core에서 사용할 수 없는 Api를 사용 하는 경우 `Microsoft.Windows.Compatibility` 이러한 Windows 관련 api를 추가 하려면 패키지에 대 한 참조를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-169">If your application depends on APIs that aren't available on .NET Core, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="c54da-170">이러한 도구는 .NET Core에서 작동 하지만 플랫폼 간에는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-170">They work on .NET Core but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="c54da-171"><https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>코드와 호환 되지 않는 api를 식별 하는 데 도움이 되는 Api Analyzer () 라는 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-171">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="c54da-172">\#If 지시문 사용</span><span class="sxs-lookup"><span data-stu-id="c54da-172">Use \#if directives</span></span>

<span data-ttu-id="c54da-173">.NET Framework 및 .NET Core를 대상으로 지정 하는 경우 다른 실행 경로가 필요한 경우 컴파일 상수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-173">If you need different execution paths when targeting .NET Framework and .NET Core, you should use compilation constants.</span></span> <span data-ttu-id="c54da-174">일부 \# if 지시문을 코드에 추가 하 여 두 대상에 대해 동일한 코드 베이스를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-174">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net-core"></a><span data-ttu-id="c54da-175">.NET Core에서 사용할 수 없는 기술</span><span class="sxs-lookup"><span data-stu-id="c54da-175">Technologies not available on .NET Core</span></span>

<span data-ttu-id="c54da-176">다음과 같은 일부 기술은 .NET Core에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-176">Some technologies aren't available on .NET Core, such as:</span></span>

* <span data-ttu-id="c54da-177">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c54da-177">AppDomains</span></span>
* <span data-ttu-id="c54da-178">원격 통신</span><span class="sxs-lookup"><span data-stu-id="c54da-178">Remoting</span></span>
* <span data-ttu-id="c54da-179">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="c54da-179">Code Access Security</span></span>
* <span data-ttu-id="c54da-180">WCF 서버</span><span class="sxs-lookup"><span data-stu-id="c54da-180">WCF Server</span></span>
* <span data-ttu-id="c54da-181">Windows 워크플로</span><span class="sxs-lookup"><span data-stu-id="c54da-181">Windows Workflow</span></span>

<span data-ttu-id="c54da-182">이러한 이유로 응용 프로그램에서 사용 하는 경우 이러한 기술을 대체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-182">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="c54da-183">자세한 내용은 [.Net Core에서 사용할 수 없는 .NET Framework 기술](../../core/porting/net-framework-tech-unavailable.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c54da-183">For more information, see the [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="c54da-184">자동 생성 클라이언트 다시 생성</span><span class="sxs-lookup"><span data-stu-id="c54da-184">Regenerate autogenerated clients</span></span>

<span data-ttu-id="c54da-185">응용 프로그램에서 WCF 클라이언트와 같은 자동 생성 된 코드를 사용 하는 경우 .NET Core를 대상으로 하기 위해이 코드를 다시 생성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-185">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET Core.</span></span> <span data-ttu-id="c54da-186">경우에 따라 일부 누락 된 참조는 기본 .NET Core 어셈블리 집합의 일부로 포함 되지 않을 수 있기 때문에 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-186">Sometimes, you can find some missing references since they may not be included as part of the default .NET Core assemblies set.</span></span> <span data-ttu-id="c54da-187">와 같은 도구를 사용 하 여 <https://apisof.net/> 누락 된 참조가 상주 하는 어셈블리를 쉽게 찾아 NuGet에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-187">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="c54da-188">패키지 버전 롤백</span><span class="sxs-lookup"><span data-stu-id="c54da-188">Rolling back package versions</span></span>

<span data-ttu-id="c54da-189">일반적으로 .NET Core와 호환 되도록 모든 단일 패키지 버전을 더 잘 업데이트 한다고 이미 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-189">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET Core.</span></span> <span data-ttu-id="c54da-190">그러나 어셈블리의 업데이트 된 버전과 호환 되는 버전을 대상으로 하는 것을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-190">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="c54da-191">변경 비용이 허용 되지 않는 경우 .NET Framework에서 사용 하는 패키지 버전을 롤백하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-191">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="c54da-192">.NET Core를 대상으로 하지 않을 수도 있지만 지원 되지 않는 일부 Api를 호출 하지 않는 한 잘 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-192">Although they may not be targeting .NET Core, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="c54da-193">실행 및 테스트</span><span class="sxs-lookup"><span data-stu-id="c54da-193">Run and test</span></span>

<span data-ttu-id="c54da-194">응용 프로그램 빌드에 오류가 발생 하지 않으면 모든 기능을 테스트 하 여 마이그레이션의 마지막 단계를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-194">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="c54da-195">이 마지막 단계에서는 응용 프로그램의 복잡성과 사용 중인 종속성 및 Api에 따라 여러 가지 문제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-195">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="c54da-196">예를 들어 구성 파일 (*app.config*)을 사용 하는 경우 구성 섹션과 같이 런타임에 몇 가지 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-196">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="c54da-197">NuGet 패키지를 사용 하면 `Microsoft.Extensions.Configuration` 이 오류를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-197">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="c54da-198">오류가 발생 하는 또 다른 이유는 `BeginInvoke` `EndInvoke` .net Core에서 지원 되지 않기 때문에 및 메서드를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-198">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET Core.</span></span> <span data-ttu-id="c54da-199">.Net core에는 존재 하지 않는 원격 기능에 종속 되어 있기 때문에 .NET Core에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-199">They aren't supported on .NET Core because they have a dependency on Remoting, which doesn't exist on .NET Core.</span></span> <span data-ttu-id="c54da-200">이 문제를 해결 하려면 `await` 키워드 (사용 가능한 경우) 또는 메서드를 사용 하십시오 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c54da-200">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c54da-201">호환성 분석기를 사용 하 여 코드에서 .NET Core로 런타임에 문제를 일으킬 수 있는 Api 및 코드 패턴을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-201">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET Core.</span></span> <span data-ttu-id="c54da-202">로 이동 하 여 <https://github.com/dotnet/platform-compat> 프로젝트에서 .NET API analyzer를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-202">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="c54da-203">Windows Forms 응용 프로그램 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c54da-203">Migrating a Windows Forms application</span></span>

<span data-ttu-id="c54da-204">Windows Forms 응용 프로그램의 전체 마이그레이션 프로세스를 소개 하기 위해에서 사용할 수 있는 eShop 샘플 응용 프로그램을 마이그레이션하도록 선택 했습니다 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="c54da-204">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="c54da-205">에서 마이그레이션의 전체 결과를 찾을 수 있습니다 <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="c54da-205">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="c54da-206">이 응용 프로그램은 제품 카탈로그를 표시 하 고 사용자가 제품을 탐색, 필터링 및 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-206">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="c54da-207">아키텍처 관점에서 앱은 백 엔드 데이터베이스에 대 한 외관 역할을 하는 외부 WCF 서비스에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-207">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="c54da-208">다음 그림에서 주 응용 프로그램 창을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-208">You can see the main application window in the following picture:</span></span>

![주 응용 프로그램 창](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="c54da-210">*.Csproj* 프로젝트 파일을 여는 경우 다음과 같은 내용이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-210">If you open the *.csproj* project file, you can see something like this:</span></span>

![.Csproj 파일 내용의 스크린샷](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="c54da-212">앞에서 설명한 것 처럼 .NET Core 프로젝트에는 더 간결한 스타일이 있으며 프로젝트 구조를 새 .NET Core SDK 스타일로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-212">As previously mentioned, .NET Core project has a more compact style and you need to migrate the project structure to the new .NET Core SDK style.</span></span>

<span data-ttu-id="c54da-213">솔루션 탐색기에서 Windows Forms 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 언로드**  >  **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-213">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="c54da-214">이제 .csproj 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-214">Now you can update the .csproj file.</span></span> <span data-ttu-id="c54da-215">전체 콘텐츠를 삭제 하 고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-215">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="c54da-216">프로젝트를 저장 하 고 다시 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-216">Save and reload the project.</span></span> <span data-ttu-id="c54da-217">이제 프로젝트 파일 업데이트가 완료 되었으며 프로젝트가 .NET Core를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-217">You're now done updating the project file and the project is targeting the .NET Core.</span></span>

<span data-ttu-id="c54da-218">이 시점에서 프로젝트를 컴파일하면 WCF 클라이언트 참조와 관련 된 몇 가지 오류가 발견 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-218">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="c54da-219">이 코드는 자동으로 생성 되므로 .NET Core를 대상으로 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-219">Since this code is autogenerated, you must regenerate it to target .NET Core.</span></span>

![Visual Studio의 컴파일 오류 스크린샷](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="c54da-221">*Reference.cs* 파일을 삭제 하 고 새 서비스 클라이언트를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-221">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="c54da-222">**연결된 서비스** 를 마우스 오른쪽 단추로 클릭 하 고 **연결 된 서비스 추가** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-222">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![연결 된 서비스 추가 옵션이 선택 된 연결된 서비스 메뉴의 스크린샷](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="c54da-224">연결된 서비스 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-224">The Connected Services window opens.</span></span> <span data-ttu-id="c54da-225">**MICROSOFT WCF 웹 서비스** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-225">Select the **Microsoft WCF Web Service** option.</span></span>

![연결된 서비스 창의 스크린샷](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="c54da-227">이 예제와 동일한 솔루션에 WCF 서비스가 있는 경우 서비스 URL을 지정 하는 대신 **검색** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-227">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![WCF 웹 서비스 참조 구성 창의 스크린샷](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="c54da-229">서비스가 있으면이 도구는 서비스에 의해 구현 된 API 계약을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-229">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="c54da-230">다음 이미지와 같이 네임 스페이스의 이름을로 변경 합니다 `eShopServiceReference` .</span><span class="sxs-lookup"><span data-stu-id="c54da-230">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![API 계약 및 네임 스페이스 변경 된 스크린 샷](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="c54da-232">**마침** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-232">Select the **Finish** button.</span></span> <span data-ttu-id="c54da-233">잠시 후 생성 된 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-233">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="c54da-234">세 개의 자동 생성 파일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-234">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="c54da-235">*시작*: WCF에 대 한 일부 정보를 제공 하는 GitHub에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-235">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="c54da-236">*ConnectedService.json*: 서비스에 연결할 구성 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-236">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="c54da-237">*Reference.cs*: 실제 WCF 클라이언트 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-237">*Reference.cs*: the actual WCF client code.</span></span>

![세 개의 자동 생성 파일을 사용 하는 솔루션 탐색기 창의 스크린샷](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="c54da-239">다시 컴파일하는 경우에는 해당 *도우미* 폴더 내의 *.cs* 파일에서 발생 하는 많은 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-239">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="c54da-240">이 폴더는 .NET Framework 버전에 있지만 이전 *.csproj* 에는 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-240">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="c54da-241">그러나 새 SDK 스타일 프로젝트를 사용 하면 프로젝트 파일 위치 아래에 있는 모든 코드 파일이 기본적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-241">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="c54da-242">즉, 새 .NET Core 프로젝트는 *도우미* 폴더 내에서 파일을 컴파일하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-242">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="c54da-243">해당 폴더가 필요 하지 않으므로 안전 하 게 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-243">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="c54da-244">프로젝트를 다시 컴파일하여 실행 하면 제품 이미지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-244">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="c54da-245">문제는 이제 파일 경로가 약간 변경 되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-245">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="c54da-246">이 문제를 해결 하려면 경로에 다른 수준의 깊이를 추가 하 여 파일의 줄을 업데이트 해야 합니다 `CatalogView.cs` .</span><span class="sxs-lookup"><span data-stu-id="c54da-246">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="c54da-247">다음으로 변경:</span><span class="sxs-lookup"><span data-stu-id="c54da-247">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="c54da-248">이렇게 변경한 후에는 응용 프로그램이 시작 되 고 .NET Core에서 예상 대로 실행 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-248">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="c54da-249">WPF 응용 프로그램 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c54da-249">Migrating a WPF application</span></span>

<span data-ttu-id="c54da-250">`Shop.ClassicWPF`예제 응용 프로그램을 사용 하 여 마이그레이션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-250">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="c54da-251">다음 이미지는 마이그레이션 전의 앱 스크린샷을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-251">The following image shows a screenshot of the app before migration:</span></span>

![마이그레이션 전의 샘플 앱](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="c54da-253">이 응용 프로그램은 로컬 SQL Server Express 데이터베이스를 사용 하 여 제품 카탈로그 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-253">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="c54da-254">이 데이터베이스는 WPF 응용 프로그램에서 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-254">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="c54da-255">먼저 *.csproj* 파일을 .net Core 응용 프로그램에서 사용 하는 새 SDK 스타일로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-255">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="c54da-256">Windows Forms 마이그레이션에 설명 된 것과 동일한 단계를 따릅니다. 프로젝트를 언로드하고 *.csproj* 파일을 열고 콘텐츠를 업데이트 하 고 프로젝트를 다시 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-256">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="c54da-257">이 경우 *.csproj* 파일의 내용을 모두 삭제 하 고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-257">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWpf>true</UseWpf>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="c54da-258">프로젝트를 다시 로드 하 고 컴파일하면 다음과 같은 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-258">If you reload the project and compile it, you'll get the following error:</span></span>

![Visual Studio의 컴파일 오류 스크린샷](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="c54da-260">*.Csproj* 콘텐츠를 모두 삭제 했기 때문에 이전 프로젝트에 존재 하는 프로젝트 참조 사양이 손실 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-260">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="c54da-261">프로젝트 참조를 다시 포함 하려면 .csproj 파일에이 줄을 추가 하기만 하면 *됩니다* .</span><span class="sxs-lookup"><span data-stu-id="c54da-261">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="c54da-262">**종속성** 노드를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 참조 추가** 를 선택 하 여 Visual Studio에서 도움을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-262">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="c54da-263">솔루션에서 프로젝트를 선택 하 고 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-263">Select the project from the solution and click **OK**:</span></span>

![EShop. SqlProvider 프로젝트가 선택 된 참조 관리자 대화 상자의 스크린샷](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="c54da-265">누락 된 프로젝트 참조를 추가 하면 응용 프로그램은 .NET Core에서 정상적으로 컴파일되고 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54da-265">Once you add the missing project reference, the application compiles and runs as expected on .NET Core.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c54da-266">[이전](windows-migration.md)
>[다음](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="c54da-266">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>
