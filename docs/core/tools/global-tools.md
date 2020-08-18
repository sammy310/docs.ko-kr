---
title: .NET Core 도구
description: .NET Core 도구를 설치, 사용, 업데이트 및 제거하는 방법을 설명합니다. 전역 도구, 도구 경로 도구 및 로컬 도구를 다룹니다.
author: KathleenDollard
ms.topic: how-to
ms.date: 02/12/2020
ms.openlocfilehash: 00c0317fcfc4da0e7205c23faa7b355c20882ec9
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062732"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="e0cfb-104">.NET Core 도구를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="e0cfb-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="e0cfb-105">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e0cfb-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="e0cfb-106">.NET Core 도구는 콘솔 애플리케이션을 포함하는 특별한 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="e0cfb-107">다음과 같은 방법으로 컴퓨터에 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="e0cfb-108">전역 도구로</span><span class="sxs-lookup"><span data-stu-id="e0cfb-108">As a global tool.</span></span>

  <span data-ttu-id="e0cfb-109">도구 이진 파일이 PATH 환경 변수에 추가된 기본 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="e0cfb-110">해당 위치를 지정하지 않고 컴퓨터의 모든 디렉터리에서 도구를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="e0cfb-111">한 버전의 도구가 컴퓨터의 모든 디렉터리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="e0cfb-112">사용자 지정 위치에서 전역 도구로(도구 경로 도구라고도 함)</span><span class="sxs-lookup"><span data-stu-id="e0cfb-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="e0cfb-113">도구 이진 파일이 사용자가 지정하는 위치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="e0cfb-114">설치 디렉터리에서 또는 명령 이름으로 디렉터리를 제공하거나 PATH 환경 변수에 디렉터리를 추가하여 이 도구를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="e0cfb-115">한 버전의 도구가 컴퓨터의 모든 디렉터리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="e0cfb-116">로컬 도구로(.NET Core SDK 3.0 이상에 적용됨)</span><span class="sxs-lookup"><span data-stu-id="e0cfb-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="e0cfb-117">도구 이진 파일이 기본 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="e0cfb-118">설치 디렉터리 또는 하위 디렉터리에서 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="e0cfb-119">디렉터리마다 동일한 도구의 다른 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="e0cfb-120">.NET CLI는 매니페스트 파일을 사용하여 디렉터리에 로컬로 설치되는 도구를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="e0cfb-121">매니페스트 파일을 소스 코드 리포지토리의 루트 디렉터리에 저장하면 참가자가 리포지토리를 복제하고 매니페스트 파일에 나열된 모든 도구를 설치하는 단일 .NET Core CLI 명령을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0cfb-122">.NET Core 도구는 완전 신뢰로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="e0cfb-123">작성자를 신뢰하지 않는 한 .NET Core 도구를 설치하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="e0cfb-124">도구 찾기</span><span class="sxs-lookup"><span data-stu-id="e0cfb-124">Find a tool</span></span>

