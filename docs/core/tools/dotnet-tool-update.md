---
title: dotnet tool update 명령
description: dotnet tool update 명령은 컴퓨터에서 지정된 .NET Core 도구를 업데이트합니다.
ms.date: 07/08/2020
ms.openlocfilehash: 7c4bde44ac9964828074baeb1a697ba64ed17887
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226623"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="69aba-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="69aba-103">dotnet tool update</span></span>

<span data-ttu-id="69aba-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="69aba-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="69aba-105">이름</span><span class="sxs-lookup"><span data-stu-id="69aba-105">Name</span></span>

<span data-ttu-id="69aba-106">`dotnet tool update` - 컴퓨터에서 지정된 [.NET Core 도구](global-tools.md)를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="69aba-107">개요</span><span class="sxs-lookup"><span data-stu-id="69aba-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="69aba-108">설명</span><span class="sxs-lookup"><span data-stu-id="69aba-108">Description</span></span>

<span data-ttu-id="69aba-109">`dotnet tool update` 명령은 컴퓨터의 .NET Core 도구를 패키지의 안정적인 최신 버전으로 업데이트하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="69aba-110">이 명령은 도구를 제거하고 다시 설치하여 효과적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="69aba-111">이 명령을 사용하려면 다음 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="69aba-112">기본 위치에 설치된 전역 도구를 업데이트하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="69aba-113">사용자 지정 위치에 설치된 전역 도구를 업데이트하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="69aba-114">로컬 도구를 업데이트하려면 `--local` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="69aba-115">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="69aba-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="69aba-116">인수</span><span class="sxs-lookup"><span data-stu-id="69aba-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="69aba-117">업데이트할 .NET Core 전역 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="69aba-118">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="69aba-119">옵션</span><span class="sxs-lookup"><span data-stu-id="69aba-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="69aba-120">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="69aba-121">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="69aba-122">여러 프로젝트를 병렬로 복원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="69aba-123">도구를 업데이트할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="69aba-124">패키지 소스 오류를 경고로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="69aba-125">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="69aba-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="69aba-126">도구 및 로컬 도구 매니페스트를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="69aba-127">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-127">Can't be combined with the `--global` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="69aba-128">패키지 및 HTTP 요청을 캐시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="69aba-129">매니페스트 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="69aba-130">전역 도구가 설치되는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="69aba-131">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="69aba-132">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="69aba-133">`--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="69aba-134">업데이트할 도구 패키지의 버전 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="69aba-135">버전을 다운그레이드하는 데 사용할 수 없으며, 먼저 최신 버전을 `uninstall`(제거)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="69aba-136">업데이트가 사용자 수준 도구에 대한 것임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="69aba-137">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="69aba-138">`--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="69aba-139">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="69aba-140">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="69aba-141">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="69aba-142">예</span><span class="sxs-lookup"><span data-stu-id="69aba-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="69aba-143">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="69aba-144">특정 Windows 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="69aba-145">특정 Linux/macOS 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="69aba-146">현재 디렉터리에 대해 설치된 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 로컬 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="69aba-147">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 최신 패치 버전(주 버전 `2` 및 부 버전 `0`)으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="69aba-148">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 지정된 범위 `(> 2.0.0 && < 2.1.4)` 내의 최하위 버전으로 업데이트합니다. `2.1.0` 버전이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aba-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="69aba-149">유의적 버전 범위에 관한 자세한 내용은 [NuGet 패키징 버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69aba-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="69aba-150">참조</span><span class="sxs-lookup"><span data-stu-id="69aba-150">See also</span></span>

- [<span data-ttu-id="69aba-151">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="69aba-151">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="69aba-152">유의적 버전</span><span class="sxs-lookup"><span data-stu-id="69aba-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="69aba-153">자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="69aba-153">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="69aba-154">자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="69aba-154">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
