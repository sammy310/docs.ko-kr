---
title: dotnet remove reference 명령
description: dotnet remove reference 명령은 프로젝트 간 참조를 제거하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 92d36bbbde64d806abc8f223c5f08e3f3d79ce9d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463436"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="e77a4-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="e77a4-103">dotnet remove reference</span></span>

<span data-ttu-id="e77a4-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e77a4-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e77a4-105">name</span><span class="sxs-lookup"><span data-stu-id="e77a4-105">Name</span></span>

<span data-ttu-id="e77a4-106">`dotnet remove reference` - 프로젝트 간 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e77a4-107">개요</span><span class="sxs-lookup"><span data-stu-id="e77a4-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>] <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a><span data-ttu-id="e77a4-108">설명</span><span class="sxs-lookup"><span data-stu-id="e77a4-108">Description</span></span>

<span data-ttu-id="e77a4-109">`dotnet remove reference` 명령은 프로젝트에서 프로젝트 참조를 제거하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="e77a4-110">인수</span><span class="sxs-lookup"><span data-stu-id="e77a4-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="e77a4-111">대상 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-111">Target project file.</span></span> <span data-ttu-id="e77a4-112">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="e77a4-113">제거할 프로젝트 간(P2P) 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="e77a4-114">하나 또는 여러 프로젝트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="e77a4-115">Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="e77a4-116">옵션</span><span class="sxs-lookup"><span data-stu-id="e77a4-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="e77a4-117">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e77a4-118">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="e77a4-119">예</span><span class="sxs-lookup"><span data-stu-id="e77a4-119">Examples</span></span>

- <span data-ttu-id="e77a4-120">지정한 프로젝트에서 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="e77a4-121">현재 디렉터리의 프로젝트에서 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="e77a4-122">Unix/Linux에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e77a4-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
