---
title: dotnet msbuild 명령
description: dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다.
ms.date: 12/03/2018
ms.openlocfilehash: 983fae6f4ecf875da0b155a668009984b5df50de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632023"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="1c339-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c339-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1c339-104">name</span><span class="sxs-lookup"><span data-stu-id="1c339-104">Name</span></span>

<span data-ttu-id="1c339-105">`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c339-106">개요</span><span class="sxs-lookup"><span data-stu-id="1c339-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="1c339-107">설명</span><span class="sxs-lookup"><span data-stu-id="1c339-107">Description</span></span>

<span data-ttu-id="1c339-108">`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="1c339-109">이 명령은 SDK 스타일 프로젝트에 대해서만 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="1c339-110">옵션은 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-110">The options are all the same.</span></span> <span data-ttu-id="1c339-111">사용 가능한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1c339-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="1c339-112">[dotnet build](dotnet-build.md) 명령은 `dotnet msbuild -restore -target:Build`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="1c339-113">`dotnet build`가 프로젝트 빌드에 더 일반적으로 사용되지만 `dotnet msbuild`는 제어를 강화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="1c339-114">예를 들어 빌드 대상을 실행하지 않고 실행하려는 특정 대상이 있는 경우 `dotnet msbuild`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="1c339-115">예제</span><span class="sxs-lookup"><span data-stu-id="1c339-115">Examples</span></span>

* <span data-ttu-id="1c339-116">프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="1c339-117">릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="1c339-118">게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="1c339-119">SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c339-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```
