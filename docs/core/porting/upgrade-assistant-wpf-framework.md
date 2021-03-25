---
title: WPF 앱을 .NET 5로 업그레이드
description: .NET 업그레이드 도우미를 사용하여 기존 .NET Framework WPF 앱을 .NET 5로 업그레이드합니다. .NET 업그레이드 도우미는 .NET Framework에서 .NET 5로 앱을 마이그레이션하는 데 도움이 되는 CLI 도구입니다.
author: ardalis
ms.date: 03/08/2021
ms.openlocfilehash: b0c9baa25be6da4e7849f28c875a1d8f5f5a5d07
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604842"
---
# <a name="upgrade-a-wpf-app-to-net-5-with-the-net-upgrade-assistant"></a><span data-ttu-id="2c236-104">.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2c236-104">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>

<span data-ttu-id="2c236-105">[.NET 업그레이드 도우미](upgrade-assistant-overview.md)는 .NET Framework WPF 앱을 .NET 5로 업그레이드하는 데 도움이 될 수 있는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-105">The [.NET Upgrade Assistant](upgrade-assistant-overview.md) is a command-line tool that can assist with upgrading .NET Framework WPF apps to .NET 5.</span></span> <span data-ttu-id="2c236-106">이 문서에서는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-106">This article provides:</span></span>

- <span data-ttu-id="2c236-107">.NET Framework WPF 앱에 대해 도구를 실행하는 방법의 데모</span><span class="sxs-lookup"><span data-stu-id="2c236-107">A demonstration of how to run the tool against a .NET Framework WPF app</span></span>
- <span data-ttu-id="2c236-108">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="2c236-108">Troubleshooting tips</span></span>

## <a name="upgrade-net-framework-wpf-apps"></a><span data-ttu-id="2c236-109">.NET Framework WPF 앱 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2c236-109">Upgrade .NET Framework WPF apps</span></span>

<span data-ttu-id="2c236-110">이 섹션에서는 .NET Framework 4.6.1을 대상으로 하는 새로 만든 WPF 앱에 대해 .NET 업그레이드 도우미를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-110">This section demonstrates running the .NET Upgrade Assistant against a newly created WPF app targeting .NET Framework 4.6.1.</span></span> <span data-ttu-id="2c236-111">도구를 설치하는 방법에 관한 자세한 내용은 [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c236-111">For more information on how to install the tool, see [Overview of the .NET Upgrade Assistant](upgrade-assistant-overview.md).</span></span>

### <a name="initial-demo-setup"></a><span data-ttu-id="2c236-112">초기 데모 설정</span><span class="sxs-lookup"><span data-stu-id="2c236-112">Initial demo setup</span></span>

<span data-ttu-id="2c236-113">고유한 .NET Framework 앱에 대해 .NET 업그레이드 도우미를 실행하는 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-113">If you're running the .NET Upgrade Assistant against your own .NET Framework app, you can skip this step.</span></span> <span data-ttu-id="2c236-114">작동 방식만 확인해 보려는 경우 이 단계에서는 사용할 샘플 .NET WPF 프로젝트를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-114">If you just want to try it out to see how it works, this step shows you how to set up a sample .NET WPF project to use.</span></span>

<span data-ttu-id="2c236-115">Visual Studio를 사용하여 .NET Framework를 통해 새 WPF 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-115">Using Visual Studio, create a new WPF App using .NET Framework.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/new-project.png" alt-text="Visual Studio의 새 WPF 프로젝트":::

<span data-ttu-id="2c236-117">프로젝트 이름을 **WpfTest** 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-117">Name the project **WpfTest**.</span></span> <span data-ttu-id="2c236-118">**.NET Framework 4.6.1** 을 사용하도록 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-118">Configure the project to use **.NET Framework 4.6.1**.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/configure-project.png" alt-text="Visual Studio에서 Windows Forms 프로젝트 구성":::

<span data-ttu-id="2c236-120">만든 프로젝트와 해당 파일, 특히 해당 프로젝트 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-120">Review the created project and its files, especially its project file(s).</span></span>

### <a name="run-upgrade-assistant"></a><span data-ttu-id="2c236-121">upgrade-assistant 실행</span><span class="sxs-lookup"><span data-stu-id="2c236-121">Run upgrade-assistant</span></span>

