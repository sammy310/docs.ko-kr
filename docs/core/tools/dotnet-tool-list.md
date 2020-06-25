---
title: dotnet tool list 명령
description: dotnet tool list 명령은 컴퓨터에 설치된 .NET Core 도구를 나열합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768276"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="b57ca-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="b57ca-103">dotnet tool list</span></span>

<span data-ttu-id="b57ca-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="b57ca-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b57ca-105">이름</span><span class="sxs-lookup"><span data-stu-id="b57ca-105">Name</span></span>

<span data-ttu-id="b57ca-106">`dotnet tool list` - 컴퓨터에 현재 설치되어 있는 지정된 유형의 모든 [.NET Core 도구](global-tools.md)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b57ca-107">개요</span><span class="sxs-lookup"><span data-stu-id="b57ca-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="b57ca-108">설명</span><span class="sxs-lookup"><span data-stu-id="b57ca-108">Description</span></span>

<span data-ttu-id="b57ca-109">`dotnet tool list` 명령을 사용하면 머신에 설치된 모든 .NET Core 전역, 도구 경로 또는 로컬 도구를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="b57ca-110">이 명령은 패키지 이름, 설치된 버전 및 도구 명령을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="b57ca-111">이 명령을 사용하려면 다음 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="b57ca-112">기본 위치에 설치된 전역 도구를 나열하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="b57ca-113">사용자 지정 위치에 설치된 전역 도구를 나열하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="b57ca-114">로컬 도구를 나열하려면</span><span class="sxs-lookup"><span data-stu-id="b57ca-114">To list local tools, A local tool.</span></span> <span data-ttu-id="b57ca-115">`--local` 옵션을 사용하거나 `--global`, `--tool-path` 및 `--local` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-115">use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="b57ca-116">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b57ca-116">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="b57ca-117">옵션</span><span class="sxs-lookup"><span data-stu-id="b57ca-117">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="b57ca-118">사용자 수준 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-118">Lists user-wide global tools.</span></span> <span data-ttu-id="b57ca-119">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="b57ca-120">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-120">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b57ca-121">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-121">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="b57ca-122">현재 디렉터리에 대한 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-122">Lists local tools for the current directory.</span></span> <span data-ttu-id="b57ca-123">`--global` 또는 `--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-123">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="b57ca-124">`--global` 및 `--tool-path`를 둘 다 생략하면 `--local`을 지정하지 않아도 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-124">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="b57ca-125">전역 도구를 찾을 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-125">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="b57ca-126">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-126">PATH can be absolute or relative.</span></span> <span data-ttu-id="b57ca-127">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-127">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="b57ca-128">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-128">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="b57ca-129">예</span><span class="sxs-lookup"><span data-stu-id="b57ca-129">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="b57ca-130">사용자 수준에서 컴퓨터에 설치된 모든 전역 도구를 나열합니다(현재 사용자 프로필).</span><span class="sxs-lookup"><span data-stu-id="b57ca-130">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="b57ca-131">특정 Windows 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-131">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="b57ca-132">특정 Linux/macOS 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-132">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="b57ca-133">**`dotnet tool list`** 또는 **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="b57ca-133">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="b57ca-134">현재 디렉터리에서 사용할 수 있는 모든 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b57ca-134">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="b57ca-135">참조</span><span class="sxs-lookup"><span data-stu-id="b57ca-135">See also</span></span>

- [<span data-ttu-id="b57ca-136">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="b57ca-136">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="b57ca-137">자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="b57ca-137">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="b57ca-138">자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="b57ca-138">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
