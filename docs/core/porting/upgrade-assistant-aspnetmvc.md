---
title: ASP.NET MVC 앱을 .NET 5로 업그레이드
description: .NET 업그레이드 도우미를 사용하여 기존 .NET Framework ASP.NET MVC 앱을 .NET 5로 업그레이드합니다. .NET 업그레이드 도우미는 .NET Framework에서 .NET 5로 앱을 마이그레이션하는 데 도움이 되는 CLI 도구입니다.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: 0c9af9e12b78df7c4a2aaed18155f7ee9f02870d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108360"
---
# <a name="upgrade-an-aspnet-mvc-app-to-net-5-with-the-net-upgrade-assistant"></a><span data-ttu-id="22a73-104">.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="22a73-104">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>

<span data-ttu-id="22a73-105">[.NET 업그레이드 도우미](upgrade-assistant-overview.md)는 .NET Framework ASP.NET MVC 앱을 .NET 5로 업그레이드하는 데 도움이 될 수 있는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-105">The [.NET Upgrade Assistant](upgrade-assistant-overview.md) is a command-line tool that can assist with upgrading .NET Framework ASP.NET MVC apps to .NET 5.</span></span> <span data-ttu-id="22a73-106">이 문서에서는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-106">This article provides:</span></span>

* <span data-ttu-id="22a73-107">.NET Framework ASP.NET MVC 앱에 대해 도구를 실행하는 방법의 데모</span><span class="sxs-lookup"><span data-stu-id="22a73-107">A demonstration of how to run the tool against a .NET Framework ASP.NET MVC app</span></span>
* <span data-ttu-id="22a73-108">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="22a73-108">Troubleshooting tips</span></span>

## <a name="upgrade-net-framework-aspnet-mvc-apps"></a><span data-ttu-id="22a73-109">.NET Framework ASP.NET MVC 앱 업그레이드</span><span class="sxs-lookup"><span data-stu-id="22a73-109">Upgrade .NET Framework ASP.NET MVC apps</span></span>

<span data-ttu-id="22a73-110">이 섹션에서는 .NET Framework 4.6.1을 대상으로 하는 새로 만든 ASP.NET MVC 앱에 대해 .NET 업그레이드 도우미를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-110">This section demonstrates running the .NET Upgrade Assistant against a newly created ASP.NET MVC app targeting .NET Framework 4.6.1.</span></span> <span data-ttu-id="22a73-111">도구를 설치하는 방법에 관한 자세한 내용은 [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22a73-111">For more information on how to install the tool, see [Overview of the .NET Upgrade Assistant](upgrade-assistant-overview.md).</span></span>

### <a name="initial-demo-setup"></a><span data-ttu-id="22a73-112">초기 데모 설정</span><span class="sxs-lookup"><span data-stu-id="22a73-112">Initial demo setup</span></span>

<span data-ttu-id="22a73-113">고유한 .NET Framework 앱에 대해 .NET 업그레이드 도우미를 실행하는 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-113">If you're running the .NET Upgrade Assistant against your own .NET Framework app, you can skip this step.</span></span> <span data-ttu-id="22a73-114">작동 방식만 확인하려는 경우 이 단계에서는 사용할 샘플 ASP.NET MVC 및 Web API(.NET Framework) 프로젝트를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-114">If you just want to try it out to see how it works, this step shows you how to set up a sample ASP.NET MVC and Web API (.NET Framework) project to use.</span></span>

<span data-ttu-id="22a73-115">Visual Studio를 사용하여 .NET Framework를 통해 새 ASP.NET 웹 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-115">Using Visual Studio, create a new ASP.NET Web Application project using .NET Framework.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/new-project.png" alt-text="Visual Studio의 새 ASP.NET 웹 애플리케이션 프로젝트":::

<span data-ttu-id="22a73-117">프로젝트 이름을 **AspNetMvcTest** 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-117">Name the project **AspNetMvcTest**.</span></span> <span data-ttu-id="22a73-118">**.NET Framework 4.6.1** 을 사용하도록 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-118">Configure the project to use **.NET Framework 4.6.1**.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/configure-project.png" alt-text="Visual Studio에서 ASP.NET 프로젝트 구성":::

<span data-ttu-id="22a73-120">다음 대화 상자에서 **MVC** 애플리케이션을 선택한 후 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-120">In the next dialog, choose **MVC** application, then select **Create**.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/create-mvc-webapi.png" alt-text="Visual Studio에서 ASP.NET MVC 프로젝트 만들기":::

<span data-ttu-id="22a73-122">만든 프로젝트와 해당 파일, 특히 해당 프로젝트 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-122">Review the created project and its files, especially its project file(s).</span></span>

