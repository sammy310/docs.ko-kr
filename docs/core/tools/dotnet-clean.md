---
title: dotnet clean 명령
description: dotnet clean 명령은 현재 디렉터리를 정리합니다.
ms.date: 04/14/2019
ms.openlocfilehash: fa19f1b041e4031082f928135395a5f06ce702e9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631814"
---
# <a name="dotnet-clean"></a><span data-ttu-id="cb7f9-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="cb7f9-103">dotnet clean</span></span>

<span data-ttu-id="cb7f9-104">**이 항목 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="cb7f9-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="cb7f9-105">name</span><span class="sxs-lookup"><span data-stu-id="cb7f9-105">Name</span></span>

<span data-ttu-id="cb7f9-106">`dotnet clean` - 프로젝트의 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb7f9-107">개요</span><span class="sxs-lookup"><span data-stu-id="cb7f9-107">Synopsis</span></span>

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="cb7f9-108">설명</span><span class="sxs-lookup"><span data-stu-id="cb7f9-108">Description</span></span>

<span data-ttu-id="cb7f9-109">`dotnet clean` 명령은 이전 빌드의 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="cb7f9-110">이 명령은 [MSBuild 대상](/visualstudio/msbuild/msbuild-targets)으로 구현되므로 명령이 실행될 때 프로젝트가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="cb7f9-111">빌드 중 생성된 출력만 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="cb7f9-112">중간(*obj*) 및 최종 출력(*bin*) 폴더가 모두 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="cb7f9-113">인수</span><span class="sxs-lookup"><span data-stu-id="cb7f9-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="cb7f9-114">정리할 MSBuild 프로젝트 또는 솔루션</span><span class="sxs-lookup"><span data-stu-id="cb7f9-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="cb7f9-115">프로젝트 또는 솔루션 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj* 또는 *sln*으로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="cb7f9-116">옵션</span><span class="sxs-lookup"><span data-stu-id="cb7f9-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="cb7f9-117">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-117">Defines the build configuration.</span></span> <span data-ttu-id="cb7f9-118">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-118">The default value is `Debug`.</span></span> <span data-ttu-id="cb7f9-119">이 옵션은 빌드 시에 지정한 경우에만 정리 시에도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="cb7f9-120">빌드 시 지정한 [프레임워크](../../standard/frameworks.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="cb7f9-121">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="cb7f9-122">빌드 시에 프레임워크를 지정한 경우 정리할 때도 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="cb7f9-123">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="cb7f9-124">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="cb7f9-125">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-125">For example, to complete authentication.</span></span> <span data-ttu-id="cb7f9-126">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-126">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="cb7f9-127">정리할 빌드 아티팩트를 포함하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-127">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="cb7f9-128">프로젝트를 빌드할 때 프레임워크를 지정한 경우 `-f|--framework <FRAMEWORK>` 스위치와 출력 디렉터리 스위치를 함께 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-128">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="cb7f9-129">지정된 런타임의 출력 폴더를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-129">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="cb7f9-130">[자체 포함된 배포](../deploying/index.md#self-contained-deployments-scd)가 만들어진 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-130">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="cb7f9-131">.NET Core 2.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-131">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="cb7f9-132">MSBuild의 자세한 정도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-132">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="cb7f9-133">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-133">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cb7f9-134">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-134">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="cb7f9-135">예제</span><span class="sxs-lookup"><span data-stu-id="cb7f9-135">Examples</span></span>

* <span data-ttu-id="cb7f9-136">프로젝트의 기본 빌드 정리:</span><span class="sxs-lookup"><span data-stu-id="cb7f9-136">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="cb7f9-137">릴리스 구성을 사용하여 빌드한 프로젝트 정리:</span><span class="sxs-lookup"><span data-stu-id="cb7f9-137">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```
