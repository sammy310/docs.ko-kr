---
title: dotnet tool list 명령
description: dotnet tool list 명령은 컴퓨터에 설치된 .NET Core 도구를 나열합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463354"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="f1d56-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="f1d56-103">dotnet tool list</span></span>

<span data-ttu-id="f1d56-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f1d56-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f1d56-105">이름</span><span class="sxs-lookup"><span data-stu-id="f1d56-105">Name</span></span>

<span data-ttu-id="f1d56-106">`dotnet tool list` - 컴퓨터에 현재 설치되어 있는 지정된 유형의 모든 [.NET Core 도구](global-tools.md)를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f1d56-107">개요</span><span class="sxs-lookup"><span data-stu-id="f1d56-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="f1d56-108">설명</span><span class="sxs-lookup"><span data-stu-id="f1d56-108">Description</span></span>

<span data-ttu-id="f1d56-109">`dotnet tool list` 명령은 컴퓨터에 설치된 모든 .NET Core 전역, 도구 경로 또는 로컬 도구를 나열하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="f1d56-110">이 명령은 패키지 이름, 설치된 버전 및 도구 명령을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="f1d56-111">이 명령을 사용하려면 다음 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="f1d56-112">기본 위치에 설치된 전역 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-112">A global tool installed in the default location.</span></span> <span data-ttu-id="f1d56-113">`--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-113">Use the `--global` option</span></span>
* <span data-ttu-id="f1d56-114">사용자 지정 위치에 설치된 전역 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="f1d56-115">`--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="f1d56-116">로컬 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-116">A local tool.</span></span> <span data-ttu-id="f1d56-117">`--global` 및 `--tool-path` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="f1d56-118">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f1d56-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="f1d56-119">옵션</span><span class="sxs-lookup"><span data-stu-id="f1d56-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="f1d56-120">사용자 수준 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-120">Lists user-wide global tools.</span></span> <span data-ttu-id="f1d56-121">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f1d56-122">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f1d56-123">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="f1d56-124">전역 도구를 찾을 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="f1d56-125">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="f1d56-126">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f1d56-127">`--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="f1d56-128">예</span><span class="sxs-lookup"><span data-stu-id="f1d56-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="f1d56-129">사용자 수준에서 컴퓨터에 설치된 모든 전역 도구를 나열합니다(현재 사용자 프로필).</span><span class="sxs-lookup"><span data-stu-id="f1d56-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="f1d56-130">특정 Windows 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="f1d56-131">특정 Linux/macOS 디렉터리의 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="f1d56-132">현재 디렉터리에서 사용할 수 있는 모든 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d56-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1d56-133">참조</span><span class="sxs-lookup"><span data-stu-id="f1d56-133">See also</span></span>

- [<span data-ttu-id="f1d56-134">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="f1d56-134">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="f1d56-135">자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="f1d56-135">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="f1d56-136">자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="f1d56-136">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
