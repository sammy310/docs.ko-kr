---
title: ML.NET CLI(명령줄 인터페이스) 도구를 설치하는 방법
description: ML.NET CLI(명령줄 인터페이스) 도구를 설치, 업그레이드, 다운그레이드 및 제거하는 방법에 대해 알아봅니다.
ms.date: 06/08/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 13203246411deadf3ab13a5eba0d2c8e6e9027c5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602273"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="4790e-103">ML.NET CLI(명령줄 인터페이스) 도구를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="4790e-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="4790e-104">Windows, Mac 또는 Linux에 ML.NET CLI(명령줄 인터페이스)를 설치하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-104">Learn how to install the ML.NET CLI (command-line interface) on Windows, Mac, or Linux.</span></span>

<span data-ttu-id="4790e-105">ML.NET CLI는 AutoML(자동화된 Machine Learning) 및 학습 데이터 세트를 사용하여 우수한 품질의 ML.NET 모델과 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-105">The ML.NET CLI generates good quality ML.NET models and source code using automated machine learning (AutoML) and a training dataset.</span></span>

> [!NOTE]
> <span data-ttu-id="4790e-106">이 항목은 현재 미리 보기로 제공되는 ML.NET CLI 및 ML.NET AutoML을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-106">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="4790e-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4790e-107">Pre-requisites</span></span>

