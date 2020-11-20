---
title: dotnet tool list 명령
description: dotnet tool list 명령은 머신에 설치된 .NET 도구를 나열합니다.
ms.date: 02/14/2020
ms.openlocfilehash: d884f2c41834dd9704de3a8ca15417ba368fde4b
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634287"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="3cbaa-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="3cbaa-103">dotnet tool list</span></span>

<span data-ttu-id="3cbaa-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="3cbaa-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3cbaa-105">이름</span><span class="sxs-lookup"><span data-stu-id="3cbaa-105">Name</span></span>

<span data-ttu-id="3cbaa-106">`dotnet tool list` - 머신에 현재 설치되어 있는 지정된 유형의 모든 [.NET 도구](global-tools.md)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-106">`dotnet tool list` - Lists all [.NET tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3cbaa-107">개요</span><span class="sxs-lookup"><span data-stu-id="3cbaa-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="3cbaa-108">설명</span><span class="sxs-lookup"><span data-stu-id="3cbaa-108">Description</span></span>

<span data-ttu-id="3cbaa-109">`dotnet tool list` 명령은 머신에 설치된 모든 .NET 전역, 도구 경로 또는 로컬 도구를 나열하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-109">The `dotnet tool list` command provides a way for you to list all .NET global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="3cbaa-110">이 명령은 패키지 이름, 설치된 버전 및 도구 명령을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="3cbaa-111">이 명령을 사용하려면 다음 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="3cbaa-112">기본 위치에 설치된 전역 도구를 나열하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="3cbaa-113">사용자 지정 위치에 설치된 전역 도구를 나열하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="3cbaa-114">로컬 도구를 나열하려면 `--local` 옵션을 사용하거나 `--global`, `--tool-path` 및 `--local` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-114">To list local tools, use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="3cbaa-115">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="3cbaa-116">옵션</span><span class="sxs-lookup"><span data-stu-id="3cbaa-116">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="3cbaa-117">사용자 수준 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-117">Lists user-wide global tools.</span></span> <span data-ttu-id="3cbaa-118">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-118">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="3cbaa-119">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-119">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3cbaa-120">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-120">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="3cbaa-121">현재 디렉터리에 대한 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-121">Lists local tools for the current directory.</span></span> <span data-ttu-id="3cbaa-122">`--global` 또는 `--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-122">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="3cbaa-123">`--global` 및 `--tool-path`를 둘 다 생략하면 `--local`을 지정하지 않아도 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-123">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="3cbaa-124">전역 도구를 찾을 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="3cbaa-125">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="3cbaa-126">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="3cbaa-127">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="3cbaa-128">예</span><span class="sxs-lookup"><span data-stu-id="3cbaa-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="3cbaa-129">사용자 수준에서 컴퓨터에 설치된 모든 전역 도구를 나열합니다(현재 사용자 프로필).</span><span class="sxs-lookup"><span data-stu-id="3cbaa-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="3cbaa-130">특정 Windows 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="3cbaa-131">특정 Linux/macOS 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="3cbaa-132">**`dotnet tool list`** 또는 **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="3cbaa-132">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="3cbaa-133">현재 디렉터리에서 사용할 수 있는 모든 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-133">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cbaa-134">참조</span><span class="sxs-lookup"><span data-stu-id="3cbaa-134">See also</span></span>

- [<span data-ttu-id="3cbaa-135">.NET 도구</span><span class="sxs-lookup"><span data-stu-id="3cbaa-135">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="3cbaa-136">자습서: .NET CLI를 사용하여 .NET 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="3cbaa-136">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="3cbaa-137">자습서: .NET CLI를 사용하여 .NET 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="3cbaa-137">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
