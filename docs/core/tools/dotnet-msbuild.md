---
title: dotnet msbuild 명령
description: dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803170"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="82fd7-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="82fd7-103">dotnet msbuild</span></span>

<span data-ttu-id="82fd7-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="82fd7-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="82fd7-105">이름</span><span class="sxs-lookup"><span data-stu-id="82fd7-105">Name</span></span>

<span data-ttu-id="82fd7-106">`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span> <span data-ttu-id="82fd7-107">참고: 솔루션 또는 프로젝트 파일이 여러 개인 경우 하나를 지정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-107">Note: A solution or project file may need to be specified if there are multiple.</span></span>

## <a name="synopsis"></a><span data-ttu-id="82fd7-108">개요</span><span class="sxs-lookup"><span data-stu-id="82fd7-108">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="82fd7-109">설명</span><span class="sxs-lookup"><span data-stu-id="82fd7-109">Description</span></span>

<span data-ttu-id="82fd7-110">`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-110">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="82fd7-111">이 명령은 SDK 스타일 프로젝트에 대해서만 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-111">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="82fd7-112">옵션은 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-112">The options are all the same.</span></span> <span data-ttu-id="82fd7-113">사용 가능한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="82fd7-113">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="82fd7-114">[dotnet build](dotnet-build.md) 명령은 `dotnet msbuild -restore`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-114">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore`.</span></span> <span data-ttu-id="82fd7-115">프로젝트를 빌드하지 않고 특정 대상을 실행하려는 경우 `dotnet build` 또는 `dotnet msbuild`를 사용하고 대상을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-115">When you don't want to build the project and you have a specific target you want to run, use `dotnet build` or `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="82fd7-116">예</span><span class="sxs-lookup"><span data-stu-id="82fd7-116">Examples</span></span>

- <span data-ttu-id="82fd7-117">프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="82fd7-118">릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="82fd7-119">게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="82fd7-120">SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82fd7-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
