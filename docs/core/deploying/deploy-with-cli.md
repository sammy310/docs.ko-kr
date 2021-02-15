---
title: .NET CLI를 사용하여 앱 게시
description: .NET CLI 명령을 사용하여 .NET 애플리케이션을 게시하는 방법을 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 02/05/2021
dev_langs:
- csharp
- vb
ms.openlocfilehash: af2198360670360f94f7fdf30d2890bc7dfd436d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773864"
---
# <a name="publish-net-apps-with-the-net-cli"></a><span data-ttu-id="9aee4-103">.NET CLI를 사용하여 .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="9aee4-103">Publish .NET apps with the .NET CLI</span></span>

<span data-ttu-id="9aee4-104">이 문서에서는 명령줄에서 .NET 애플리케이션을 게시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-104">This article demonstrates how you can publish your .NET application from the command line.</span></span> <span data-ttu-id="9aee4-105">.NET은 애플리케이션을 게시하는 세 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-105">.NET provides three ways to publish your applications.</span></span> <span data-ttu-id="9aee4-106">프레임워크 종속 배포는 로컬에 설치된 .NET 런타임을 사용하는 플랫폼 간 .dll 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-106">Framework-dependent deployment produces a cross-platform .dll file that uses the locally installed .NET runtime.</span></span> <span data-ttu-id="9aee4-107">프레임워크 종속 실행 파일은 로컬에 설치된 .NET 런타임을 사용하는 플랫폼별 실행 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-107">Framework-dependent executable produces a platform-specific executable that uses the locally installed .NET runtime.</span></span> <span data-ttu-id="9aee4-108">자체 포함 실행 파일은 플랫폼별 실행 파일을 생성하고 .NET 런타임의 로컬 복사본을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-108">Self-contained executable produces a platform-specific executable and includes a local copy of the .NET runtime.</span></span>

