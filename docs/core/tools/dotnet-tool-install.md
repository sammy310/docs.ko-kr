---
title: dotnet tool install 명령
description: dotnet tool install 명령은 컴퓨터에 지정된 .NET Core 도구를 설치합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 2705defe9b77009ca1411da28dd86d144ccc19e6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543471"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="41bc0-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="41bc0-103">dotnet tool install</span></span>

<span data-ttu-id="41bc0-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="41bc0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="41bc0-105">이름</span><span class="sxs-lookup"><span data-stu-id="41bc0-105">Name</span></span>

<span data-ttu-id="41bc0-106">`dotnet tool install` - 컴퓨터에 지정된 [.NET Core 도구](global-tools.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="41bc0-107">개요</span><span class="sxs-lookup"><span data-stu-id="41bc0-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="41bc0-108">설명</span><span class="sxs-lookup"><span data-stu-id="41bc0-108">Description</span></span>

<span data-ttu-id="41bc0-109">`dotnet tool install` 명령은 컴퓨터에서 .NET Core 도구를 설치하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="41bc0-110">이 명령을 사용하려면 다음 설치 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="41bc0-111">전역 도구를 기본 위치에 설치하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-111">To install a global tool in the default location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="41bc0-112">전역 도구를 사용자 지정 위치에 설치하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="41bc0-113">로컬 도구를 설치하려면 `--global` 및 `--tool-path` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="41bc0-114">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="41bc0-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="41bc0-115">`-g` 또는 `--global` 옵션을 지정하면 전역 도구는 기본적으로 다음 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="41bc0-116">OS</span><span class="sxs-lookup"><span data-stu-id="41bc0-116">OS</span></span>          | <span data-ttu-id="41bc0-117">경로</span><span class="sxs-lookup"><span data-stu-id="41bc0-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="41bc0-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="41bc0-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="41bc0-119">Windows</span><span class="sxs-lookup"><span data-stu-id="41bc0-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="41bc0-120">로컬 도구는 현재 디렉터리 아래의 *.config* 디렉터리에 있는 *tool-manifest.json* 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="41bc0-121">매니페스트 파일이 아직 없는 경우 다음 명령을 실행하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="41bc0-122">자세한 내용은 [로컬 도구 설치](global-tools.md#install-a-local-tool)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41bc0-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="41bc0-123">인수</span><span class="sxs-lookup"><span data-stu-id="41bc0-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="41bc0-124">설치할 .NET Core 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="41bc0-125">옵션</span><span class="sxs-lookup"><span data-stu-id="41bc0-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="41bc0-126">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="41bc0-127">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="41bc0-128">도구를 설치할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="41bc0-129">기본적으로 .NET Core SDK는 가장 적합한 대상 프레임워크를 선택하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="41bc0-130">사용자 전체 설치임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="41bc0-131">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="41bc0-132">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구 설치가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="41bc0-133">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="41bc0-134">전역 도구를 설치할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="41bc0-135">경로는 절대 또는 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="41bc0-136">경로가 존재하지 않는 경우 이 명령은 해당 경로를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="41bc0-137">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구 설치가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span> 

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="41bc0-138">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="41bc0-139">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="41bc0-140">설치할 도구의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-140">The version of the tool to install.</span></span> <span data-ttu-id="41bc0-141">기본적으로 안정적인 최신 버전이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="41bc0-142">도구의 미리 보기 또는 이전 버전을 설치할 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="41bc0-143">예</span><span class="sxs-lookup"><span data-stu-id="41bc0-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="41bc0-144">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 기본 위치에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="41bc0-145">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 특정 Windows 디렉터리에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="41bc0-146">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 특정 Linux/macOS 디렉터리에 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="41bc0-147">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)의 버전 2.0.0을 전역 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="41bc0-148">[dotnetsay](https://www.nuget.org/packages/dotnetsay/)를 현재 디렉터리용 로컬 도구로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="41bc0-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="41bc0-149">참조</span><span class="sxs-lookup"><span data-stu-id="41bc0-149">See also</span></span>

- [<span data-ttu-id="41bc0-150">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="41bc0-150">.NET Core tools</span></span>](global-tools.md)
