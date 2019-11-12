---
title: dotnet sln 명령
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191829"
---
# <a name="dotnet-sln"></a><span data-ttu-id="0667e-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="0667e-103">dotnet sln</span></span>

<span data-ttu-id="0667e-104">**이 문서 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0667e-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="0667e-105">name</span><span class="sxs-lookup"><span data-stu-id="0667e-105">Name</span></span>

<span data-ttu-id="0667e-106">`dotnet sln` - .NET Core 솔루션 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0667e-107">개요</span><span class="sxs-lookup"><span data-stu-id="0667e-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="0667e-108">설명</span><span class="sxs-lookup"><span data-stu-id="0667e-108">Description</span></span>

<span data-ttu-id="0667e-109">`dotnet sln` 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="0667e-110">`dotnet sln` 명령을 사용하려면 솔루션 파일이 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="0667e-111">하나를 생성해야 하는 경우, 다음 예제와 같이 [dotnet new](dotnet-new.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="0667e-112">인수</span><span class="sxs-lookup"><span data-stu-id="0667e-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0667e-113">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-113">The solution file to use.</span></span> <span data-ttu-id="0667e-114">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="0667e-115">디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="0667e-116">옵션</span><span class="sxs-lookup"><span data-stu-id="0667e-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0667e-117">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="0667e-118">명령</span><span class="sxs-lookup"><span data-stu-id="0667e-118">Commands</span></span>

### `add`

<span data-ttu-id="0667e-119">솔루션 파일에 하나 이상의 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0667e-120">개요</span><span class="sxs-lookup"><span data-stu-id="0667e-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0667e-121">인수</span><span class="sxs-lookup"><span data-stu-id="0667e-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0667e-122">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-122">The solution file to use.</span></span> <span data-ttu-id="0667e-123">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="0667e-124">디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0667e-125">솔루션에 추가할 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="0667e-126">공백으로 구분된 다른 경로를 추가하여 여러 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="0667e-127">Unix/Linux 셸 [GLOB 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0667e-128">옵션</span><span class="sxs-lookup"><span data-stu-id="0667e-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0667e-129">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="0667e-130">솔루션 폴더를 만드는 대신, 솔루션의 루트에 프로젝트를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="0667e-131">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="0667e-132">프로젝트를 추가하려는 대상 솔루션 폴더 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="0667e-133">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="0667e-134">솔루션 파일에서 하나 이상의 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0667e-135">개요</span><span class="sxs-lookup"><span data-stu-id="0667e-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0667e-136">인수</span><span class="sxs-lookup"><span data-stu-id="0667e-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0667e-137">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-137">The solution file to use.</span></span> <span data-ttu-id="0667e-138">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="0667e-139">디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0667e-140">솔루션에서 제거할 프로젝트 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="0667e-141">공백으로 구분된 다른 경로를 추가하여 여러 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="0667e-142">Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0667e-143">옵션</span><span class="sxs-lookup"><span data-stu-id="0667e-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0667e-144">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="0667e-145">솔루션 파일의 모든 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0667e-146">개요</span><span class="sxs-lookup"><span data-stu-id="0667e-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a><span data-ttu-id="0667e-147">인수</span><span class="sxs-lookup"><span data-stu-id="0667e-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0667e-148">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-148">The solution file to use.</span></span> <span data-ttu-id="0667e-149">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="0667e-150">디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="0667e-151">옵션</span><span class="sxs-lookup"><span data-stu-id="0667e-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0667e-152">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0667e-153">예</span><span class="sxs-lookup"><span data-stu-id="0667e-153">Examples</span></span>

<span data-ttu-id="0667e-154">솔루션에 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-154">Add a C# project to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

<span data-ttu-id="0667e-155">솔루션에서 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-155">Remove a C# project from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

<span data-ttu-id="0667e-156">솔루션에 여러 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-156">Add multiple C# projects to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="0667e-157">솔루션에서 여러 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0667e-157">Remove multiple C# projects from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="0667e-158">와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다(Unix/Linux만 해당).</span><span class="sxs-lookup"><span data-stu-id="0667e-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

<span data-ttu-id="0667e-159">와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다(Unix/Linux만 해당).</span><span class="sxs-lookup"><span data-stu-id="0667e-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
