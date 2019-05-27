---
title: dotnet list package 명령
description: ‘dotnet list package’ 명령은 프로젝트 또는 솔루션에 대한 패키지 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 04/09/2019
ms.openlocfilehash: 88ef3302a955eadc4167384312e4eb721dd496fb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631759"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="492df-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="492df-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="492df-104">name</span><span class="sxs-lookup"><span data-stu-id="492df-104">Name</span></span>

<span data-ttu-id="492df-105">`dotnet list package` - 프로젝트 또는 솔루션에 대한 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-105">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="492df-106">개요</span><span class="sxs-lookup"><span data-stu-id="492df-106">Synopsis</span></span>

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="492df-107">설명</span><span class="sxs-lookup"><span data-stu-id="492df-107">Description</span></span>

<span data-ttu-id="492df-108">`dotnet list package` 명령은 특정 프로젝트 또는 솔루션에 대한 모든 NuGet 패키지 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="492df-109">이 명령을 처리하는 데 필요한 자산을 포함하려면 먼저 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="492df-110">다음 예제에서는 [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 프로젝트에 대한 `dotnet list package` 명령의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492df-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="492df-111">**요청됨** 열은 프로젝트 파일에 지정된 패키지 버전을 나타내고 이 버전은 범위일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492df-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="492df-112">**해결됨** 열에는 프로젝트가 현재 사용 중이고 항상 단일 값인 버전이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="492df-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="492df-113">이름 오른쪽에 `(A)`를 표시하는 패키지는 프로젝트 설정(`Sdk` 형식, `<TargetFramework>` 또는 `<TargetFrameworks>` 속성 등)에서 유추된 [암시적 패키지 참조](csproj.md#implicit-package-references)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="492df-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="492df-114">`--outdated` 옵션을 사용하여 프로젝트에서 사용 중인 패키지에 사용 가능한 최신 버전이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="492df-115">기본적으로 해결된 버전이 사전 릴리스 버전이 아닌 경우 `--outdated`는 안정적인 최신 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="492df-116">최신 버전을 나열할 때 사전 릴리스 버전을 포함하려면 `--include-prerelease` 옵션도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="492df-117">다음 예제에서는 이전 예제와 동일한 프로젝트에 대한 `dotnet list package --outdated --include-prerelease` 명령의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492df-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="492df-118">프로젝트에 전이적 종속성이 있는지 확인해야 하는 경우에는 `--include-transitive` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="492df-119">다른 패키지에 의존하는 패키지를 프로젝트에 추가하면 전이적 종속성이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="492df-120">다음 예제에서는 최상위 패키지 및 자신이 종속된 패키지를 표시하는, [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) 프로젝트에 대한 `dotnet list package --include-transitive` 명령 실행의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492df-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="492df-121">인수</span><span class="sxs-lookup"><span data-stu-id="492df-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="492df-122">작업할 프로젝트 또는 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="492df-122">The project or solution file to operate on.</span></span> <span data-ttu-id="492df-123">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="492df-124">둘 이상의 솔루션 또는 프로젝트가 있으면 오류가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="492df-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="492df-125">옵션</span><span class="sxs-lookup"><span data-stu-id="492df-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="492df-126">최신 패키지를 검색할 때 사용할 NuGet 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="492df-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="492df-127">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="492df-128">지정된 [대상 프레임워크](../../standard/frameworks.md)에 적용 가능한 패키지만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="492df-129">여러 프레임워크를 지정하려면 옵션을 여러 번 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="492df-130">예: `--framework netcoreapp2.2 --framework netstandard2.0`</span><span class="sxs-lookup"><span data-stu-id="492df-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="492df-131">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="492df-132">최신 패키지를 검색할 때 주 버전 번호가 일치하는 패키지만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="492df-133">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="492df-134">최신 패키지를 검색할 때 주 및 부 버전 번호가 일치하는 패키지만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="492df-135">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="492df-136">최신 패키지를 검색할 때 사전 릴리스 버전을 가진 패키지를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="492df-137">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="492df-138">최상위 패키지 이외에 전이적 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="492df-139">이 옵션을 지정하면 최상위 패키지가 종속된 패키지 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="492df-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--outdated`**

  <span data-ttu-id="492df-140">최신 버전을 사용할 수 있는 패키지를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-140">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="492df-141">최신 패키지를 검색할 때 사용할 NuGet 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="492df-141">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="492df-142">`--outdated` 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-142">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="492df-143">예제</span><span class="sxs-lookup"><span data-stu-id="492df-143">Examples</span></span>

* <span data-ttu-id="492df-144">특정 프로젝트의 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-144">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="492df-145">사전 릴리스 버전을 포함하여 최신 버전을 사용할 수 있는 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-145">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="492df-146">특정 대상 프레임워크에 대한 패키지 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="492df-146">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