### <a name="run-upgrade-assistant"></a><span data-ttu-id="22a73-123">upgrade-assistant 실행</span><span class="sxs-lookup"><span data-stu-id="22a73-123">Run upgrade-assistant</span></span>

<span data-ttu-id="22a73-124">터미널을 열고 대상 프로젝트 또는 솔루션이 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-124">Open a terminal and navigate to the folder where the target project or solution is located.</span></span> <span data-ttu-id="22a73-125">`upgrade-assistant` 명령을 실행하여 대상으로 지정할 프로젝트의 이름을 전달합니다(프로젝트 파일의 경로가 유효한 경우 어디서나 명령을 실행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="22a73-125">Run the `upgrade-assistant` command, passing in the name of the project you're targeting (you can run the command from anywhere, as long as the path to the project file is valid).</span></span>

```console
upgrade-assistant .\AspNetMvcTest.csproj
```

<span data-ttu-id="22a73-126">도구가 실행되고 수행할 단계 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-126">The tool runs and shows you a list of the steps it will do.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/initial-run.png" alt-text=".NET 업그레이드 도우미 초기 화면":::

<span data-ttu-id="22a73-128">각 단계가 완료되면 도구는 사용자가 다음 단계를 적용하거나 건너뛰거나, 추가 세부 정보를 확인하거나, 로깅을 구성하거나, 프로세스를 종료할 수 있도록 하는 명령 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-128">As each step is completed, the tool provides a set of commands allowing the user to apply or skip the next step, see more details, configure logging, or exit the process.</span></span> <span data-ttu-id="22a73-129">도구가 단계에서 작업을 수행하지 않을 것임을 감지하면 해당 단계를 자동으로 건너뛰고 수행할 작업이 있는 단계에 도달할 때까지 계속 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-129">If the tool detects that a step will perform no actions, it automatically skips that step and continues to the next step until it reaches one that has actions to perform.</span></span> <span data-ttu-id="22a73-130"><kbd>Enter</kbd> 키를 누르면 다른 항목이 선택되지 않은 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-130">Pressing <kbd>Enter</kbd> will perform the next step if no other selection is made.</span></span>

<span data-ttu-id="22a73-131">이 예제에서는 매번 적용 단계가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-131">In this example, the apply step is chosen each time.</span></span> <span data-ttu-id="22a73-132">첫 번째 단계는 프로젝트를 백업하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-132">The first step is to back up the project.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/backup-project.png" alt-text=".NET 업그레이드 도우미 프로젝트 백업":::

<span data-ttu-id="22a73-134">도구는 백업을 위한 사용자 지정 경로를 입력하거나, 기본값을 사용하여 `.backup` 확장명을 사용하는 프로젝트 백업을 동일한 폴더에 배치할 것인지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-134">The tool prompts for a custom path for the backup, or to use the default, which will place the project backup in the same folder with a `.backup` extension.</span></span> <span data-ttu-id="22a73-135">도구가 수행하는 다음 단계는 프로젝트 파일을 SDK 스타일로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-135">The next step the tool does is to convert the project file to SDK style.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/convert-project.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

<span data-ttu-id="22a73-137">프로젝트 형식이 업데이트된 후 다음 단계는 프로젝트의 TFM을 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-137">Once the project format has been updated, the next step is to update the TFM of the project.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-tfm.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

<span data-ttu-id="22a73-139">그런 다음, 도구는 프로젝트의 NuGet 패키지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-139">Next, the tool updates the project's NuGet packages.</span></span> <span data-ttu-id="22a73-140">여러 패키지에 업데이트가 필요하며 새 분석기 패키지가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-140">Several packages need updates, and a new analyzer package is added.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-nuget-packages.png" alt-text=".NET 업그레이드 도우미 NuGet 패키지 업데이트":::

<span data-ttu-id="22a73-142">패키지가 업데이트된 후 다음 단계는 템플릿 파일(있는 경우)을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-142">Once the packages are updated, the next step is to add template files, if any.</span></span> <span data-ttu-id="22a73-143">도구는 추가해야 하는 4개의 예상 템플릿 항목을 기록한 후 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-143">The tool notes there are four expected template items that must be added, and then adds them.</span></span> <span data-ttu-id="22a73-144">해당 항목에는 다음 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-144">These include the following files:</span></span>

- `Program.cs`
- `Startup.cs`
- `appsettings.json`
- `appsettings.Development.json`

<span data-ttu-id="22a73-145">해당 파일은 ASP.NET Core에서 [앱 시작](/aspnet/core/fundamentals/startup) 및 [구성](/aspnet/core/fundamentals/configuration)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-145">These files are used by ASP.NET Core for [app startup](/aspnet/core/fundamentals/startup) and [configuration](/aspnet/core/fundamentals/configuration).</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/add-template-files.png" alt-text=".NET 업그레이드 도우미 템플릿 파일 추가":::