<span data-ttu-id="2c236-122">터미널을 열고 대상 프로젝트 또는 솔루션이 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-122">Open a terminal and navigate to the folder where the target project or solution is located.</span></span> <span data-ttu-id="2c236-123">`upgrade-assistant` 명령을 실행하여 대상으로 지정할 프로젝트의 이름을 전달합니다(프로젝트 파일의 경로가 유효한 경우 어디서나 명령을 실행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="2c236-123">Run the `upgrade-assistant` command, passing in the name of the project you're targeting (you can run the command from anywhere, as long as the path to the project file is valid).</span></span>

```console
upgrade-assistant .\WpfTest.csproj
```

<span data-ttu-id="2c236-124">도구가 실행되고 수행할 단계 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-124">The tool runs and shows you a list of the steps it will do.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/initial-run.png" alt-text=".NET 업그레이드 도우미 초기 화면":::

<span data-ttu-id="2c236-126">각 단계가 완료되면 도구는 사용자가 다음 단계를 적용하거나 건너뛰거나, 추가 세부 정보를 확인하거나, 로깅을 구성하거나, 프로세스를 종료할 수 있도록 하는 명령 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-126">As each step is completed, the tool provides a set of commands allowing the user to apply or skip the next step, see more details, configure logging, or exit the process.</span></span> <span data-ttu-id="2c236-127">도구가 단계에서 작업을 수행하지 않을 것임을 감지하면 해당 단계를 자동으로 건너뛰고 수행할 작업이 있는 단계에 도달할 때까지 계속 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-127">If the tool detects that a step will perform no actions, it will automatically skip that step and continue to the next step until it reaches one that will have actions to perform.</span></span> <span data-ttu-id="2c236-128">Enter 키를 누르면 다른 항목이 선택되지 않은 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-128">Pressing enter will perform the next step if no other selection is made.</span></span>

<span data-ttu-id="2c236-129">이 예제에서는 매번 적용 단계가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-129">In this example, the apply step is chosen each time.</span></span> <span data-ttu-id="2c236-130">첫 번째 단계는 프로젝트를 백업하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-130">The first step is to back up the project.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/backup-project.png" alt-text=".NET 업그레이드 도우미 프로젝트 백업":::

<span data-ttu-id="2c236-132">도구는 백업을 위한 사용자 지정 경로를 입력하거나, 기본값을 사용하여 `.backup` 확장명을 사용하는 프로젝트 백업을 동일한 폴더에 배치할 것인지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-132">The tool prompts for a custom path for the backup, or to use the default, which will place the project backup in the same folder with a `.backup` extension.</span></span> <span data-ttu-id="2c236-133">도구가 수행하는 다음 단계는 프로젝트 파일을 SDK 스타일로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-133">The next step the tool performs is to convert the project file to SDK style.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/convert-project.png" alt-text=".NET 업그레이드 도우미 SDK 스타일로 프로젝트 변환":::

<span data-ttu-id="2c236-135">프로젝트 형식이 업데이트된 후 다음 단계는 프로젝트의 TFM을 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-135">Once the project format has been updated, the next step is to update the TFM of the project.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-tfm.png" alt-text=".NET 업그레이드 도우미 업데이트 TFM":::

<span data-ttu-id="2c236-137">그런 다음, 도구는 프로젝트의 NuGet 패키지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-137">Next, the tool updates the project's NuGet packages.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-nuget-packages.png" alt-text=".NET 업그레이드 도우미 NuGet 패키지 업데이트":::

<span data-ttu-id="2c236-139">패키지가 업데이트된 후 다음 단계는 템플릿 파일(있는 경우)을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-139">Once the packages are updated, the next step is to add template files, if any.</span></span> <span data-ttu-id="2c236-140">이 경우 추가해야 하는 템플릿 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-140">In this case, there are no template files that need to be added.</span></span> <span data-ttu-id="2c236-141">이 단계에서는 아래와 같이 계속해서 앱 구성 파일을 마이그레이션하고 C# 소스를 업데이트하여 수정 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-141">This step continues and migrates app config files and updates C# source to apply fixes, as shown below.</span></span> <span data-ttu-id="2c236-142">이 프로젝트에서는 구성 파일이나 소스 코드를 변경할 필요가 없으므로 해당 단계가 자동으로 진행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-142">This project didn't need any config file or source code changes, so these steps proceeded automatically.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/add-template-files.png" alt-text=".NET 업그레이드 도우미 템플릿 파일 추가 및 구성 마이그레이션":::