<span data-ttu-id="9aee4-109">이러한 게시 모드에 대한 개요는 [.NET 애플리케이션 배포](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-109">For an overview of these publishing modes, see [.NET Application Deployment](index.md).</span></span>

<span data-ttu-id="9aee4-110">CLI 사용에 대한 빠른 도움말을 찾나요?</span><span class="sxs-lookup"><span data-stu-id="9aee4-110">Looking for some quick help on using the CLI?</span></span> <span data-ttu-id="9aee4-111">다음 표는 앱을 게시하는 방법의 몇 가지 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-111">The following table shows some examples of how to publish your app.</span></span> <span data-ttu-id="9aee4-112">`-f <TFM>` 매개 변수를 사용하거나 프로젝트 파일을 편집하여 대상 프레임워크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-112">You can specify the target framework with the `-f <TFM>` parameter or by editing the project file.</span></span> <span data-ttu-id="9aee4-113">자세한 내용은 [기본 사항 게시](#publishing-basics)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-113">For more information, see [Publishing basics](#publishing-basics).</span></span>

| <span data-ttu-id="9aee4-114">게시 모드</span><span class="sxs-lookup"><span data-stu-id="9aee4-114">Publish Mode</span></span>                   | <span data-ttu-id="9aee4-115">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="9aee4-115">SDK Version</span></span> | <span data-ttu-id="9aee4-116">명령</span><span class="sxs-lookup"><span data-stu-id="9aee4-116">Command</span></span>                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| [<span data-ttu-id="9aee4-117">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-117">Framework-dependent deployment</span></span>](#framework-dependent-deployment) | <span data-ttu-id="9aee4-118">2.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-118">2.1</span></span>         | `dotnet publish -c Release`                                 |
|                                | <span data-ttu-id="9aee4-119">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-119">3.1</span></span>         | `dotnet publish -c Release -p:UseAppHost=false`             |
|                                | <span data-ttu-id="9aee4-120">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-120">5.0</span></span>         | `dotnet publish -c Release -p:UseAppHost=false`             |
| [<span data-ttu-id="9aee4-121">프레임워크 종속 실행 파일</span><span class="sxs-lookup"><span data-stu-id="9aee4-121">Framework-dependent executable</span></span>](#framework-dependent-executable) | <span data-ttu-id="9aee4-122">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-122">3.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
|                                | <span data-ttu-id="9aee4-123">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-123">5.0</span></span>         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
| [<span data-ttu-id="9aee4-124">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-124">Self-contained deployment</span></span>](#self-contained-deployment)      | <span data-ttu-id="9aee4-125">2.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-125">2.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | <span data-ttu-id="9aee4-126">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-126">3.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | <span data-ttu-id="9aee4-127">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-127">5.0</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |

<span data-ttu-id="9aee4-128">\* **SDK 버전 3.1** 이상을 사용할 경우 프레임워크 종속 실행 파일은 기본 `dotnet publish` 명령을 실행할 때 기본 게시 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-128">\* When using **SDK version 3.1** or higher, framework-dependent executable is the default publishing mode when running the basic `dotnet publish` command.</span></span>

> [!NOTE]
> <span data-ttu-id="9aee4-129">`-c Release` 매개 변수는 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-129">The `-c Release` parameter isn't required.</span></span> <span data-ttu-id="9aee4-130">앱의 **릴리스** 빌드를 게시하는 미리 알림으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-130">It's provided as a reminder to publish the **Release** build of your app.</span></span>

## <a name="publishing-basics"></a><span data-ttu-id="9aee4-131">게시 기본 사항</span><span class="sxs-lookup"><span data-stu-id="9aee4-131">Publishing basics</span></span>

<span data-ttu-id="9aee4-132">프로젝트 파일의 `<TargetFramework>` 설정은 앱을 게시할 때 기본 대상 프레임워크를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-132">The `<TargetFramework>` setting of the project file specifies the default target framework when you publish your app.</span></span> <span data-ttu-id="9aee4-133">대상 프레임워크를 유효한 [TFM(대상 프레임워크 모니커)](../../standard/frameworks.md)으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-133">You can change the target framework to any valid [Target Framework Moniker (TFM)](../../standard/frameworks.md).</span></span> <span data-ttu-id="9aee4-134">예를 들어 프로젝트에서 `<TargetFramework>netcoreapp2.1</TargetFramework>`를 사용하는 경우 .NET Core 2.1을 대상으로 하는 이진 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-134">For example, if your project uses `<TargetFramework>netcoreapp2.1</TargetFramework>`, a binary that targets .NET Core 2.1 is created.</span></span> <span data-ttu-id="9aee4-135">이 설정에 지정된 TFM은 [`dotnet publish`](../tools/dotnet-publish.md) 명령에서 사용되는 기본 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-135">The TFM specified in this setting is the default target used by the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="9aee4-136">둘 이상의 프레임워크를 대상으로 하려는 경우 `<TargetFrameworks>` 설정을 세미콜론으로 구분된 여러 TFM 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-136">If you want to target more than one framework, you can set the `<TargetFrameworks>` setting to multiple TFM values, separated by a semicolon.</span></span> <span data-ttu-id="9aee4-137">앱을 빌드하면 각 대상 프레임워크에 대해 빌드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-137">When you build your app, a build is produced for each target framework.</span></span> <span data-ttu-id="9aee4-138">그러나 앱을 게시할 때 `dotnet publish -f <TFM>` 명령을 사용하여 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-138">However, when you publish your app, you must specify the target framework with the `dotnet publish -f <TFM>` command.</span></span>

<span data-ttu-id="9aee4-139">달리 설정하지 않으면 [`dotnet publish`](../tools/dotnet-publish.md) 명령의 출력 디렉터리는 `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-139">Unless otherwise set, the output directory of the [`dotnet publish`](../tools/dotnet-publish.md) command is `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`.</span></span> <span data-ttu-id="9aee4-140">`-c` 매개 변수를 사용하여 변경하지 않는 한 기본 **BUILD-CONFIGURATION** 모드는 **디버그** 입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-140">The default **BUILD-CONFIGURATION** mode is **Debug** unless changed with the `-c` parameter.</span></span> <span data-ttu-id="9aee4-141">예를 들어 `dotnet publish -c Release -f netcoreapp2.1`은 `./bin/Release/netcoreapp2.1/publish/`에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-141">For example, `dotnet publish -c Release -f netcoreapp2.1` publishes to `./bin/Release/netcoreapp2.1/publish/`.</span></span>

<span data-ttu-id="9aee4-142">.NET Core SDK 3.1 이상을 사용하는 경우 기본 게시 모드는 프레임워크 종속 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-142">If you use .NET Core SDK 3.1 or later, the default publish mode is framework-dependent _executable_.</span></span>

<span data-ttu-id="9aee4-143">.NET Core SDK 2.1을 사용하는 경우 기본 게시 모드는 프레임워크 종속 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-143">If you use .NET Core SDK 2.1, the default publish mode is framework-dependent _deployment_.</span></span>

### <a name="native-dependencies"></a><span data-ttu-id="9aee4-144">네이티브 종속성</span><span class="sxs-lookup"><span data-stu-id="9aee4-144">Native dependencies</span></span>

<span data-ttu-id="9aee4-145">앱에 네이티브 종속성이 있는 경우 다른 운영 체제에서 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-145">If your app has native dependencies, it may not run on a different operating system.</span></span> <span data-ttu-id="9aee4-146">예를 들어 앱이 네이티브 Windows API를 사용하는 경우 macOS 또는 Linux에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-146">For example, if your app uses the native Windows API, it won't run on macOS or Linux.</span></span> <span data-ttu-id="9aee4-147">플랫폼별 코드를 제공하고 각 플랫폼에 대해 실행 파일을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-147">You would need to provide platform-specific code and compile an executable for each platform.</span></span>

<span data-ttu-id="9aee4-148">또한 참조한 라이브러리에 네이티브 종속성이 있는 경우 모든 플랫폼에서 앱이 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-148">Consider also, if a library you referenced has a native dependency, your app may not run on every platform.</span></span> <span data-ttu-id="9aee4-149">그러나 참조하는 NuGet 패키지에 플랫폼별 버전이 포함되어 있어 사용자의 필수 네이티브 종속성을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-149">However, it's possible a NuGet package you're referencing has included platform-specific versions to handle the required native dependencies for you.</span></span>

<span data-ttu-id="9aee4-150">네이티브 종속성이 있는 앱을 배포할 때 `dotnet publish -r <RID>` 스위치를 사용하여 게시할 대상 플랫폼을 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-150">When distributing an app with native dependencies, you may need to use the `dotnet publish -r <RID>` switch to specify the target platform you want to publish for.</span></span> <span data-ttu-id="9aee4-151">런타임 식별자 목록은 [런타임 식별자(RID) 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-151">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

<span data-ttu-id="9aee4-152">플랫폼별 이진 파일에 대한 자세한 내용은 [프레임워크 종속 실행 파일](#framework-dependent-executable) 및 [자체 포함 배포](#self-contained-deployment) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-152">More information about platform-specific binaries is covered in the [Framework-dependent executable](#framework-dependent-executable) and [Self-contained deployment](#self-contained-deployment) sections.</span></span>

## <a name="sample-app"></a><span data-ttu-id="9aee4-153">샘플 앱</span><span class="sxs-lookup"><span data-stu-id="9aee4-153">Sample app</span></span>

<span data-ttu-id="9aee4-154">다음 앱을 사용하여 게시 명령을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-154">You can use the following app to explore the publishing commands.</span></span> <span data-ttu-id="9aee4-155">이 앱은 터미널에서 다음 명령을 실행하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-155">The app is created by running the following commands in your terminal:</span></span>

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

<span data-ttu-id="9aee4-156">콘솔 템플릿에 의해 생성된 `Program.cs` 또는 `Program.vb` 파일을 다음과 같이 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-156">The `Program.cs` or `Program.vb` file that is generated by the console template needs to be changed to the following:</span></span>

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```

```vb
Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

<span data-ttu-id="9aee4-157">앱([`dotnet run`](../tools/dotnet-run.md))을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-157">When you run the app ([`dotnet run`](../tools/dotnet-run.md)), the following output is displayed:</span></span>

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a><span data-ttu-id="9aee4-158">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-158">Framework-dependent deployment</span></span>

<span data-ttu-id="9aee4-159">.NET Core 2.1 SDK CLI의 경우 FDD(프레임워크 종속 배포)가 기본 `dotnet publish` 명령의 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-159">For the .NET Core 2.1 SDK CLI, framework-dependent deployment (FDD) is the default mode for the basic `dotnet publish` command.</span></span> <span data-ttu-id="9aee4-160">더 최신 SDK에서는 [프레임워크 종속 실행 파일](#framework-dependent-executable)이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-160">In newer SDKs, [Framework-dependent executable](#framework-dependent-executable) is the default.</span></span>

<span data-ttu-id="9aee4-161">앱을 FDD로 게시하면 `<PROJECT-NAME>.dll` 파일이 `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/` 폴더에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-161">When you publish your app as an FDD, a `<PROJECT-NAME>.dll` file is created in the `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/` folder.</span></span> <span data-ttu-id="9aee4-162">앱을 실행하려면 출력 폴더로 이동하여 `dotnet <PROJECT-NAME>.dll` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-162">To run your app, navigate to the output folder and use the `dotnet <PROJECT-NAME>.dll` command.</span></span>

<span data-ttu-id="9aee4-163">앱이 특정 버전의 .NET을 대상으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-163">Your app is configured to target a specific version of .NET.</span></span> <span data-ttu-id="9aee4-164">대상으로 하는 .NET 런타임이 앱을 실행하는 컴퓨터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-164">That targeted .NET runtime is required to be on any machine where your app runs.</span></span> <span data-ttu-id="9aee4-165">예를 들어 앱이 .NET Core 3.1을 대상으로 하는 경우, 앱이 실행 되는 모든 머신에 .NET Core 3.1 런타임이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-165">For example, if your app targets .NET Core 3.1, any machine that your app runs on must have the .NET Core 3.1 runtime installed.</span></span> <span data-ttu-id="9aee4-166">[기본 사항 게시](#publishing-basics) 섹션에서 설명된 대로 프로젝트 파일을 편집하여 기본 대상 프레임워크를 변경하거나 둘 이상의 프레임워크를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-166">As stated in the [Publishing basics](#publishing-basics) section, you can edit your project file to change the default target framework or to target more than one framework.</span></span>

<span data-ttu-id="9aee4-167">FDD를 게시하면 앱을 실행하는 시스템에서 사용할 수 있는 최신 .NET 보안 패치로 자동으로 롤포워드하는 앱이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-167">Publishing an FDD creates an app that automatically rolls-forward to the latest .NET security patch available on the system that runs the app.</span></span> <span data-ttu-id="9aee4-168">컴파일 시 버전 바인딩에 대한 자세한 내용은 [사용할 .NET 버전 선택](../versions/selection.md#framework-dependent-apps-roll-forward)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-168">For more information on version binding at compile time, see [Select the .NET version to use](../versions/selection.md#framework-dependent-apps-roll-forward).</span></span>

| <span data-ttu-id="9aee4-169">게시 모드</span><span class="sxs-lookup"><span data-stu-id="9aee4-169">Publish Mode</span></span>                   | <span data-ttu-id="9aee4-170">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="9aee4-170">SDK Version</span></span> | <span data-ttu-id="9aee4-171">명령</span><span class="sxs-lookup"><span data-stu-id="9aee4-171">Command</span></span>                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| <span data-ttu-id="9aee4-172">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-172">Framework-dependent deployment</span></span> | <span data-ttu-id="9aee4-173">2.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-173">2.1</span></span>         | `dotnet publish -c Release`                                 |
|                                | <span data-ttu-id="9aee4-174">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-174">3.1</span></span>         | `dotnet publish -c Release -p:UseAppHost=false`             |
|                                | <span data-ttu-id="9aee4-175">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-175">5.0</span></span>         | `dotnet publish -c Release -p:UseAppHost=false`             |

## <a name="framework-dependent-executable"></a><span data-ttu-id="9aee4-176">프레임워크 종속 실행 파일</span><span class="sxs-lookup"><span data-stu-id="9aee4-176">Framework-dependent executable</span></span>

<span data-ttu-id="9aee4-177">.NET 5(및 .NET Core 3.1) SDK CLI의 경우 FDE(프레임워크 종속 실행 파일)가 기본 `dotnet publish` 명령의 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-177">For the .NET 5 (and .NET Core 3.1) SDK CLI, framework-dependent executable (FDE) is the default mode for the basic `dotnet publish` command.</span></span> <span data-ttu-id="9aee4-178">현재 운영 체제를 대상으로 하는 한 다른 매개 변수를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-178">You don't need to specify any other parameters, as long as you want to target the current operating system.</span></span>

<span data-ttu-id="9aee4-179">이 모드에서는 플랫폼별 실행 파일 호스트가 만들어져 플랫폼 간 앱을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-179">In this mode, a platform-specific executable host is created to host your cross-platform app.</span></span> <span data-ttu-id="9aee4-180">이 모드는 FDD에 `dotnet` 명령 형식의 호스트가 필요함으로 FDD와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-180">This mode is similar to FDD, as FDD requires a host in the form of the `dotnet` command.</span></span> <span data-ttu-id="9aee4-181">호스트 실행 파일 이름은 플랫폼마다 다르며 `<PROJECT-FILE>.exe`와 유사한 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-181">The host executable filename varies per platform and is named something similar to `<PROJECT-FILE>.exe`.</span></span> <span data-ttu-id="9aee4-182">`dotnet <PROJECT-FILE>.dll`을 호출하는 대신 이 실행 파일을 직접 실행하여 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-182">You can run this executable directly instead of calling `dotnet <PROJECT-FILE>.dll`, which is still an acceptable way to run the app.</span></span>

<span data-ttu-id="9aee4-183">앱이 특정 버전의 .NET을 대상으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-183">Your app is configured to target a specific version of .NET.</span></span> <span data-ttu-id="9aee4-184">대상으로 하는 .NET 런타임이 앱을 실행하는 컴퓨터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-184">That targeted .NET runtime is required to be on any machine where your app runs.</span></span> <span data-ttu-id="9aee4-185">예를 들어 앱이 .NET Core 3.1을 대상으로 하는 경우, 앱이 실행 되는 모든 머신에 .NET Core 3.1 런타임이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-185">For example, if your app targets .NET Core 3.1, any machine that your app runs on must have the .NET Core 3.1 runtime installed.</span></span> <span data-ttu-id="9aee4-186">[기본 사항 게시](#publishing-basics) 섹션에서 설명된 대로 프로젝트 파일을 편집하여 기본 대상 프레임워크를 변경하거나 둘 이상의 프레임워크를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-186">As stated in the [Publishing basics](#publishing-basics) section, you can edit your project file to change the default target framework or to target more than one framework.</span></span>

<span data-ttu-id="9aee4-187">FDE를 게시하면 앱을 실행하는 시스템에서 사용할 수 있는 최신 .NET 보안 패치로 자동으로 롤포워드하는 앱이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-187">Publishing an FDE creates an app that automatically rolls-forward to the latest .NET security patch available on the system that runs the app.</span></span> <span data-ttu-id="9aee4-188">컴파일 시 버전 바인딩에 대한 자세한 내용은 [사용할 .NET 버전 선택](../versions/selection.md#framework-dependent-apps-roll-forward)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-188">For more information on version binding at compile time, see [Select the .NET version to use](../versions/selection.md#framework-dependent-apps-roll-forward).</span></span>

<span data-ttu-id="9aee4-189">.NET 2.1의 경우 FDE를 게시하려면 `dotnet publish` 명령과 함께 다음 스위치를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-189">For .NET 2.1, you must use the following switches with the `dotnet publish` command to publish an FDE:</span></span>

- <span data-ttu-id="9aee4-190">`-r <RID>` 이 스위치는 식별자(RID)를 사용하여 대상 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-190">`-r <RID>` This switch uses an identifier (RID) to specify the target platform.</span></span> <span data-ttu-id="9aee4-191">런타임 식별자 목록은 [런타임 식별자(RID) 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-191">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

- <span data-ttu-id="9aee4-192">`--self-contained false` 이 스위치는 .NET Core SDK에 실행 파일을 FDE로 생성하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-192">`--self-contained false` This switch tells the .NET Core SDK to create an executable as an FDE.</span></span>

| <span data-ttu-id="9aee4-193">게시 모드</span><span class="sxs-lookup"><span data-stu-id="9aee4-193">Publish Mode</span></span>                   | <span data-ttu-id="9aee4-194">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="9aee4-194">SDK Version</span></span> | <span data-ttu-id="9aee4-195">명령</span><span class="sxs-lookup"><span data-stu-id="9aee4-195">Command</span></span>                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| <span data-ttu-id="9aee4-196">프레임워크 종속 실행 파일</span><span class="sxs-lookup"><span data-stu-id="9aee4-196">Framework-dependent executable</span></span> | <span data-ttu-id="9aee4-197">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-197">3.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
|                                | <span data-ttu-id="9aee4-198">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-198">5.0</span></span>         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |

<span data-ttu-id="9aee4-199">`-r` 스위치를 사용할 때마다 출력 폴더 경로가 `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-199">Whenever you use the `-r` switch, the output folder path changes to: `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`</span></span>

<span data-ttu-id="9aee4-200">[예제 앱](#sample-app)을 사용하는 경우 `dotnet publish -f net5.0 -r win10-x64 --self-contained false`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-200">If you use the [example app](#sample-app), run `dotnet publish -f net5.0 -r win10-x64 --self-contained false`.</span></span> <span data-ttu-id="9aee4-201">이 명령은 `./bin/Debug/net5.0/win10-x64/publish/apptest1.exe` 실행 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-201">This command creates the following executable: `./bin/Debug/net5.0/win10-x64/publish/apptest1.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="9aee4-202">**세계화 고정 모드** 를 사용하여 배포의 전체 크기를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-202">You can reduce the total size of your deployment by enabling **globalization invariant mode**.</span></span> <span data-ttu-id="9aee4-203">이 모드는 전역적으로 인식되지 않는 서식 지정 규칙, 대/소문자 규칙 및 문자열 비교와 [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture)의 정렬 순서를 사용할 수 있는 애플리케이션에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-203">This mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span> <span data-ttu-id="9aee4-204">**세계화 고정 모드** 와 이 모드를 사용하는 방법에 대한 자세한 내용은 [.NET 세계화 고정 모드](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-204">For more information about **globalization invariant mode** and how to enable it, see [.NET Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

## <a name="self-contained-deployment"></a><span data-ttu-id="9aee4-205">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-205">Self-contained deployment</span></span>

<span data-ttu-id="9aee4-206">SCD(자체 포함 배포)를 게시하면 .NET SDK는 플랫폼별 실행 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-206">When you publish a self-contained deployment (SCD), the .NET SDK creates a platform-specific executable.</span></span> <span data-ttu-id="9aee4-207">SCD 게시에는 앱을 실행하는 데 필요한 모든 .NET 파일이 포함되지만, [.NET의 네이티브 종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-207">Publishing an SCD includes all required .NET files to run your app but it doesn't include the [native dependencies of .NET](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span> <span data-ttu-id="9aee4-208">이러한 종속성은 앱을 실행하기 전에 시스템에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-208">These dependencies must be present on the system before the app runs.</span></span>

<span data-ttu-id="9aee4-209">SCD를 게시하면 사용 가능한 최신 .NET 보안 패치로 롤포워드되지 않는 앱이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-209">Publishing an SCD creates an app that doesn't roll forward to the latest available .NET security patch.</span></span> <span data-ttu-id="9aee4-210">컴파일 시 버전 바인딩에 대한 자세한 내용은 [사용할 .NET 버전 선택](../versions/selection.md#self-contained-deployments-include-the-selected-runtime)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-210">For more information on version binding at compile time, see [Select the .NET version to use](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).</span></span>

<span data-ttu-id="9aee4-211">SCD를 게시하려면 `dotnet publish` 명령과 함께 다음 스위치를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-211">You must use the following switches with the `dotnet publish` command to publish an SCD:</span></span>

- <span data-ttu-id="9aee4-212">`-r <RID>` 이 스위치는 식별자(RID)를 사용하여 대상 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-212">`-r <RID>` This switch uses an identifier (RID) to specify the target platform.</span></span> <span data-ttu-id="9aee4-213">런타임 식별자 목록은 [런타임 식별자(RID) 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-213">For a list of runtime identifiers, see [Runtime Identifier (RID) catalog](../rid-catalog.md).</span></span>

- <span data-ttu-id="9aee4-214">`--self-contained true` 이 스위치는 .NET Core SDK에 실행 파일을 SCD로 생성하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-214">`--self-contained true` This switch tells the .NET Core SDK to create an executable as an SCD.</span></span>

| <span data-ttu-id="9aee4-215">게시 모드</span><span class="sxs-lookup"><span data-stu-id="9aee4-215">Publish Mode</span></span>                   | <span data-ttu-id="9aee4-216">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="9aee4-216">SDK Version</span></span> | <span data-ttu-id="9aee4-217">명령</span><span class="sxs-lookup"><span data-stu-id="9aee4-217">Command</span></span>                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| <span data-ttu-id="9aee4-218">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="9aee4-218">Self-contained deployment</span></span>      | <span data-ttu-id="9aee4-219">2.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-219">2.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | <span data-ttu-id="9aee4-220">3.1</span><span class="sxs-lookup"><span data-stu-id="9aee4-220">3.1</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | <span data-ttu-id="9aee4-221">5.0</span><span class="sxs-lookup"><span data-stu-id="9aee4-221">5.0</span></span>         | `dotnet publish -c Release -r <RID> --self-contained true`  |

> [!NOTE]
> <span data-ttu-id="9aee4-222">**세계화 고정 모드** 를 사용하여 배포의 전체 크기를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-222">You can reduce the total size of your deployment by enabling **globalization invariant mode**.</span></span> <span data-ttu-id="9aee4-223">이 모드는 전역적으로 인식되지 않는 서식 지정 규칙, 대/소문자 규칙 및 문자열 비교와 [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture)의 정렬 순서를 사용할 수 있는 애플리케이션에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aee4-223">This mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span> <span data-ttu-id="9aee4-224">**세계화 고정 모드** 와 이 모드를 사용하는 방법에 대한 자세한 내용은 [.NET Core 세계화 고정 모드](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aee4-224">For more information about **globalization invariant mode** and how to enable it, see [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9aee4-225">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9aee4-225">See also</span></span>

- [<span data-ttu-id="9aee4-226">.NET 애플리케이션 배포 개요</span><span class="sxs-lookup"><span data-stu-id="9aee4-226">.NET Application Deployment Overview</span></span>](index.md)
- [<span data-ttu-id="9aee4-227">.NET RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="9aee4-227">.NET Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
