---
title: dotnet list package 명령
description: ‘dotnet list package’ 명령은 프로젝트 또는 솔루션에 대한 패키지 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 11/11/2020
ms.openlocfilehash: 684b73dec553a424252e1368c265847622fb7850
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189898"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="5d4d1-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="5d4d1-103">dotnet list package</span></span>

<span data-ttu-id="5d4d1-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.2 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="5d4d1-104">**This article applies to:** ✔️ .NET Core 2.2 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5d4d1-105">이름</span><span class="sxs-lookup"><span data-stu-id="5d4d1-105">Name</span></span>

<span data-ttu-id="5d4d1-106">`dotnet list package` - 프로젝트 또는 솔루션에 대한 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-106">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5d4d1-107">개요</span><span class="sxs-lookup"><span data-stu-id="5d4d1-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config <SOURCE>]
    [--deprecated]
    [--framework <FRAMEWORK>] [--highest-minor] [--highest-patch]
    [--include-prerelease] [--include-transitive] [--interactive]
    [--outdated] [--source <SOURCE>] [-v|--verbosity <LEVEL>]

dotnet list package -h|--help
```

## <a name="description"></a><span data-ttu-id="5d4d1-108">설명</span><span class="sxs-lookup"><span data-stu-id="5d4d1-108">Description</span></span>

<span data-ttu-id="5d4d1-109">`dotnet list package` 명령은 특정 프로젝트 또는 솔루션에 대한 모든 NuGet 패키지 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-109">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="5d4d1-110">이 명령을 처리하는 데 필요한 자산을 포함하려면 먼저 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-110">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="5d4d1-111">다음 예제에서는 [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 프로젝트에 대한 `dotnet list package` 명령의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-111">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="5d4d1-112">**요청됨** 열은 프로젝트 파일에 지정된 패키지 버전을 나타내고 이 버전은 범위일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-112">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="5d4d1-113">**해결됨** 열에는 프로젝트가 현재 사용 중이고 항상 단일 값인 버전이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-113">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="5d4d1-114">이름 오른쪽에 `(A)`를 표시하는 패키지는 프로젝트 설정(`Sdk` 형식, `<TargetFramework>` 또는 `<TargetFrameworks>` 속성)에서 유추된 암시적 패키지 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-114">The packages displaying an `(A)` right next to their names represent implicit package references that are inferred from your project settings (`Sdk` type, or `<TargetFramework>` or `<TargetFrameworks>` property).</span></span>

<span data-ttu-id="5d4d1-115">`--outdated` 옵션을 사용하여 프로젝트에서 사용 중인 패키지에 사용 가능한 최신 버전이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-115">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="5d4d1-116">기본적으로 해결된 버전이 사전 릴리스 버전이 아닌 경우 `--outdated`는 안정적인 최신 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-116">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="5d4d1-117">최신 버전을 나열할 때 사전 릴리스 버전을 포함하려면 `--include-prerelease` 옵션도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-117">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="5d4d1-118">다음 예제에서는 이전 예제와 동일한 프로젝트에 대한 `dotnet list package --outdated --include-prerelease` 명령의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-118">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

<span data-ttu-id="5d4d1-119">프로젝트에 전이적 종속성이 있는지 확인해야 하는 경우에는 `--include-transitive` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-119">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="5d4d1-120">다른 패키지에 의존하는 패키지를 프로젝트에 추가하면 전이적 종속성이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-120">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="5d4d1-121">다음 예제에서는 최상위 패키지 및 자신이 종속된 패키지를 표시하는, [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) 프로젝트에 대한 `dotnet list package --include-transitive` 명령 실행의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-121">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a><span data-ttu-id="5d4d1-122">인수</span><span class="sxs-lookup"><span data-stu-id="5d4d1-122">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="5d4d1-123">작업할 프로젝트 또는 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-123">The project or solution file to operate on.</span></span> <span data-ttu-id="5d4d1-124">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-124">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="5d4d1-125">둘 이상의 솔루션 또는 프로젝트가 있으면 오류가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-125">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="5d4d1-126">옵션</span><span class="sxs-lookup"><span data-stu-id="5d4d1-126">Options</span></span>

- **`--config <SOURCE>`**

  <span data-ttu-id="5d4d1-127">최신 패키지를 검색할 때 사용할 NuGet 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-127">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="5d4d1-128">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-128">Requires the `--outdated` option.</span></span>

- **`--deprecated`**

  <span data-ttu-id="5d4d1-129">사용되지 않는 패키지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-129">Displays packages that have been deprecated.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="5d4d1-130">지정된 [대상 프레임워크](../../standard/frameworks.md)에 적용 가능한 패키지만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-130">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="5d4d1-131">여러 프레임워크를 지정하려면 옵션을 여러 번 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-131">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="5d4d1-132">예를 들어 `--framework netcoreapp2.2 --framework netstandard2.0`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-132">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5d4d1-133">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-133">Prints out a short help for the command.</span></span>

- **`--highest-minor`**

  <span data-ttu-id="5d4d1-134">최신 패키지를 검색할 때 주 버전 번호가 일치하는 패키지만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-134">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="5d4d1-135">`--outdated` 또는 `--deprecated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-135">Requires the `--outdated` or `--deprecated` option.</span></span>

- **`--highest-patch`**

  <span data-ttu-id="5d4d1-136">최신 패키지를 검색할 때 주 및 부 버전 번호가 일치하는 패키지만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-136">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="5d4d1-137">`--outdated` 또는 `--deprecated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-137">Requires the `--outdated` or `--deprecated` option.</span></span>

- **`--include-prerelease`**

  <span data-ttu-id="5d4d1-138">최신 패키지를 검색할 때 사전 릴리스 버전을 가진 패키지를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-138">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="5d4d1-139">`--outdated` 또는 `--deprecated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-139">Requires the `--outdated` or `--deprecated` option.</span></span>

- **`--include-transitive`**

  <span data-ttu-id="5d4d1-140">최상위 패키지 이외에 전이적 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-140">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="5d4d1-141">이 옵션을 지정하면 최상위 패키지가 종속된 패키지 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-141">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

- **`--interactive`**

  <span data-ttu-id="5d4d1-142">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-142">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="5d4d1-143">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-143">For example, to complete authentication.</span></span> <span data-ttu-id="5d4d1-144">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-144">Available since .NET Core 3.0 SDK.</span></span>

- **`--outdated`**

  <span data-ttu-id="5d4d1-145">최신 버전을 사용할 수 있는 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-145">Lists packages that have newer versions available.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="5d4d1-146">최신 패키지를 검색할 때 사용할 NuGet 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-146">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="5d4d1-147">`--outdated` 또는 `--deprecated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-147">Requires the `--outdated` or `--deprecated` option.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5d4d1-148">MSBuild의 자세한 정도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-148">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="5d4d1-149">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="5d4d1-150">기본값은 `minimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-150">The default is `minimal`.</span></span>

## <a name="examples"></a><span data-ttu-id="5d4d1-151">예</span><span class="sxs-lookup"><span data-stu-id="5d4d1-151">Examples</span></span>

- <span data-ttu-id="5d4d1-152">특정 프로젝트의 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-152">List package references of a specific project:</span></span>

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- <span data-ttu-id="5d4d1-153">사전 릴리스 버전을 포함하여 최신 버전을 사용할 수 있는 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-153">List package references that have newer versions available, including prerelease versions:</span></span>

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- <span data-ttu-id="5d4d1-154">특정 대상 프레임워크에 대한 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4d1-154">List package references for a specific target framework:</span></span>

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