<span data-ttu-id="22a73-147">그런 다음, 도구는 구성 파일을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-147">Next, the tool migrates config files.</span></span> <span data-ttu-id="22a73-148">도구는 앱 설정을 식별하고 지원되지 않는 구성 섹션을 사용하지 않도록 설정한 다음, `appSettings` 구성 값을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-148">The tool identifies app settings and disables unsupported configuration sections, then migrates the `appSettings` configuration values.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config.png" alt-text=".NET 업그레이드 도우미 구성 마이그레이션":::

<span data-ttu-id="22a73-150">도구는 `system.web.webPages.razor/pages/namespaces`를 마이그레이션하여 구성 파일의 마이그레이션을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-150">The tool completes the migration of config files by migrating `system.web.webPages.razor/pages/namespaces`.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config2.png" alt-text=".NET 업그레이드 도우미 구성 마이그레이션":::

<span data-ttu-id="22a73-152">도구는 알려진 수정 사항을 적용하여 C# 참조를 새 대응 항목으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-152">The tool applies known fixes to migrate C# references to their new counterparts.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-csharp.png" alt-text=".NET 업그레이드 도우미 C# 소스 업데이트":::

<span data-ttu-id="22a73-154">이는 마지막 프로젝트이므로, 다음 단계인 “다음 프로젝트로 이동”에서는 전체 솔루션을 마이그레이션하는 프로세스를 완료하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-154">Since this is the last project, the next step, "Move to next project", prompts to complete the process of migrating the entire solution.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/complete-solution.png" alt-text=".NET 업그레이드 도우미 솔루션 완료":::

<span data-ttu-id="22a73-156">해당 프로세스가 완료된 후 프로젝트 파일을 열고 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-156">Once this process has completed, open the project file and review it.</span></span> <span data-ttu-id="22a73-157">다음과 같은 정적 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-157">Look for static files like these:</span></span>

```xml
  <ItemGroup>
    <Content Include="fonts\glyphicons-halflings-regular.woff2" />
    <Content Include="fonts\glyphicons-halflings-regular.woff" />
    <Content Include="fonts\glyphicons-halflings-regular.ttf" />
    <Content Include="fonts\glyphicons-halflings-regular.eot" />
    <Content Include="Content\bootstrap.min.css.map" />
    <Content Include="Content\bootstrap.css.map" />
    <Content Include="Content\bootstrap-theme.min.css.map" />
    <Content Include="Content\bootstrap-theme.css.map" />
    <Content Include="Scripts\jquery-3.4.1.slim.min.map" />
    <Content Include="Scripts\jquery-3.4.1.min.map" />
  </ItemGroup>
```

<span data-ttu-id="22a73-158">웹 서버에서 제공해야 하는 정적 파일은 `wwwroot`라는 루트 수준 폴더 내의 적절한 폴더로 이동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-158">Static files that should be served by the web server should be moved to an appropriate folder within a root level folder named `wwwroot`.</span></span> <span data-ttu-id="22a73-159">자세한 내용은 [ASP.NET Core의 정적 파일](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22a73-159">See [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0) for details.</span></span> <span data-ttu-id="22a73-160">파일이 이동된 후에는 이 파일에 해당하는 프로젝트 파일의 `<Content>` 요소가 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-160">Once the files have been moved, the `<Content>` elements in the project file corresponding to these files can be deleted.</span></span> <span data-ttu-id="22a73-161">실제로 모든 `<Content>` 요소와 포함하는 그룹이 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-161">In fact, all `<Content>` elements and their containing groups can be removed.</span></span> <span data-ttu-id="22a73-162">또한 `bootstrap` 또는 `jQuery`와 같은 클라이언트 쪽 라이브러리에 대한 `<PackageReference>`가 제거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-162">Also, any `<PackageReference>` to a client-side library like `bootstrap` or `jQuery` should be removed.</span></span>

<span data-ttu-id="22a73-163">기본적으로 프로젝트는 클래스 라이브러리로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-163">By default, the project will be converted as a class library.</span></span> <span data-ttu-id="22a73-164">첫 번째 줄의 `Sdk` 특성을 `Microsoft.NET.Sdk.Web`으로 변경하고 `<TargetFramework>`를 `net5.0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-164">Change the first line's `Sdk` attribute to `Microsoft.NET.Sdk.Web` and set the `<TargetFramework>` to `net5.0`.</span></span> <span data-ttu-id="22a73-165">프로젝트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-165">Compile the project.</span></span> <span data-ttu-id="22a73-166">이때 오류 수는 상당히 적습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-166">At this point, the number of errors should be fairly small.</span></span> <span data-ttu-id="22a73-167">새 ASP.NET 4.6.1 MVC 프로젝트를 이동할 때 나머지 오류는 `App_Start` 폴더의 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-167">When porting a new ASP.NET 4.6.1 MVC project, the remaining errors refer to files in the `App_Start` folder:</span></span>

