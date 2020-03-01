---
title: dotnet tool uninstall 명령
description: dotnet tool uninstall 명령은 컴퓨터에서 지정된 .NET Core 도구를 제거합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 7a15c169c73cf5a743e0fa6f47645d6bccedbde3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157047"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="e623d-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="e623d-103">dotnet tool uninstall</span></span>

<span data-ttu-id="e623d-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e623d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e623d-105">이름</span><span class="sxs-lookup"><span data-stu-id="e623d-105">Name</span></span>

<span data-ttu-id="e623d-106">`dotnet tool uninstall` - 컴퓨터에서 지정된 [.NET Core 도구](global-tools.md)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e623d-107">개요</span><span class="sxs-lookup"><span data-stu-id="e623d-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="e623d-108">설명</span><span class="sxs-lookup"><span data-stu-id="e623d-108">Description</span></span>

<span data-ttu-id="e623d-109">`dotnet tool uninstall` 명령은 컴퓨터에서 .NET Core 도구를 제거하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="e623d-110">이 명령을 사용하려면 다음 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="e623d-111">기본 위치에 설치된 전역 도구를 제거하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="e623d-112">사용자 지정 위치에 설치된 전역 도구를 제거하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="e623d-113">로컬 도구를 제거하려면 `--global` 및 `--tool-path` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="e623d-114">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e623d-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="e623d-115">인수</span><span class="sxs-lookup"><span data-stu-id="e623d-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="e623d-116">제거할 .NET Core 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="e623d-117">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="e623d-118">옵션</span><span class="sxs-lookup"><span data-stu-id="e623d-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="e623d-119">사용자 수준 설치에서 제거할 도구임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="e623d-120">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="e623d-121">`--global` 및 `--tool-path` 옵션을 모두 생략하면 제거할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e623d-122">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="e623d-123">도구를 제거할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="e623d-124">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="e623d-125">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="e623d-126">`--global` 및 `--tool-path` 옵션을 모두 생략하면 제거할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="e623d-127">예</span><span class="sxs-lookup"><span data-stu-id="e623d-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="e623d-128">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="e623d-129">특정 Windows 디렉터리에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="e623d-130">특정 Linux/macOS 디렉터리에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="e623d-131">현재 디렉터리에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 로컬 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e623d-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="e623d-132">참조</span><span class="sxs-lookup"><span data-stu-id="e623d-132">See also</span></span>

- [<span data-ttu-id="e623d-133">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="e623d-133">.NET Core tools</span></span>](global-tools.md)