- [<span data-ttu-id="4790e-108">.NET Core 3.1 SDK</span><span class="sxs-lookup"><span data-stu-id="4790e-108">.NET Core 3.1 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

- <span data-ttu-id="4790e-109">(선택 사항) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="4790e-109">(Optional) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="4790e-110">`F5` 키를 누르거나 `dotnet run`(.NET Core CLI)을 사용하여 Visual Studio에서 생성된 C# 코드 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-110">You can run the generated C# code projects with Visual Studio by pressing the `F5` key or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="4790e-111">참고: .NET Core SDK 설치 후 `dotnet tool` 명령이 작동하지 않는 경우 Windows에서 로그아웃했다가 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-111">Note: If after installing .NET Core SDK the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="4790e-112">설치</span><span class="sxs-lookup"><span data-stu-id="4790e-112">Install</span></span>

<span data-ttu-id="4790e-113">ML.NET CLI는 다른 DotNet Global Tool처럼 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-113">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="4790e-114">`dotnet tool install` .NET Core CLI 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-114">You use the `dotnet tool install` .NET Core CLI command.</span></span>

<span data-ttu-id="4790e-115">다음 예제에서는 기본 NuGet 피드 위치에 ML.NET CLI를 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-115">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```dotnetcli
dotnet tool install -g mlnet
```

<span data-ttu-id="4790e-116">도구를 설치할 수 없는 경우(즉 기본 NuGet 피드에서 사용할 수 없는 경우) 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-116">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="4790e-117">예상한 피드가 확인되고 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-117">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="4790e-118">설치에 성공하면 다음 예와 같이 도구와 설치된 버전을 호출하는 데 사용되는 명령을 보여 주는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-118">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="4790e-119">다음 명령을 입력하여 설치가 완료되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-119">You can confirm the installation was successful by typing the following command:</span></span>

```console
mlnet
```

<span data-ttu-id="4790e-120">‘classification’ 명령처럼 mlnet 도구에 대해 사용 가능한 명령의 도움말을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-120">You should see the help for available commands for the mlnet tool such as the 'classification' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="4790e-121">특정 릴리스 버전 설치</span><span class="sxs-lookup"><span data-stu-id="4790e-121">Install a specific release version</span></span>

<span data-ttu-id="4790e-122">이전 릴리스 버전 또는 특정 버전의 도구를 설치하려는 경우 다음 형식을 사용하여 [프레임워크](../../standard/frameworks.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-122">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="4790e-123">다음 명령을 입력하여 패키지가 올바르게 설치되었는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-123">You can also check if the package is properly installed by typing the following command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="4790e-124">CLI 패키지 제거</span><span class="sxs-lookup"><span data-stu-id="4790e-124">Uninstall the CLI package</span></span>

<span data-ttu-id="4790e-125">로컬 컴퓨터에서 패키지를 제거하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-125">Type the following command to uninstall the package from your local machine:</span></span>

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="4790e-126">CLI 패키지 업데이트</span><span class="sxs-lookup"><span data-stu-id="4790e-126">Update the CLI package</span></span>

<span data-ttu-id="4790e-127">로컬 컴퓨터에서 패키지를 업데이트하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-127">Type the following command to update the package from your local machine:</span></span>

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="4790e-128">CLI 제안(탭 기반 자동 완성) 설정</span><span class="sxs-lookup"><span data-stu-id="4790e-128">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="4790e-129">ML.NET CLI는 `System.CommandLine`을 기반으로 하므로 탭 완성을 기본 제공으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-129">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="4790e-130">탭 자동 완성이 작동하는 예제는 다음 애니메이션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-130">An example of how tab auto completion works is shown in the following animation:</span></span>

![이미지](./media/cli-tab-completion.gif)

<span data-ttu-id="4790e-132">'탭 기반 자동 완성'(매개 변수 제안)은 *Windows PowerShell* 및 *macOS/Linux bash*에서 실행되나 *Windows CMD*에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-132">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="4790e-133">현재 미리 보기 버전에서 이를 사용하려면 최종 사용자가 아래에서 설명한 대로 셸마다 한 번씩 몇 가지 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-133">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="4790e-134">이 후에는 ML.NET CLI처럼 `System.CommandLine`을 사용하여 작성된 모든 앱에 완성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-134">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="4790e-135">완성을 사용하려는 컴퓨터에서 다음 두 가지를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-135">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="4790e-136">다음 명령을 실행하여 `dotnet-suggest` 글로벌 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-136">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="4790e-137">셸 프로필에 적합한 Shim 스크립트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-137">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="4790e-138">셸 프로필 파일을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-138">You may have to create a shell profile file.</span></span> <span data-ttu-id="4790e-139">Shim 스크립트는 셸의 완성 요청을 `dotnet-suggest` 도구로 전달하며 적합한 `System.CommandLine` 기반 앱에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-139">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    - <span data-ttu-id="4790e-140">Bash의 경우 [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash)의 콘텐츠를 `~/.bash_profile`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-140">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    - <span data-ttu-id="4790e-141">PowerShell의 경우 [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1)의 콘텐츠를 PowerShell 프로필에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-141">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="4790e-142">콘솔에서 다음 명령을 실행하여 PowerShell 프로필의 예상 경로를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-142">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    echo $profile
    ```

<span data-ttu-id="4790e-143">(다른 셸의 경우 [검색](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) 또는 [문제](https://github.com/dotnet/System.CommandLine/issues) 열기)</span><span class="sxs-lookup"><span data-stu-id="4790e-143">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="4790e-144">설치 디렉터리</span><span class="sxs-lookup"><span data-stu-id="4790e-144">Installation directory</span></span>

<span data-ttu-id="4790e-145">ML.NET CLI는 기본 디렉터리 또는 특정 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-145">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="4790e-146">기본 디렉터리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-146">The default directories are:</span></span>

| <span data-ttu-id="4790e-147">OS</span><span class="sxs-lookup"><span data-stu-id="4790e-147">OS</span></span>          | <span data-ttu-id="4790e-148">경로</span><span class="sxs-lookup"><span data-stu-id="4790e-148">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="4790e-149">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="4790e-149">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="4790e-150">Windows</span><span class="sxs-lookup"><span data-stu-id="4790e-150">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="4790e-151">이러한 위치는 SDK를 처음 실행할 때 사용자 경로에 추가되므로 설치된 Global Tool을 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-151">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="4790e-152">참고: Global Tool은 컴퓨터 전체가 아닌 사용자 특정입니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-152">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="4790e-153">사용자별 도구라는 것은 컴퓨터의 모든 사용자가 사용할 수 있는 Global Tool을 설치할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-153">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="4790e-154">이 도구는 도구가 설치된 각 사용자 프로필에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-154">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="4790e-155">Global Tool을 특정 디렉터리에 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-155">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="4790e-156">특정 디렉터리에 설치된 경우 사용자는 경로에 해당 디렉터리를 포함하거나, 지정된 디렉터리로 명령을 호출하거나, 지정된 디렉터리 내에서 도구를 호출하여 명령을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-156">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="4790e-157">이 경우 .NET Core CLI는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4790e-157">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="4790e-158">참조</span><span class="sxs-lookup"><span data-stu-id="4790e-158">See also</span></span>

- [<span data-ttu-id="4790e-159">ML.NET CLI 개요</span><span class="sxs-lookup"><span data-stu-id="4790e-159">ML.NET CLI overview</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="4790e-160">자습서: ML.NET CLI를 사용하여 감정 분석</span><span class="sxs-lookup"><span data-stu-id="4790e-160">Tutorial: Analyze sentiment with the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="4790e-161">ML.NET CLI auto-train 명령 참조 가이드</span><span class="sxs-lookup"><span data-stu-id="4790e-161">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="4790e-162">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="4790e-162">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
