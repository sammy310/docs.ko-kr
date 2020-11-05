---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bf38ffe4d47986ae78c6cf2b2e5ecb292411ba6c
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925287"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="1a4d5-104">자체 포함 배포 및 실행 파일 트리밍</span><span class="sxs-lookup"><span data-stu-id="1a4d5-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="1a4d5-105">[프레임워크 종속 배포 모델](index.md#publish-framework-dependent)은 .NET 도입 이후 가장 성공적인 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="1a4d5-106">이 시나리오에서 애플리케이션 개발자는 애플리케이션과 타사 어셈블리만 번들하고 .NET 런타임 및 프레임워크 라이브러리는 클라이언트 머신에서 사용할 수 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="1a4d5-107">이 배포 모델은 .NET Core에서도 주요 모델로 계속 사용되지만 프레임워크 종속 모델이 최적이 아닌 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="1a4d5-108">다른 방법은 .NET Core 런타임과 프레임워크가 애플리케이션 및 타사 어셈블리와 함께 번들되는 [자체 포함 애플리케이션](index.md#publish-self-contained)을 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="1a4d5-109">트리밍된 자체 포함 배포 모델은 배포 크기를 줄이도록 최적화된 특수 버전의 자체 포함 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="1a4d5-110">배포 크기 최소화는 Blazor 애플리케이션과 같은 일부 클라이언트 쪽 시나리오의 중요한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="1a4d5-111">애플리케이션 복잡성에 따라 프레임워크 어셈블리의 하위 집합만 참조되며 각 어셈블리 내 코드의 하위 집합은 애플리케이션 실행에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="1a4d5-112">사용되지 않는 라이브러리 부분은 필요가 없으며 패키지된 애플리케이션에서 트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="1a4d5-113">그러나 다양한 문제 코드 패턴을 안정적으로 분석할 수 없다는 점에서(주로 리플렉션 사용을 중심으로 함) 애플리케이션의 빌드 시간 분석으로 인해 런타임에 오류가 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="1a4d5-114">안정성을 보장할 수 없으므로 이 배포 모델은 미리 보기 기능으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="1a4d5-115">빌드 시간 분석 엔진은 문제가 있는 코드 패턴의 개발자에게 필요한 다른 코드를 검색하도록 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic to detect which other code is required.</span></span> <span data-ttu-id="1a4d5-116">포함할 다른 항목을 트리머에 알리도록 특성을 사용하여 코드에 주석을 달 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="1a4d5-117">[소스 생성기](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md)를 사용하여 많은 리플렉션 패턴을 빌드 시간 코드 생성으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="1a4d5-118">애플리케이션의 트리밍 모드는 `TrimMode` 설정으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="1a4d5-119">기본값은 `copyused`이며 참조된 어셈블리를 애플리케이션에서 번들로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="1a4d5-120">`link` 값은 Blazor WebAssembly 애플리케이션에서 사용되며 어셈블리 내에서 사용되지 않는 코드를 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="1a4d5-121">트리밍 분석 경고는 전체 종속성 분석이 불가능한 코드 패턴에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="1a4d5-122">해당 경고는 기본적으로 표시되지 않으며, `SuppressTrimAnalysisWarnings` 플래그를 `false`로 지정하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="1a4d5-123">사용 가능한 트리밍 옵션에 관한 자세한 내용은 [트리밍 옵션](trimming-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a4d5-124">트리밍은 .NET Core 3.1 및 .NET 5.0의 실험적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-124">Trimming is an experimental feature in .NET Core 3.1 and .NET 5.0.</span></span> <span data-ttu-id="1a4d5-125">트리밍은 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-125">Trimming is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="1a4d5-126">어셈블리가 트리밍되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="1a4d5-126">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="1a4d5-127">트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-127">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="1a4d5-128">예를 들어 애플리케이션 또는 애플리케이션에서 참조하는 라이브러리가 런타임 어셈블리에서 리플렉션을 사용하는 경우 어셈블리는 직접 참조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-128">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="1a4d5-129">트리밍은 이 간접 참조를 인식할 수 없으며 게시된 폴더에서 라이브러리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-129">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="1a4d5-130">코드에서 리플렉션을 통해 어셈블리를 간접적으로 참조하는 경우 `<TrimmerRootAssembly>` 설정으로 어셈블리가 트리밍되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-130">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="1a4d5-131">다음 예제에서는 `System.Security` 어셈블리라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-131">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="support-for-ssl-certificates"></a><span data-ttu-id="1a4d5-132">SSL 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="1a4d5-132">Support for SSL certificates</span></span>

<span data-ttu-id="1a4d5-133">ASP.NET Core 앱에서처럼 앱이 SSL 인증서를 로드하는 경우 트리밍할 때 SSL 인증서 로드에 도움이 되는 어셈블리가 트리밍되지 않게 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-133">If your app loads SSL certificates, such as in an ASP.NET Core app, you'll want to ensure that when trimming you prevent trimming assemblies that will help with loading SSL certificates.</span></span>

<span data-ttu-id="1a4d5-134">ASP.NET Core 3.1에 다음을 포함하도록 프로젝트 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-134">We can update our project file to include the following for ASP.NET Core 3.1:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>...</PropertyGroup>
  <!--Include the following for .aspnetcore 3.1-->
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Net" />
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

<span data-ttu-id="1a4d5-135">.Net 5.0을 사용하는 경우 다음을 포함하도록 프로젝트 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-135">If we're using .Net 5.0, we can update our project file to include the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
 <PropertyGroup>...</PropertyGroup>
 <!--Include the following for .net 5.0-->
 <ItemGroup>
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="1a4d5-136">앱 트리밍 - CLI</span><span class="sxs-lookup"><span data-stu-id="1a4d5-136">Trim your app - CLI</span></span>

<span data-ttu-id="1a4d5-137">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-137">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="1a4d5-138">앱을 게시할 때 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-138">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="1a4d5-139">특정 런타임을 위해 자체 포함 앱으로 게시: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="1a4d5-139">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="1a4d5-140">트리밍 사용: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="1a4d5-140">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="1a4d5-141">다음 예제에서는 Windows용 앱을 자체 포함으로 게시하고 출력을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-141">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="1a4d5-142">다음 예제에서는 어셈블리 내의 사용되지 않는 코드가 트리밍되고 트리머 경고가 사용되는 적극적인 트리밍 모드로 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-142">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="1a4d5-143">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-143">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="1a4d5-144">앱 트리밍 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1a4d5-144">Trim your app - Visual Studio</span></span>

<span data-ttu-id="1a4d5-145">Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-145">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="1a4d5-146">**솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-146">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="1a4d5-147">**게시...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-147">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    <span data-ttu-id="1a4d5-149">기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-149">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="1a4d5-150">**편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-150">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. <span data-ttu-id="1a4d5-152">**프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-152">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="1a4d5-153">**배포 모드** 를 **자체 포함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-153">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="1a4d5-154">**대상 런타임** 을 게시할 플랫폼으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-154">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="1a4d5-155">**사용하지 않는 어셈블리 트리밍(미리 보기)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-155">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="1a4d5-156">**저장** 을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-156">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="배포 모드, 대상 런타임 및 사용하지 않는 어셈블리 트리밍 옵션이 강조 표시된 프로필 설정 대화 상자.":::

01. <span data-ttu-id="1a4d5-158">**게시** 를 선택하여 트리밍된 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-158">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="1a4d5-159">자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-159">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="1a4d5-160">앱 트리밍 - Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1a4d5-160">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="1a4d5-161">Mac용 Visual Studio는 게시하는 동안 앱을 트리밍하는 옵션을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-161">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="1a4d5-162">[앱 트리밍 - CLI](#trim-your-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-162">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="1a4d5-163">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a4d5-163">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a4d5-164">참조</span><span class="sxs-lookup"><span data-stu-id="1a4d5-164">See also</span></span>

- <span data-ttu-id="1a4d5-165">[.NET Core 애플리케이션 배포](index.md).</span><span class="sxs-lookup"><span data-stu-id="1a4d5-165">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="1a4d5-166">[.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="1a4d5-166">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="1a4d5-167">[Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1a4d5-167">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="1a4d5-168">[dotnet publish 명령](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="1a4d5-168">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
