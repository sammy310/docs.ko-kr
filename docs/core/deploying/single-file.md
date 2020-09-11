---
title: 단일 파일 애플리케이션
description: 단일 파일 애플리케이션이란 무엇이고, 이 애플리케이션 배포 모델 사용을 왜 고려해야 하는지를 알아봅니다.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495756"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="14b6b-103">단일 파일 배포 및 실행 파일</span><span class="sxs-lookup"><span data-stu-id="14b6b-103">Single file deployment and executable</span></span>

<span data-ttu-id="14b6b-104">모든 애플리케이션 종속 파일을 하나의 이진 파일로 묶으면 애플리케이션 개발자가 애플리케이션을 단일 파일로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="14b6b-105">이 배포 모델은 .NET Core 3.0부터 사용할 수 있었으며 .NET 5.0에서 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="14b6b-106">이전의 .NET Core 3.0에서는 사용자가 단일 파일 앱을 실행할 때 .NET Core 호스트에서 먼저 모든 파일을 임시 디렉터리로 추출한 후 애플리케이션을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="14b6b-107">.NET 5.0에서는 앱에서 파일을 추출할 필요 없이 코드를 직접 실행하여 이 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="14b6b-108">단일 파일 배포는 [프레임워크 종속 배포 모델](index.md#publish-framework-dependent)과 [자체 포함 애플리케이션](index.md#publish-self-contained)에 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="14b6b-109">자체 포함 애플리케이션의 단일 파일 크기는 런타임 및 프레임워크 라이브러리를 포함하므로 커집니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="14b6b-110">단일 파일 배포 옵션을 [ReadyToRun](../tools/dotnet-publish.md) 및 [Trim(.NET 5.0의 실험적 기능)](trim-self-contained.md) 게시 옵션과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="14b6b-111">단일 파일 사용과 관련해서 유의해야 할 몇 가지 사항이 있습니다. 먼저, 경로 정보를 사용하여 애플리케이션 위치를 기준으로 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="14b6b-112"><xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API는 메모리에서 로드된 어셈블리의 기본 동작인 빈 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="14b6b-113">컴파일러는 빌드 시간에 이 API에 대한 경고를 제공하여 개발자에게 특정 동작을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="14b6b-114">애플리케이션 디렉터리 경로가 필요한 경우 <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API는 AppHost(단일 파일 번들 자체)가 있는 디렉터리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="14b6b-115">관리형 C++ 애플리케이션은 단일 파일 배포에 적합하지 않으므로 C#으로 단일 파일 호환 애플리케이션을 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="14b6b-116">단일 파일은 기본적으로 네이티브 라이브러리를 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="14b6b-117">Linux에서는 런타임을 번들로 사전 링크하며, 애플리케이션 네이티브 라이브러리만 단일 파일 앱과 동일한 디렉터리에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="14b6b-118">Windows에서는 호스팅 코드만 사전 링크하며, 런타임 및 애플리케이션 네이티브 라이브러리가 모두 단일 파일 앱과 동일한 디렉터리에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="14b6b-119">그러면 네이티브 파일을 단일 파일에서 제외해야 하는 좋은 디버깅 환경이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="14b6b-120">`IncludeNativeLibrariesForSelfExtract` 플래그를 설정하면 네이티브 라이브러리가 단일 파일 번들에 포함되지만 단일 파일 애플리케이션을 실행할 때 클라이언트 머신의 임시 디렉터리에 파일이 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="14b6b-121">파일이 포함되지 않도록 제외</span><span class="sxs-lookup"><span data-stu-id="14b6b-121">Exclude files from being embedded</span></span>

<span data-ttu-id="14b6b-122">다음 메타데이터를 설정하면 특정 파일이 단일 파일에 포함되지 않도록 명시적으로 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="14b6b-123">예를 들어 일부 파일을 게시 디렉터리에 저장하지만 단일 파일에 묶이지 않도록 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="14b6b-124">단일 파일 앱 게시 - CLI</span><span class="sxs-lookup"><span data-stu-id="14b6b-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="14b6b-125">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 단일 파일 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="14b6b-126">앱을 게시할 때 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="14b6b-127">특정 런타임에 대해 게시: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="14b6b-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="14b6b-128">단일 파일로 게시: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="14b6b-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="14b6b-129">다음 예제에서는 Windows용 앱을 자체 포함 단일 파일 애플리케이션으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="14b6b-130">다음 예제에서는 Linux용 앱을 프레임워크 종속 단일 파일 애플리케이션으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="14b6b-131">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b6b-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="14b6b-132">단일 파일 앱 게시 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14b6b-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="14b6b-133">Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="14b6b-134">**솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="14b6b-135">**게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    <span data-ttu-id="14b6b-137">기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="14b6b-138">**편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. <span data-ttu-id="14b6b-140">**프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="14b6b-141">**배포 모드**를 **자체 포함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="14b6b-142">**대상 런타임**을 게시할 플랫폼으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="14b6b-143">**단일 파일 생성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="14b6b-144">**저장**을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="배포 모드, 대상 런타임, 단일 파일 옵션이 강조 표시된 프로필 설정 대화 상자":::

01. <span data-ttu-id="14b6b-146">**게시**를 선택하여 앱을 단일 파일로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="14b6b-147">자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b6b-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="14b6b-148">단일 파일 앱 게시 - Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14b6b-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="14b6b-149">Mac용 Visual Studio에서는 앱을 단일 파일로 게시하는 옵션을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="14b6b-150">[단일 파일 앱 게시 - CLI](#publish-a-single-file-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b6b-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="14b6b-151">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14b6b-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14b6b-152">참조</span><span class="sxs-lookup"><span data-stu-id="14b6b-152">See also</span></span>

- <span data-ttu-id="14b6b-153">[.NET Core 애플리케이션 배포](index.md).</span><span class="sxs-lookup"><span data-stu-id="14b6b-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="14b6b-154">[.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="14b6b-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="14b6b-155">[Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="14b6b-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="14b6b-156">[`dotnet publish` 명령](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="14b6b-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
