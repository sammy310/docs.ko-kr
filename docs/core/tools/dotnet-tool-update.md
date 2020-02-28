---
title: dotnet tool update 명령
description: dotnet tool update 명령은 컴퓨터에서 지정된 .NET Core 도구를 업데이트합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 50bb366fedfb0ea69b8b6007ff89e366b4f689de
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543419"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="d9725-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="d9725-103">dotnet tool update</span></span>

<span data-ttu-id="d9725-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d9725-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d9725-105">이름</span><span class="sxs-lookup"><span data-stu-id="d9725-105">Name</span></span>

<span data-ttu-id="d9725-106">`dotnet tool update` - 컴퓨터에서 지정된 [.NET Core 도구](global-tools.md)를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d9725-107">개요</span><span class="sxs-lookup"><span data-stu-id="d9725-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="d9725-108">설명</span><span class="sxs-lookup"><span data-stu-id="d9725-108">Description</span></span>

<span data-ttu-id="d9725-109">`dotnet tool update` 명령은 컴퓨터의 .NET Core 도구를 패키지의 안정적인 최신 버전으로 업데이트하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="d9725-110">이 명령은 도구를 제거하고 다시 설치하여 효과적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="d9725-111">이 명령을 사용하려면 다음 옵션 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="d9725-112">기본 위치에 설치된 전역 도구를 업데이트하려면 `--global` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="d9725-113">사용자 지정 위치에 설치된 전역 도구를 업데이트하려면 `--tool-path` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="d9725-114">로컬 도구를 업데이트하려면 `--global` 및 `--tool-path` 옵션을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="d9725-115">**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d9725-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="d9725-116">인수</span><span class="sxs-lookup"><span data-stu-id="d9725-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="d9725-117">업데이트할 .NET Core 전역 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="d9725-118">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="d9725-119">옵션</span><span class="sxs-lookup"><span data-stu-id="d9725-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="d9725-120">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d9725-121">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="d9725-122">도구를 업데이트할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="d9725-123">업데이트가 사용자 수준 도구에 대한 것임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="d9725-124">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="d9725-125">`--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="d9725-126">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="d9725-127">전역 도구가 설치되는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="d9725-128">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="d9725-129">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="d9725-130">`--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d9725-131">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d9725-132">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d9725-133">예</span><span class="sxs-lookup"><span data-stu-id="d9725-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="d9725-134">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="d9725-135">특정 Windows 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="d9725-136">특정 Linux/macOS 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="d9725-137">현재 디렉터리에 대해 설치된 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 로컬 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9725-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9725-138">참조</span><span class="sxs-lookup"><span data-stu-id="d9725-138">See also</span></span>

- [<span data-ttu-id="d9725-139">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="d9725-139">.NET Core tools</span></span>](global-tools.md)
