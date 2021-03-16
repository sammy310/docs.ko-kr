---
title: dotnet tool install 명령
description: dotnet tool install 명령은 머신에 지정된 .NET 도구를 설치합니다.
ms.date: 02/14/2020
ms.openlocfilehash: b04e7fd24edce5d5da67cdd83fbea797118689b4
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206483"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="90bb4-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="90bb4-103">dotnet tool install</span></span>

<span data-ttu-id="90bb4-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="90bb4-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="90bb4-105">이름</span><span class="sxs-lookup"><span data-stu-id="90bb4-105">Name</span></span>

<span data-ttu-id="90bb4-106">`dotnet tool install` - 머신에 지정된 [.NET 도구](global-tools.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-106">`dotnet tool install` - Installs the specified [.NET tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="90bb4-107">개요</span><span class="sxs-lookup"><span data-stu-id="90bb4-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a><span data-ttu-id="90bb4-108">설명</span><span class="sxs-lookup"><span data-stu-id="90bb4-108">Description</span></span>

<span data-ttu-id="90bb4-109">`dotnet tool install` 명령은 머신에 .NET 도구를 설치하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-109">The `dotnet tool install` command provides a way for you to install .NET tools on your machine.</span></span> <span data-ttu-id="90bb4-110">이 명령을 사용하려면 다음 설치 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="90bb4-111">전역 도구를 기본 위치에 설치하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="90bb4-112">전역 도구를 사용자 지정 위치에 설치하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="90bb4-113">로컬 도구를 설치하려면 `--global` 및 `--tool-path` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="90bb4-114">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="90bb4-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="90bb4-115">`-g` 또는 `--global` 옵션을 지정하면 전역 도구는 기본적으로 다음 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="90bb4-116">OS</span><span class="sxs-lookup"><span data-stu-id="90bb4-116">OS</span></span>          | <span data-ttu-id="90bb4-117">경로</span><span class="sxs-lookup"><span data-stu-id="90bb4-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="90bb4-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="90bb4-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="90bb4-119">Windows</span><span class="sxs-lookup"><span data-stu-id="90bb4-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="90bb4-120">로컬 도구는 현재 디렉터리 아래의 *.config* 디렉터리에 있는 *dotnet-tools.json* 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-120">Local tools are added to a *dotnet-tools.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="90bb4-121">매니페스트 파일이 아직 없는 경우 다음 명령을 실행하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="90bb4-122">자세한 내용은 [로컬 도구 설치](global-tools.md#install-a-local-tool)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90bb4-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="90bb4-123">인수</span><span class="sxs-lookup"><span data-stu-id="90bb4-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="90bb4-124">설치할 .NET 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-124">Name/ID of the NuGet package that contains the .NET tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="90bb4-125">옵션</span><span class="sxs-lookup"><span data-stu-id="90bb4-125">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="90bb4-126">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-126">Adds an additional NuGet package source to use during installation.</span></span> <span data-ttu-id="90bb4-127">피드는 우선 순위에 따라 순차적으로 액세스하는 것이 아니라 병렬로 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-127">Feeds are accessed in parallel, not sequentially in some order of precedence.</span></span> <span data-ttu-id="90bb4-128">동일한 패키지와 버전이 여러 피드에 있는 경우 가장 빠른 피드가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-128">If the same package and version is in multiple feeds, the fastest feed wins.</span></span> <span data-ttu-id="90bb4-129">자세한 내용은 [NuGet 패키지를 설치하면 어떻게 되나요?](/nuget/concepts/package-installation-process)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90bb4-129">For more information, see [What happens when a NuGet package is installed?](/nuget/concepts/package-installation-process).</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="90bb4-130">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-130">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="90bb4-131">도구를 설치할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-131">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="90bb4-132">기본적으로 .NET SDK는 가장 적합한 대상 프레임워크를 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-132">By default, the .NET SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="90bb4-133">사용자 전체 설치임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-133">Specifies that the installation is user wide.</span></span> <span data-ttu-id="90bb4-134">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-134">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="90bb4-135">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구 설치가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-135">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="90bb4-136">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-136">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="90bb4-137">전역 도구를 설치할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-137">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="90bb4-138">경로는 절대 또는 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-138">PATH can be absolute or relative.</span></span> <span data-ttu-id="90bb4-139">경로가 존재하지 않는 경우 이 명령은 해당 경로를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-139">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="90bb4-140">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구 설치가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-140">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="90bb4-141">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="90bb4-142">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="90bb4-143">설치할 도구의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-143">The version of the tool to install.</span></span> <span data-ttu-id="90bb4-144">기본적으로 안정적인 최신 버전이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-144">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="90bb4-145">도구의 미리 보기 또는 이전 버전을 설치할 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-145">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="90bb4-146">예</span><span class="sxs-lookup"><span data-stu-id="90bb4-146">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="90bb4-147">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 기본 위치에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-147">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="90bb4-148">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 특정 Windows 디렉터리에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="90bb4-149">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 특정 Linux/macOS 디렉터리에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-149">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="90bb4-150">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)의 버전 2.0.0을 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-150">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="90bb4-151">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 현재 디렉터리용 로컬 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="90bb4-151">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="90bb4-152">참조</span><span class="sxs-lookup"><span data-stu-id="90bb4-152">See also</span></span>

- [<span data-ttu-id="90bb4-153">.NET 도구</span><span class="sxs-lookup"><span data-stu-id="90bb4-153">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="90bb4-154">자습서: .NET CLI를 사용하여 .NET 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="90bb4-154">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="90bb4-155">자습서: .NET CLI를 사용하여 .NET 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="90bb4-155">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
