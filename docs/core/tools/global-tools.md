---
title: .NET Core Global Tool
description: .NET Core Global Tool의 개요와 사용 가능한 .NET Core CLI 명령입니다.
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 1531df48b7ca9c816b897d06e725ec375f6cae31
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920499"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="7441f-103">.NET Core Global Tool 개요</span><span class="sxs-lookup"><span data-stu-id="7441f-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="7441f-104">.NET Core Global Tool은 콘솔 애플리케이션을 포함하는 특별한 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="7441f-105">Global Tool은 컴퓨터에서 PATH 환경 변수 또는 사용자 지정 위치에 포함된 기본 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="7441f-106">.NET Core Global Tool을 사용하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="7441f-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="7441f-107">도구에 대한 정보를 찾습니다(일반적으로 웹 사이트 또는 GitHub 페이지).</span><span class="sxs-lookup"><span data-stu-id="7441f-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="7441f-108">홈에서 피드의 작성자 및 통계를 확인합니다(일반적으로 NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="7441f-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="7441f-109">도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-109">Install the tool.</span></span>
* <span data-ttu-id="7441f-110">도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-110">Call the tool.</span></span>
* <span data-ttu-id="7441f-111">도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-111">Update the tool.</span></span>
* <span data-ttu-id="7441f-112">도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7441f-113">.NET Core Global Tool이 경로에 나타나고 완전 신뢰 상태로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="7441f-114">작성자를 신뢰하지 않는 경우 .NET Core Global Tool을 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="7441f-115">.NET Core Global Tool 찾기</span><span class="sxs-lookup"><span data-stu-id="7441f-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="7441f-116">현재 .NET Core CLI에는 Global Tool 검색 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-116">Currently, there isn't a Global Tool search feature in the .NET Core CLI.</span></span> <span data-ttu-id="7441f-117">다음은 도구를 찾는 방법에 대한 몇 가지 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-117">The following are some recommendations on how to find tools:</span></span>

* <span data-ttu-id="7441f-118">[NuGet](https://www.nuget.org)에서 .NET Core Global Tool을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-118">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="7441f-119">그러나 NuGet에서는 아직 .NET Core Global Tool을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-119">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>
* <span data-ttu-id="7441f-120">블로그 게시물 또는 [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 리포지토리에서 도구 권장 사항을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-120">You may find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="7441f-121">[dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub 리포지토리에서 ASP.NET 팀이 만든 Global Tool의 소스 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-121">You can see the source code for the Global Tools created by the ASP.NET team at the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub repository.</span></span>
* <span data-ttu-id="7441f-122">[.NET Core dotnet 진단 글로벌 도구](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)에서 진단 도구에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-122">You can learn about diagnostic tools at [.NET Core dotnet diagnostic Global Tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="7441f-123">작성자 및 통계 확인</span><span class="sxs-lookup"><span data-stu-id="7441f-123">Check the author and statistics</span></span>

<span data-ttu-id="7441f-124">.NET Core Global Tool은 완전 신뢰 상태로 실행되며 일반적으로 사용자 경로에 설치되므로 매우 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-124">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="7441f-125">신뢰할 수 없는 사용자의 도구를 다운로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7441f-125">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="7441f-126">도구가 NuGet에서 호스팅되는 경우 도구를 검색하여 작성자 및 통계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-126">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="7441f-127">Global Tool 설치</span><span class="sxs-lookup"><span data-stu-id="7441f-127">Install a Global Tool</span></span>

<span data-ttu-id="7441f-128">Global Tool을 설치하려면 [dotnet tool install](dotnet-tool-install.md) .NET Core CLI 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-128">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="7441f-129">다음 예제에서는 기본 위치에 Global Tool을 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-129">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="7441f-130">도구를 설치할 수 없는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-130">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="7441f-131">예상한 피드가 확인되고 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-131">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="7441f-132">이전 릴리스 버전 또는 특정 버전의 도구를 설치하려는 경우 다음 형식을 사용하여 버전 번호를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-132">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="7441f-133">설치에 성공하면 다음 예와 같이 도구와 설치된 버전을 호출하는 데 사용되는 명령을 보여 주는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-133">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="7441f-134">Global Tool은 기본 디렉터리 또는 특정 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-134">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="7441f-135">기본 디렉터리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-135">The default directories are:</span></span>

| <span data-ttu-id="7441f-136">OS</span><span class="sxs-lookup"><span data-stu-id="7441f-136">OS</span></span>          | <span data-ttu-id="7441f-137">경로</span><span class="sxs-lookup"><span data-stu-id="7441f-137">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="7441f-138">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="7441f-138">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="7441f-139">Windows</span><span class="sxs-lookup"><span data-stu-id="7441f-139">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="7441f-140">이러한 위치는 SDK를 처음 실행할 때 사용자 경로에 추가되므로 설치된 Global Tool을 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-140">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="7441f-141">Global Tool은 컴퓨터 전체가 아니라 사용자별 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-141">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="7441f-142">사용자별 도구라는 것은 컴퓨터의 모든 사용자가 사용할 수 있는 Global Tool을 설치할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-142">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="7441f-143">이 도구는 도구가 설치된 각 사용자 프로필에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-143">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="7441f-144">Global Tool을 특정 디렉터리에 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-144">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="7441f-145">특정 디렉터리에 설치된 경우 사용자는 경로에 해당 디렉터리를 포함하거나, 지정된 디렉터리로 명령을 호출하거나, 지정된 디렉터리 내에서 도구를 호출하여 명령을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-145">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="7441f-146">이 경우 .NET Core CLI는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-146">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="7441f-147">도구 사용</span><span class="sxs-lookup"><span data-stu-id="7441f-147">Use the tool</span></span>

<span data-ttu-id="7441f-148">도구가 설치되면 명령을 사용하여 도구를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-148">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="7441f-149">명령이 패키지 이름과 같지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-149">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="7441f-150">명령이 `dotnetsay`인 경우 다음을 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-150">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="7441f-151">도구 작성자가 도구를 `dotnet` 프롬프트 컨텍스트에 표시하려면 도구를 다음과 같이 `dotnet <command>`로 호출하는 방식으로 작성했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-151">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="7441f-152">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 설치된 패키지를 나열하면 설치된 Global Tool 패키지에 포함된 도구를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-152">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="7441f-153">도구의 웹 사이트에서 사용 지침을 찾거나 다음 명령 중 하나를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-153">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="7441f-154">기타 CLI 명령</span><span class="sxs-lookup"><span data-stu-id="7441f-154">Other CLI commands</span></span>

<span data-ttu-id="7441f-155">.NET Core SDK에는 .NET Core Global Tool을 지원하는 다른 명령이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-155">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="7441f-156">다음 옵션 중 하나와 함께 `dotnet tool` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-156">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="7441f-157">`--global` 또는 `-g`는 명령을 사용자 수준의 Global Tool에 적용 가능함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-157">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="7441f-158">`--tool-path`는 Global Tool의 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-158">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="7441f-159">Global Tool에 사용할 수 있는 명령을 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="7441f-159">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="7441f-160">Global Tool을 업데이트하려면 원래 버전을 제거하고 안정적인 최신 버전으로 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-160">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="7441f-161">Global Tool을 업데이트하려면 [dotnet tool update](dotnet-tool-update.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-161">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="7441f-162">[dotnet tool uninstall](dotnet-tool-uninstall.md)을 사용하여 Global Tool을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-162">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="7441f-163">현재 컴퓨터에 설치된 모든 Global Tool과 해당 버전 및 명령을 표시하려면 [dotnet tool list](dotnet-tool-list.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7441f-163">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="7441f-164">참조</span><span class="sxs-lookup"><span data-stu-id="7441f-164">See also</span></span>

* [<span data-ttu-id="7441f-165">.NET Core 도구 사용 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7441f-165">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