- <span data-ttu-id="22a73-168">BundleConfig.cs</span><span class="sxs-lookup"><span data-stu-id="22a73-168">BundleConfig.cs</span></span>
- <span data-ttu-id="22a73-169">FilterConfig.cs</span><span class="sxs-lookup"><span data-stu-id="22a73-169">FilterConfig.cs</span></span>
- <span data-ttu-id="22a73-170">RouteConfig.cs</span><span class="sxs-lookup"><span data-stu-id="22a73-170">RouteConfig.cs</span></span>

<span data-ttu-id="22a73-171">해당 파일과 전체 `App_Start` 폴더가 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-171">These files - and the entire `App_Start` folder - can be deleted.</span></span> <span data-ttu-id="22a73-172">마찬가지로 `Global.asax` 및 `Global.asax.cs` 파일도 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-172">Likewise, the `Global.asax` and `Global.asax.cs` files can be removed.</span></span>

<span data-ttu-id="22a73-173">이때 남아 있는 오류만 묶음과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-173">At this point the only errors that remain are related to bundling.</span></span> <span data-ttu-id="22a73-174">[ASP.NET Core에서 묶음 및 축소를 구성하는 여러 가지 방법](/aspnet/core/migration/mvc?view=aspnetcore-5.0#configure-bundling-and-minification)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-174">There are [several ways to configure bundling and minification in ASP.NET Core](/aspnet/core/migration/mvc?view=aspnetcore-5.0#configure-bundling-and-minification).</span></span> <span data-ttu-id="22a73-175">프로젝트에 가장 적합한 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-175">Choose whatever makes the most sense for your project.</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="22a73-176">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="22a73-176">Troubleshooting tips</span></span>

<span data-ttu-id="22a73-177">.NET 업그레이드 도우미를 사용하는 경우 발생할 수 있는 여러 가지 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-177">There are several known problems that can occur when using the .NET Upgrade Assistant.</span></span> <span data-ttu-id="22a73-178">경우에 따라 해당 문제는 .NET 업그레이드 도우미가 내부적으로 사용하는 [try-convert 도구](https://github.com/dotnet/try-convert)와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-178">In some cases, these are problems with the [try-convert tool](https://github.com/dotnet/try-convert) that the .NET Upgrade Assistant uses internally.</span></span> <span data-ttu-id="22a73-179">해당 도구는 더 많은 시나리오를 해결하기 위해 자주 업데이트되므로 최신 버전을 사용하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="22a73-179">This tool is being frequently updated to address more scenarios, so make sure you're using a recent version.</span></span>

- <span data-ttu-id="22a73-180">**try-convert** 도구를 설치하고 _0.7.212201_ 버전 이상으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-180">The **try-convert** tool must be installed and updated to at least version _0.7.212201_.</span></span>
- <span data-ttu-id="22a73-181">이전 버전의 **try-convert** 도구는 사용자 지정 대상 또는 props 파일을 지원하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-181">Earlier versions of the **try-convert** tool didn't support custom target or props files.</span></span> <span data-ttu-id="22a73-182">최신 버전으로 업그레이드할 수 없는 경우 해당 문제를 수동으로 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-182">If you can't upgrade to the latest version, you may need to manually address these issues.</span></span> <span data-ttu-id="22a73-183">사용자 지정 대상 또는 props 파일에 대한 참조가 대상 프로젝트 파일에 포함된 경우 .NET 업그레이드 도우미가 실행되기 전에 해당 참조를 파일에서 수동으로 삭제해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-183">If the target project file includes references to custom targets or props files, these references may need to be manually deleted from the file before the .NET Upgrade Assistant is run against it.</span></span>

```xml
<Import Project="packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props" Condition="Exists('packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props')" />
```

<span data-ttu-id="22a73-184">[도구의 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues)에는 더 많은 문제 해결 팁과 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22a73-184">[The tool's GitHub repository](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) has more troubleshooting tips and known issues.</span></span>

## <a name="see-also"></a><span data-ttu-id="22a73-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22a73-185">See also</span></span>

- [<span data-ttu-id="22a73-186">.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="22a73-186">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-wpf-framework.md)
- [<span data-ttu-id="22a73-187">.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="22a73-187">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="22a73-188">.NET 업그레이드 도우미 개요</span><span class="sxs-lookup"><span data-stu-id="22a73-188">Overview of the .NET Upgrade Assistant</span></span>](upgrade-assistant-overview.md)
- [<span data-ttu-id="22a73-189">.NET 업그레이드 도우미 GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="22a73-189">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
