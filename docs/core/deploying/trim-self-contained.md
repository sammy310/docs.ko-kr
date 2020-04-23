---
title: 자체 포함 애플리케이션 트리밍
description: 자체 포함 앱을 트리밍하여 크기를 줄이는 방법을 알아봅니다. .NET Core는 게시된 자체 포함 앱과 런타임을 묶고, 일반적으로 필요한 수준보다 더 많은 런타임을 포함합니다.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242920"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="8bbb0-104">자체 포함 배포 및 실행 파일 트리밍</span><span class="sxs-lookup"><span data-stu-id="8bbb0-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="8bbb0-105">자체 포함 애플리케이션을 게시하면 .NET Core 런타임이 애플리케이션과 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="8bbb0-106">이렇게 묶음으로써 패키지된 애플리케이션에 상당한 양의 콘텐츠가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="8bbb0-107">애플리케이션 배포와 관련하여 크기는 종종 중요한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="8bbb0-108">패키지 애플리케이션의 크기를 가능한 한 작게 유지하는 것은 일반적으로 애플리케이션 개발자의 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="8bbb0-109">애플리케이션의 복잡성에 따라 런타임의 하위 집합만 애플리케이션 실행에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="8bbb0-110">사용되지 않는 이러한 런타임 부분은 필요 없으며 패키지된 애플리케이션에서 트리밍해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="8bbb0-111">트리밍 기능은 애플리케이션 이진 파일을 검사하여 필요한 런타임 어셈블리의 그래프를 발견하고 작성하는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="8bbb0-112">참조되지 않는 나머지 런타임 어셈블리는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="8bbb0-113">트리밍은 .NET Core 3.1의 실험적 기능이며 ‘게시된 자체 포함 애플리케이션에만’ 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="8bbb0-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="8bbb0-114">어셈블리가 트리밍되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="8bbb0-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="8bbb0-115">트리밍 기능에서 참조를 검색하지 못하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="8bbb0-116">예를 들어 애플리케이션 또는 애플리케이션에서 참조하는 라이브러리가 런타임 어셈블리에서 리플렉션을 사용하는 경우 어셈블리는 직접 참조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="8bbb0-117">트리밍은 이 간접 참조를 인식할 수 없으며 게시된 폴더에서 라이브러리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="8bbb0-118">코드에서 리플렉션을 통해 어셈블리를 간접적으로 참조하는 경우 `<TrimmerRootAssembly>` 설정으로 어셈블리가 트리밍되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="8bbb0-119">다음 예제에서는 `System.Security` 어셈블리라는 어셈블리가 트리밍되지 않게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="8bbb0-120">앱 트리밍 - CLI</span><span class="sxs-lookup"><span data-stu-id="8bbb0-120">Trim your app - CLI</span></span>

<span data-ttu-id="8bbb0-121">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 애플리케이션을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="8bbb0-122">앱을 게시하는 경우 다음 세 가지 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="8bbb0-123">자체 포함으로 게시: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="8bbb0-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="8bbb0-124">단일 파일 게시 사용 안 함: `-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="8bbb0-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="8bbb0-125">트리밍 사용: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="8bbb0-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="8bbb0-126">다음 예제에서는 Windows 10용 앱을 자체 포함으로 게시하고 출력을 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="8bbb0-127">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="8bbb0-128">앱 트리밍 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8bbb0-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="8bbb0-129">Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="8bbb0-130">**솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="8bbb0-131">**게시...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    <span data-ttu-id="8bbb0-133">기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="8bbb0-134">**편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. <span data-ttu-id="8bbb0-136">**프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="8bbb0-137">**배포 모드**를 **자체 포함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="8bbb0-138">**대상 런타임**을 게시할 플랫폼으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="8bbb0-139">**사용하지 않는 어셈블리 트리밍(미리 보기)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="8bbb0-140">**저장**을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="배포 모드, 대상 런타임 및 사용하지 않는 어셈블리 트리밍 옵션이 강조 표시된 프로필 설정 대화 상자.":::

01. <span data-ttu-id="8bbb0-142">**게시**를 선택하여 트리밍된 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="8bbb0-143">자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="8bbb0-144">앱 트리밍 - Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8bbb0-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="8bbb0-145">Mac용 Visual Studio는 게시하는 동안 앱을 트리밍하는 옵션을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="8bbb0-146">[앱 트리밍 - CLI](#trim-your-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="8bbb0-147">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbb0-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bbb0-148">참조</span><span class="sxs-lookup"><span data-stu-id="8bbb0-148">See also</span></span>

- <span data-ttu-id="8bbb0-149">[.NET Core 애플리케이션 배포](index.md).</span><span class="sxs-lookup"><span data-stu-id="8bbb0-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="8bbb0-150">[.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="8bbb0-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="8bbb0-151">[Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8bbb0-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="8bbb0-152">[dotnet publish 명령](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="8bbb0-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
