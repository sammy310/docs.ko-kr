---
title: .NET Core 도구 사용 문제 해결
description: .NET Core 도구를 실행할 때 발생하는 일반적인 문제와 가능한 해결 방법을 검색합니다.
author: kdollard
ms.date: 02/14/2020
ms.openlocfilehash: ed6243f802c4d3ce56a742916a1a28676e3cd876
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146452"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="5e64e-103">.NET Core 도구 사용 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5e64e-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="5e64e-104">전역 도구 또는 로컬 도구일 수 있는 .NET Core 도구를 설치하거나 실행할 때 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="5e64e-105">이 문서에서는 일반적인 근본 원인과 몇 가지 가능한 해결 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="5e64e-106">설치된 .NET Core 도구가 실행되지 않음</span><span class="sxs-lookup"><span data-stu-id="5e64e-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="5e64e-107">.NET Core 도구가 실행되지 않는 경우, 다음 문제 중 하나가 발생했을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="5e64e-108">도구의 실행 파일을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="5e64e-109">올바른 버전의 .NET Core 런타임을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="5e64e-110">실행 파일을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="5e64e-110">Executable file not found</span></span>

<span data-ttu-id="5e64e-111">실행 파일을 찾을 수 없는 경우 다음과 유사한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="5e64e-112">실행 파일 이름에 따라 도구 호출 방법이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="5e64e-113">다음 표에서는 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-113">The following table describes the format:</span></span>

