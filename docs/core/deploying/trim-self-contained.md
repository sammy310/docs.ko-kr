---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 0fde409e9e5911213855ab206368d302b73eebb3
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720126"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="0d281-104">자체 포함 배포 및 실행 파일 트리밍</span><span class="sxs-lookup"><span data-stu-id="0d281-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="0d281-105">[프레임워크 종속 배포 모델](index.md#publish-framework-dependent)은 .NET 도입 이후 가장 성공적인 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="0d281-106">이 시나리오에서 애플리케이션 개발자는 애플리케이션과 타사 어셈블리만 번들하고 .NET 런타임 및 프레임워크 라이브러리는 클라이언트 머신에서 사용할 수 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="0d281-107">이 배포 모델은 .NET Core에서도 주요 모델로 계속 사용되지만 프레임워크 종속 모델이 최적이 아닌 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="0d281-108">다른 방법은 .NET Core 런타임과 프레임워크가 애플리케이션 및 타사 어셈블리와 함께 번들되는 [자체 포함 애플리케이션](index.md#publish-self-contained)을 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="0d281-109">트리밍된 자체 포함 배포 모델은 배포 크기를 줄이도록 최적화된 특수 버전의 자체 포함 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="0d281-110">배포 크기 최소화는 Blazor 애플리케이션과 같은 일부 클라이언트 쪽 시나리오의 중요한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="0d281-111">애플리케이션 복잡성에 따라 애플리케이션 실행에 필요한 것은 프레임워크 어셈블리의 일부일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-111">Depending on the complexity of the application, only a subset of the framework assemblies is required to run the application.</span></span> <span data-ttu-id="0d281-112">사용되지 않는 라이브러리 부분은 필요 없으며 패키지된 애플리케이션에서 트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-112">These unused parts of the library are unnecessary and can be trimmed from the packaged application.</span></span> <span data-ttu-id="0d281-113">그러나 다양한 문제 코드 패턴을 안정적으로 분석할 수 없다는 점에서(주로 리플렉션 사용을 중심으로 함) 애플리케이션의 빌드 시간 분석으로 인해 런타임에 오류가 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="0d281-114">안정성을 보장할 수 없으므로 이 배포 모델은 미리 보기 기능으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span> <span data-ttu-id="0d281-115">빌드 시간 분석 엔진은 문제가 되는 코드 패턴의 개발자에게 경고하고, 해당 코드 패턴이 수정될 것이라고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic, with the expectation that these code patterns will be fixed.</span></span> <span data-ttu-id="0d281-116">가능한 경우 동일한 요구 사항을 충족하는 코드를 사용하여 애플리케이션의 런타임 리플렉션 종속성을 빌드 시간으로 모두 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-116">Where possible, we recommend that you move any runtime reflection dependencies in your application to build time by using code that meets the same requirements.</span></span>

<span data-ttu-id="0d281-117">애플리케이션의 트리밍 모드는 TrimMode를 통해 구성할 수 있으며, 애플리케이션에서 사용되는 어셈블리를 번들하는 `copyused`로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-117">The trim mode for the applications can be configured via the TrimMode and will default (`copyused`) to bundle assemblies that are used in the application.</span></span> <span data-ttu-id="0d281-118">Blazor WebAssembly 애플리케이션은 어셈블리 내에서 사용되지 않는 코드를 트리밍하는 더 적극적인 모드(`link`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-118">Blazor WebAssembly applications will use a more aggressive mode (`link`) that will trim unused code within assemblies.</span></span> <span data-ttu-id="0d281-119">트리밍 분석 경고는 전체 종속성 분석이 불가능한 코드 패턴에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-119">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="0d281-120">해당 경고는 기본적으로 표시되지 않으며, `SuppressTrimAnalysisWarnings` 플래그를 false로 설정하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-120">These warnings are suppressed by default and can be turned on by setting the flag, `SuppressTrimAnalysisWarnings`, to false.</span></span> <span data-ttu-id="0d281-121">사용 가능한 트리밍 옵션에 대한 자세한 내용은 [ILLinker 페이지](https://github.com/mono/linker/blob/master/docs/illink-options.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-121">More information on the trim options available can be found at the [ILLinker page](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0d281-122">트리밍은 .NET Core 3.1, 5.0의 실험적 기능이며 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-122">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="0d281-123">어셈블리가 트리밍되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="0d281-123">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="0d281-124">트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-124">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="0d281-125">예를 들어 애플리케이션 또는 애플리케이션에서 참조하는 라이브러리가 런타임 어셈블리에서 리플렉션을 사용하는 경우 어셈블리는 직접 참조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-125">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="0d281-126">트리밍은 이 간접 참조를 인식할 수 없으며 게시된 폴더에서 라이브러리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-126">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="0d281-127">코드에서 리플렉션을 통해 어셈블리를 간접적으로 참조하는 경우 `<TrimmerRootAssembly>` 설정으로 어셈블리가 트리밍되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-127">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="0d281-128">다음 예제에서는 `System.Security` 어셈블리라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-128">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="0d281-129">앱 트리밍 - CLI</span><span class="sxs-lookup"><span data-stu-id="0d281-129">Trim your app - CLI</span></span>

<span data-ttu-id="0d281-130">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-130">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="0d281-131">앱을 게시하는 경우 다음 세 가지 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-131">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="0d281-132">자체 포함으로 게시: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="0d281-132">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="0d281-133">트리밍 사용: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="0d281-133">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="0d281-134">다음 예제에서는 Windows용 앱을 자체 포함으로 게시하고 출력을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-134">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<ItemGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <PublishTrimmed>true</PublishTrimmed>
</ItemGroup>
```

<span data-ttu-id="0d281-135">다음 예제에서는 어셈블리 내의 사용되지 않는 코드가 트리밍되고 트리머 경고가 사용되는 적극적인 트리밍 모드로 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-135">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and  trimmer warnings enabled.</span></span>

```xml
<ItemGroup>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</ItemGroup>
```

<span data-ttu-id="0d281-136">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d281-136">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="0d281-137">앱 트리밍 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0d281-137">Trim your app - Visual Studio</span></span>

<span data-ttu-id="0d281-138">Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-138">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="0d281-139">**솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-139">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="0d281-140">**게시...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-140">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    <span data-ttu-id="0d281-142">기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-142">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="0d281-143">**편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-143">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. <span data-ttu-id="0d281-145">**프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-145">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="0d281-146">**배포 모드**를 **자체 포함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-146">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="0d281-147">**대상 런타임**을 게시할 플랫폼으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-147">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="0d281-148">**사용하지 않는 어셈블리 트리밍(미리 보기)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-148">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="0d281-149">**저장**을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-149">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="배포 모드, 대상 런타임 및 사용하지 않는 어셈블리 트리밍 옵션이 강조 표시된 프로필 설정 대화 상자.":::

01. <span data-ttu-id="0d281-151">**게시**를 선택하여 트리밍된 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-151">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="0d281-152">자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d281-152">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="0d281-153">앱 트리밍 - Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0d281-153">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="0d281-154">Mac용 Visual Studio는 게시하는 동안 앱을 트리밍하는 옵션을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-154">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="0d281-155">[앱 트리밍 - CLI](#trim-your-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d281-155">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="0d281-156">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d281-156">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d281-157">참조</span><span class="sxs-lookup"><span data-stu-id="0d281-157">See also</span></span>

- <span data-ttu-id="0d281-158">[.NET Core 애플리케이션 배포](index.md).</span><span class="sxs-lookup"><span data-stu-id="0d281-158">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="0d281-159">[.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="0d281-159">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="0d281-160">[Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0d281-160">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="0d281-161">[dotnet publish 명령](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="0d281-161">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