<span data-ttu-id="2c236-144">이는 마지막 프로젝트이므로, 다음 단계인 “다음 프로젝트로 이동”에서는 전체 솔루션을 마이그레이션하는 프로세스를 완료하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-144">Since this is the last project, the next step, "Move to next project", prompts to complete the process of migrating the entire solution.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/complete-solution.png" alt-text=".NET 업그레이드 도우미 솔루션 완료":::

<span data-ttu-id="2c236-146">이 프로세스가 완료된 후 마이그레이션된 WPF 프로젝트는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-146">Once this process has completed, the migrated WPF project will look something like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0-windows</TargetFramework>
    <OutputType>WinExe</OutputType>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <UseWPF>true</UseWPF>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
    <PackageReference Include="Microsoft.DotNet.UpgradeAssistant.Extensions.Default.Analyzers" Version="0.2.211942">
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="2c236-147">또한 .NET 업그레이드 도우미는 업그레이드 프로세스를 계속하는 데 도움이 되는 분석기를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-147">Notice that the .NET Upgrade Assistant also adds analyzers to the project that assist with continuing the upgrade process.</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="2c236-148">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="2c236-148">Troubleshooting tips</span></span>

<span data-ttu-id="2c236-149">.NET 업그레이드 도우미를 사용하는 경우 발생할 수 있는 여러 가지 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-149">There are several known problems that can occur when using the .NET Upgrade Assistant.</span></span> <span data-ttu-id="2c236-150">경우에 따라 해당 문제는 .NET 업그레이드 도우미가 내부적으로 사용하는 [try-convert 도구](https://github.com/dotnet/try-convert)와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-150">In some cases, these are problems with the [try-convert tool](https://github.com/dotnet/try-convert) that the .NET Upgrade Assistant uses internally.</span></span> <span data-ttu-id="2c236-151">해당 도구는 더 많은 시나리오를 해결하기 위해 자주 업데이트되므로 최신 버전을 사용하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c236-151">This tool is being frequently updated to address more scenarios, so make sure you're using a recent version.</span></span>

- <span data-ttu-id="2c236-152">try-convert 도구를 설치하고 _0.7.21201_ 버전 이상으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-152">The try-convert tool must be installed and updated to at least version _0.7.21201_.</span></span>
- <span data-ttu-id="2c236-153">이전 버전의 try-convert 도구는 사용자 지정 대상 또는 props 파일을 지원하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-153">Earlier versions of the try-convert tool didn't support custom target or props files.</span></span> <span data-ttu-id="2c236-154">최신 버전으로 업그레이드할 수 없는 경우 해당 문제를 수동으로 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-154">If you can't upgrade to the latest version, you may need to manually address these issues.</span></span> <span data-ttu-id="2c236-155">사용자 지정 대상 또는 props 파일에 대한 참조가 대상 프로젝트 파일에 포함된 경우 .NET 업그레이드 도우미가 실행되기 전에 해당 참조를 파일에서 수동으로 삭제해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-155">If the target project file includes references to custom targets or props files, these references may need to be manually deleted from the file before the .NET Upgrade Assistant is run against it.</span></span>

<span data-ttu-id="2c236-156">[도구의 GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues)에는 더 많은 문제 해결 팁과 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c236-156">[The tool's GitHub repository](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) has more troubleshooting tips and known issues.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c236-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c236-157">See also</span></span>

- [<span data-ttu-id="2c236-158">.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2c236-158">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="2c236-159">.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2c236-159">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-aspnetmvc.md)
- [<span data-ttu-id="2c236-160">.NET 업그레이드 도우미 개요</span><span class="sxs-lookup"><span data-stu-id="2c236-160">Overview of the .NET Upgrade Assistant</span></span>](upgrade-assistant-overview.md)
- [<span data-ttu-id="2c236-161">.NET 업그레이드 도우미 GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="2c236-161">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