| <span data-ttu-id="5e64e-114">실행 파일 이름 형식</span><span class="sxs-lookup"><span data-stu-id="5e64e-114">Executable name format</span></span>  | <span data-ttu-id="5e64e-115">호출 형식</span><span class="sxs-lookup"><span data-stu-id="5e64e-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="5e64e-116">전역 도구</span><span class="sxs-lookup"><span data-stu-id="5e64e-116">Global tools</span></span>

  <span data-ttu-id="5e64e-117">전역 도구는 기본 디렉터리 또는 특정 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="5e64e-118">기본 디렉터리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-118">The default directories are:</span></span>

  | <span data-ttu-id="5e64e-119">OS</span><span class="sxs-lookup"><span data-stu-id="5e64e-119">OS</span></span>          | <span data-ttu-id="5e64e-120">경로</span><span class="sxs-lookup"><span data-stu-id="5e64e-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="5e64e-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="5e64e-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="5e64e-122">Windows</span><span class="sxs-lookup"><span data-stu-id="5e64e-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="5e64e-123">전역 도구를 실행하려는 경우, 머신의 `PATH` 환경 변수에 전역 도구를 설치한 경로가 포함되어 있고 실행 파일이 해당 경로에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="5e64e-124">.NET Core CLI는 처음 사용 시 PATH 환경 변수에 기본 위치를 추가하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-124">The .NET Core CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="5e64e-125">그러나 위치가 PATH에 자동으로 추가되지 않는 다음과 같은 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="5e64e-126">Linux를 사용 중이고, apt-get 또는 rpm이 아닌 *.tar.gz* 파일을 사용하여 .NET Core SDK를 설치한 경우</span><span class="sxs-lookup"><span data-stu-id="5e64e-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="5e64e-127">macOS10.15 “Catalina” 이상 버전을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="5e64e-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="5e64e-128">macOS10.14 “Mojave” 또는 이전 버전을 사용 중이고, *.pkg*가 아닌 *.tar.gz* 파일을 사용하여 .NET Core SDK를 설치한 경우</span><span class="sxs-lookup"><span data-stu-id="5e64e-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="5e64e-129">.NET Core 3.0 SDK를 설치했으며 `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` 환경 변수를 `false`로 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="5e64e-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="5e64e-130">.NET Core 2.2 SDK 또는 이전 버전을 설치했으며 `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` 환경 변수를 `true`로 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="5e64e-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="5e64e-131">이러한 시나리오이거나 `--tool-path` 옵션을 지정한 경우 컴퓨터의 `PATH` 환경 변수는 전역 도구를 설치한 경로를 자동으로 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="5e64e-132">이 경우 셸에서 환경 변수 업데이트용으로 제공하는 모든 메서드를 사용하여 도구 위치(예: `$HOME/.dotnet/tools`)를 `PATH` 환경 변수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="5e64e-133">자세한 내용은 [.NET Core 도구](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e64e-133">For more information, see [.NET Core tools](global-tools.md).</span></span>

* <span data-ttu-id="5e64e-134">로컬 도구</span><span class="sxs-lookup"><span data-stu-id="5e64e-134">Local tools</span></span>

  <span data-ttu-id="5e64e-135">로컬 도구를 실행하려는 경우, 현재 디렉터리 또는 부모 디렉터리 중 하나에 *dotnet-tools.json*이라는 매니페스트 파일이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="5e64e-136">이 파일은 루트 폴더 대신, 프로젝트 폴더 계층 구조에서 *.config*라는 임의 폴더 아래에 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="5e64e-137">*dotnet-tools.json*이 있으면 파일을 열고 실행하려는 도구를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="5e64e-138">파일에 `"isRoot": true` 항목이 없을 경우 파일 계층 구조 위로 추가 도구 매니페스트 파일이 있는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="5e64e-139">지정된 경로를 사용하여 설치된 .NET Core 도구를 실행하려는 경우, 도구를 사용할 때 해당 경로를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-139">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="5e64e-140">도구 경로를 사용하여 설치된 도구의 사용 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="5e64e-141">런타임을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="5e64e-141">Runtime not found</span></span>

<span data-ttu-id="5e64e-142">전역 도구는 [프레임워크 종속 애플리케이션](../deploying/index.md#publish-runtime-dependent)이므로, 머신에 설치된 .NET Core 런타임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-142">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-runtime-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="5e64e-143">필요한 런타임을 찾을 수 없는 경우, 다음과 같은 일반적인 .NET Core 런타임 롤포워드 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-143">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="5e64e-144">애플리케이션은 지정된 주 및 부 버전의 가장 높은 패치 릴리스로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="5e64e-145">일치하는 주 버전 및 부 버전 번호를 가진, 일치하는 런타임이 없으면 다음으로 높은 부 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="5e64e-146">런타임의 미리 보기 버전 간 또는 미리 보기 버전과 릴리스 버전 간에는 롤포워드가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="5e64e-147">따라서 미리 보기 버전을 사용하여 만든 .NET Core 도구는 작성자가 다시 빌드하여 다시 게시한 후에 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-147">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="5e64e-148">다음 두 가지 일반적인 시나리오에서는 롤포워드가 기본적으로 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="5e64e-149">하위 버전의 런타임만 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5e64e-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="5e64e-150">롤포워드는 이후 버전의 런타임만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="5e64e-151">상위 주 버전의 런타임만 사용할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5e64e-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="5e64e-152">롤포워드는 주 버전 경계를 넘지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="5e64e-153">애플리케이션이 적절한 런타임을 찾을 수 없는 경우 애플리케이션이 실행되지 않고 오류가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="5e64e-154">다음 명령 중 하나를 사용하여 머신에 설치된 .NET Core 런타임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-154">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="5e64e-155">도구가 현재 설치된 런타임 버전을 지원해야 한다고 생각되는 경우, 도구 작성자에게 버전 번호 또는 다중 대상의 업데이트가 가능한지 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="5e64e-156">작성자가 업데이트된 버전 번호로 도구 패키지를 다시 컴파일하고 NuGet에 다시 게시하면 복사본을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="5e64e-157">업데이트가 가능할 때까지 가장 빠른 해결 방법은 실행하려는 도구에서 작동하는 런타임 버전을 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="5e64e-158">특정 .NET Core 런타임 버전을 다운로드하려면 [.NET Core 다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-158">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="5e64e-159">기본 위치가 아닌 다른 위치에 .NET Core SDK를 설치하는 경우, 환경 변수 `DOTNET_ROOT`를 `dotnet` 실행 파일이 있는 디렉터리로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-159">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="5e64e-160">.NET Core 도구 설치 실패</span><span class="sxs-lookup"><span data-stu-id="5e64e-160">.NET Core tool installation fails</span></span>

<span data-ttu-id="5e64e-161">.NET Core 전역 또는 로컬 도구의 설치에 실패할 수 있는 원인에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-161">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="5e64e-162">도구 설치에 실패하면 다음과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="5e64e-163">실패 진단을 지원하기 위해 이전 메시지와 함께 NuGet 메시지가 사용자에게 직접 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="5e64e-164">NuGet 메시지는 문제를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="5e64e-165">패키지 명명 적용</span><span class="sxs-lookup"><span data-stu-id="5e64e-165">Package naming enforcement</span></span>

<span data-ttu-id="5e64e-166">Microsoft에서 도구의 패키지 ID 지침이 변경되어, 예상 이름으로 찾을 수 없는 도구가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="5e64e-167">새 지침에 따라 모든 Microsoft 도구 앞에 “Microsoft”가 접두사로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="5e64e-168">이 접두사는 예약되었으며, Microsoft 공인 인증서로 서명된 패키지에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="5e64e-169">전환 중에 일부 Microsoft 도구는 이전 형식의 패키지 ID를 사용하고 다른 도구는 새 형식을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="5e64e-170">패키지 ID가 업데이트될 경우, 최신 업데이트를 가져오려면 새 패키지 ID로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="5e64e-171">간소화된 도구 이름을 가진 패키지는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="5e64e-172">미리 보기 릴리스</span><span class="sxs-lookup"><span data-stu-id="5e64e-172">Preview releases</span></span>

* <span data-ttu-id="5e64e-173">미리 보기 릴리스를 설치하려고 하며, `--version` 옵션을 통해 버전을 지정하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="5e64e-174">미리 보기로 제공되는 .NET Core 도구는 미리 보기 상태임을 나타내는 이름 부분으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-174">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="5e64e-175">전체 미리 보기를 포함할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="5e64e-176">버전 번호가 올바른 형식이라고 가정하면, 다음 예제와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="5e64e-177">패키지가 .NET Core 도구가 아님</span><span class="sxs-lookup"><span data-stu-id="5e64e-177">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="5e64e-178">이 이름을 가진 NuGet 패키지는 있지만 .NET Core 도구가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-178">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="5e64e-179">.NET Core 도구가 아닌 일반 NuGet 패키지인 NuGet 패키지를 설치하려고 하면 다음과 유사한 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="5e64e-180">NU1212: `<ToolName>`에 대한 잘못된 프로젝트-패키지 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="5e64e-181">DotnetToolReference 프로젝트 스타일에는 DotnetTool 형식의 참조만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="5e64e-182">NuGet 피드에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5e64e-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="5e64e-183">인터넷 연결 문제 등의 이유로, 필요한 NuGet 피드에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="5e64e-184">도구를 설치하려면 도구 패키지가 포함된 NuGet 피드에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="5e64e-185">피드를 사용할 수 없는 경우 설치에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="5e64e-186">`nuget.config`를 사용하여 피드를 변경하거나, 특정 `nuget.config` 파일을 요청하거나, `--add-source` 스위치를 사용하여 추가 피드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="5e64e-187">기본적으로 NuGet은 연결할 수 없는 모든 피드에 대해 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="5e64e-188">`--ignore-failed-sources` 플래그는 연결할 수 없는 이러한 소스를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="5e64e-189">패키지 ID가 올바르지 않음</span><span class="sxs-lookup"><span data-stu-id="5e64e-189">Package ID incorrect</span></span>

* <span data-ttu-id="5e64e-190">도구 이름을 잘못 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="5e64e-191">일반적인 실패 원인은 잘못된 도구 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="5e64e-192">잘못 입력했을 수도 있고, 도구가 이동되었거나 사용 중단되었을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="5e64e-193">NuGet.org 도구의 경우 올바른 이름을 입력하는 한 가지 방법은 NuGet.org에서 도구를 검색하여 설치 명령을 복사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5e64e-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e64e-194">참조</span><span class="sxs-lookup"><span data-stu-id="5e64e-194">See also</span></span>

* [<span data-ttu-id="5e64e-195">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="5e64e-195">.NET Core tools</span></span>](global-tools.md)