<span data-ttu-id="e0cfb-125">현재 .NET Core에는 도구 검색 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="e0cfb-126">다음은 도구를 찾는 몇 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="e0cfb-127">".NET 도구" 패키지 유형 필터를 사용하여 [NuGet](https://www.nuget.org) 웹 사이트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-127">Search the [NuGet](https://www.nuget.org) website by using the ".NET tool" package type filter.</span></span> <span data-ttu-id="e0cfb-128">자세한 내용은 [패키지 찾기 및 선택](/nuget/consume-packages/finding-and-choosing-packages)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-128">For more information, see [Finding and choosing packages](/nuget/consume-packages/finding-and-choosing-packages).</span></span>
* <span data-ttu-id="e0cfb-129">[natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 리포지토리에서 도구 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-129">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="e0cfb-130">[ToolGet](https://www.toolget.net/)을 사용하여 .NET 도구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-130">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="e0cfb-131">[dotnet/aspnetcore GitHub 리포지토리의 Tools 디렉터리](https://github.com/dotnet/aspnetcore/tree/master/src/Tools)에서 ASP.NET Core 팀이 만든 도구의 소스 코드를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-131">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="e0cfb-132">[.NET Core dotnet 진단 도구](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)에서 진단 도구에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-132">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="e0cfb-133">작성자 및 통계 확인</span><span class="sxs-lookup"><span data-stu-id="e0cfb-133">Check the author and statistics</span></span>

<span data-ttu-id="e0cfb-134">.NET Core 도구는 완전 신뢰로 실행되고 전역 도구는 PATH 환경 변수에 추가되므로 매우 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="e0cfb-135">신뢰할 수 없는 사용자의 도구를 다운로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="e0cfb-136">도구가 NuGet에서 호스팅되는 경우 도구를 검색하여 작성자 및 통계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="e0cfb-137">전역 도구 설치</span><span class="sxs-lookup"><span data-stu-id="e0cfb-137">Install a global tool</span></span>

<span data-ttu-id="e0cfb-138">도구를 전역 도구로 설치하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md)의 `-g` 또는 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="e0cfb-139">출력은 다음 예제와 같이 도구 및 설치된 버전을 호출하는 데 사용되는 명령을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="e0cfb-140">도구 이진 파일의 기본 위치는 운영 체제에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="e0cfb-141">OS</span><span class="sxs-lookup"><span data-stu-id="e0cfb-141">OS</span></span>          | <span data-ttu-id="e0cfb-142">경로</span><span class="sxs-lookup"><span data-stu-id="e0cfb-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="e0cfb-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="e0cfb-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="e0cfb-144">Windows</span><span class="sxs-lookup"><span data-stu-id="e0cfb-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="e0cfb-145">이 위치는 SDK를 처음 실행할 때 사용자의 경로에 추가되므로 전역 도구는 도구 위치를 지정하지 않고 모든 디렉터리에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="e0cfb-146">도구 액세스는 컴퓨터 전역이 아닌 사용자별로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="e0cfb-147">전역 도구는 도구를 설치한 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="e0cfb-148">사용자 지정 위치에 전역 도구 설치</span><span class="sxs-lookup"><span data-stu-id="e0cfb-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="e0cfb-149">도구를 사용자 지정 위치에 전역 도구로 설치하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md)의 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="e0cfb-150">Windows에서:</span><span class="sxs-lookup"><span data-stu-id="e0cfb-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="e0cfb-151">Linux 또는 macOS에서:</span><span class="sxs-lookup"><span data-stu-id="e0cfb-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="e0cfb-152">.NET Core SDK는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="e0cfb-153">[도구 경로 도구를 호출](#invoke-a-tool-path-tool)하려면 다음 방법 중 하나를 사용하여 명령을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="e0cfb-154">PATH 환경 변수에 설치 디렉터리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="e0cfb-155">도구를 호출할 때 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="e0cfb-156">설치 디렉터리 내에서 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="e0cfb-157">로컬 도구 설치</span><span class="sxs-lookup"><span data-stu-id="e0cfb-157">Install a local tool</span></span>

<span data-ttu-id="e0cfb-158">**.NET Core 3.0 SDK 이상에 적용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e0cfb-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="e0cfb-159">로컬 액세스 전용(현재 디렉터리 및 하위 디렉터리용) 도구를 설치하려면 매니페스트 파일에 도구를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="e0cfb-160">도구 매니페스트 파일을 만들려면 `dotnet new tool-manifest` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="e0cfb-161">이 명령은 *.config* 디렉터리 아래에 *dotnet-tools.json*이라는 매니페스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="e0cfb-162">매니페스트 파일에 로컬 도구를 추가하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md) 명령을 사용하고 `--global` 및 `--tool-path` 옵션을 **생략**합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="e0cfb-163">명령 출력은 다음 예제와 같이 새로 설치된 도구가 있는 매니페스트 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="e0cfb-164">다음 예제에서는 두 개의 로컬 도구가 설치된 매니페스트 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="e0cfb-165">일반적으로 로컬 도구는 리포지토리의 루트 디렉터리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="e0cfb-166">저장소에 매니페스트 파일을 체크 인한 후에는 리포지토리에서 코드를 체크 아웃하는 개발자가 최신 매니페스트 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="e0cfb-167">매니페스트 파일에 나열된 모든 도구를 설치하려면 `dotnet tool restore` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="e0cfb-168">출력은 복원된 도구를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="e0cfb-169">특정 도구 버전 설치</span><span class="sxs-lookup"><span data-stu-id="e0cfb-169">Install a specific tool version</span></span>

<span data-ttu-id="e0cfb-170">시험판 버전 또는 특정 버전의 도구를 설치하려면 다음 예제와 같이 `--version` 옵션을 사용하여 버전 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="e0cfb-171">도구 사용</span><span class="sxs-lookup"><span data-stu-id="e0cfb-171">Use a tool</span></span>

<span data-ttu-id="e0cfb-172">도구를 호출하는 데 사용하는 명령은 사용자가 설치하는 패키지의 이름과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="e0cfb-173">현재 컴퓨터에 현재 사용자에 대해 설치되어 있는 모든 도구를 표시하려면 [dotnet tool list](dotnet-tool-list.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="e0cfb-174">출력에는 다음 예제와 같이 각 도구의 버전 및 명령이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="e0cfb-175">이 예제에서는 목록에 로컬 도구가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="e0cfb-176">전역 도구를 보려면 `--global` 옵션을 사용하고, 도구 경로 도구를 보려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="e0cfb-177">전역 도구 호출</span><span class="sxs-lookup"><span data-stu-id="e0cfb-177">Invoke a global tool</span></span>

<span data-ttu-id="e0cfb-178">전역 도구의 경우 도구 명령을 단독으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="e0cfb-179">예를 들어 명령이 `dotnetsay` 또는 `dotnet-doc`이면 명령을 호출하는 데 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="e0cfb-180">명령이 접두사 `dotnet-`으로 시작하는 경우 도구를 호출하는 다른 방법은 `dotnet` 명령을 사용하고 도구 명령 접두사를 생략하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="e0cfb-181">예를 들어 명령이 `dotnet-doc`인 경우 다음 명령은 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="e0cfb-182">그러나 다음 시나리오에서는 `dotnet` 명령을 사용하여 전역 도구를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="e0cfb-183">전역 도구와 로컬 도구는 접두사 `dotnet-`가 있는 동일한 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="e0cfb-184">로컬 도구에 대한 범위에 있는 디렉터리에서 전역 도구를 호출하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="e0cfb-185">이 시나리오에서는 `dotnet doc` 및 `dotnet dotnet-doc`이 로컬 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="e0cfb-186">전역 도구를 호출하려면 명령을 단독으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="e0cfb-187">도구 경로 도구 호출</span><span class="sxs-lookup"><span data-stu-id="e0cfb-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="e0cfb-188">`tool-path` 옵션을 사용하여 설치된 전역 도구를 호출하려면 [이 문서의 앞부분](#install-a-global-tool-in-a-custom-location)에서 설명한 대로 명령을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="e0cfb-189">로컬 도구 호출</span><span class="sxs-lookup"><span data-stu-id="e0cfb-189">Invoke a local tool</span></span>

<span data-ttu-id="e0cfb-190">로컬 도구를 호출하려면 설치 디렉터리 내에서 `dotnet` 명령을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="e0cfb-191">다음 예제와 같이 긴 형식(`dotnet tool run <COMMAND_NAME>`) 또는 짧은 형식(`dotnet <COMMAND_NAME>`)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="e0cfb-192">명령에 접두사 `dotnet-`가 있으면 도구를 호출할 때 접두사를 포함하거나 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="e0cfb-193">예를 들어 명령이 `dotnet-doc`인 경우 다음 예제 중 하나는 로컬 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="e0cfb-194">도구 업데이트</span><span class="sxs-lookup"><span data-stu-id="e0cfb-194">Update a tool</span></span>

<span data-ttu-id="e0cfb-195">도구 업데이트는 원래 버전을 제거하고 안정적인 최신 버전을 다시 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="e0cfb-196">도구를 업데이트하려면 도구를 설치하는 데 사용한 것과 동일한 옵션을 지정하여 [dotnet tool update](dotnet-tool-update.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="e0cfb-197">로컬 도구의 경우 SDK는 현재 디렉터리와 부모 디렉터리를 검색하여 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="e0cfb-198">매니페스트 파일에 이러한 패키지 ID가 없는 경우 SDK는 가장 가까운 매니페스트 파일에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="e0cfb-199">도구 제거</span><span class="sxs-lookup"><span data-stu-id="e0cfb-199">Uninstall a tool</span></span>

<span data-ttu-id="e0cfb-200">도구를 설치하는 데 사용한 것과 동일한 옵션을 지정하여 [dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 사용하여 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path <packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="e0cfb-201">로컬 도구의 경우 SDK는 현재 디렉터리와 부모 디렉터리를 검색하여 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="e0cfb-202">도움말 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e0cfb-202">Get help and troubleshoot</span></span>

<span data-ttu-id="e0cfb-203">사용 가능한 `dotnet tool` 명령 목록을 가져오려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="e0cfb-204">도구 사용 지침을 얻으려면 다음 명령 중 하나를 입력하거나 도구의 웹 사이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="e0cfb-205">도구를 설치하거나 실행하지 못하는 경우 [.NET Core 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0cfb-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0cfb-206">참조</span><span class="sxs-lookup"><span data-stu-id="e0cfb-206">See also</span></span>

- [<span data-ttu-id="e0cfb-207">자습서: .NET Core CLI를 사용하여 .NET Core 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="e0cfb-207">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>](global-tools-how-to-create.md)
- [<span data-ttu-id="e0cfb-208">자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="e0cfb-208">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="e0cfb-209">자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="e0cfb-209">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
