---
title: dotnet sln 명령
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543484"
---
# <a name="dotnet-sln"></a><span data-ttu-id="0167e-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="0167e-103">dotnet sln</span></span>

<span data-ttu-id="0167e-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0167e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0167e-105">이름</span><span class="sxs-lookup"><span data-stu-id="0167e-105">Name</span></span>

<span data-ttu-id="0167e-106">`dotnet sln` - .NET Core 솔루션 파일의 프로젝트를 나열하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0167e-107">개요</span><span class="sxs-lookup"><span data-stu-id="0167e-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="0167e-108">설명</span><span class="sxs-lookup"><span data-stu-id="0167e-108">Description</span></span>

<span data-ttu-id="0167e-109">`dotnet sln` 명령은 솔루션 파일의 프로젝트를 나열 및 수정하는 간편한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="0167e-110">`dotnet sln` 명령을 사용하려면 솔루션 파일이 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="0167e-111">파일을 생성해야 하는 경우, 다음 예제와 같이 [dotnet new](dotnet-new.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="0167e-112">인수</span><span class="sxs-lookup"><span data-stu-id="0167e-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0167e-113">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-113">The solution file to use.</span></span> <span data-ttu-id="0167e-114">이 인수를 생략하면 명령은 현재 디렉터리에서 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="0167e-115">솔루션 파일이 없거나 여러 개 있는 경우 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="0167e-116">옵션</span><span class="sxs-lookup"><span data-stu-id="0167e-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0167e-117">명령을 사용하는 방법에 대한 설명을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="0167e-118">명령</span><span class="sxs-lookup"><span data-stu-id="0167e-118">Commands</span></span>

### `list`

<span data-ttu-id="0167e-119">솔루션 파일의 모든 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0167e-120">개요</span><span class="sxs-lookup"><span data-stu-id="0167e-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0167e-121">인수</span><span class="sxs-lookup"><span data-stu-id="0167e-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0167e-122">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-122">The solution file to use.</span></span> <span data-ttu-id="0167e-123">이 인수를 생략하면 명령은 현재 디렉터리에서 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="0167e-124">솔루션 파일이 없거나 여러 개 있는 경우 명령이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="0167e-125">옵션</span><span class="sxs-lookup"><span data-stu-id="0167e-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0167e-126">명령을 사용하는 방법에 대한 설명을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="0167e-127">솔루션 파일에 하나 이상의 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0167e-128">개요</span><span class="sxs-lookup"><span data-stu-id="0167e-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0167e-129">인수</span><span class="sxs-lookup"><span data-stu-id="0167e-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0167e-130">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-130">The solution file to use.</span></span> <span data-ttu-id="0167e-131">지정되지 않은 경우 이 명령은 현재 디렉터리를 검색하고, 여러 솔루션 파일이 있을 경우 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0167e-132">솔루션에 추가할 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="0167e-133">Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0167e-134">옵션</span><span class="sxs-lookup"><span data-stu-id="0167e-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0167e-135">명령을 사용하는 방법에 대한 설명을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="0167e-136">솔루션 폴더를 만드는 대신, 솔루션의 루트에 프로젝트를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="0167e-137">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="0167e-138">프로젝트를 추가하려는 대상 솔루션 폴더 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="0167e-139">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="0167e-140">솔루션 파일에서 하나 이상의 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0167e-141">개요</span><span class="sxs-lookup"><span data-stu-id="0167e-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0167e-142">인수</span><span class="sxs-lookup"><span data-stu-id="0167e-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0167e-143">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-143">The solution file to use.</span></span> <span data-ttu-id="0167e-144">지정되지 않은 경우 이 명령은 현재 디렉터리를 검색하고, 여러 솔루션 파일이 있을 경우 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0167e-145">솔루션에 추가할 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="0167e-146">Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0167e-147">옵션</span><span class="sxs-lookup"><span data-stu-id="0167e-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0167e-148">명령을 사용하는 방법에 대한 설명을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0167e-149">예</span><span class="sxs-lookup"><span data-stu-id="0167e-149">Examples</span></span>

- <span data-ttu-id="0167e-150">솔루션의 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="0167e-151">솔루션에 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="0167e-152">솔루션에서 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="0167e-153">솔루션의 루트에 여러 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="0167e-154">솔루션에 여러 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="0167e-155">솔루션에서 여러 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0167e-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="0167e-156">와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다(Unix/Linux만 해당).</span><span class="sxs-lookup"><span data-stu-id="0167e-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="0167e-157">와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다(Unix/Linux만 해당).</span><span class="sxs-lookup"><span data-stu-id="0167e-157">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
