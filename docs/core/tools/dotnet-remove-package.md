---
title: dotnet remove package 명령
description: dotnet remove package 명령은 프로젝트에 대한 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503637"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="0896f-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="0896f-103">dotnet remove package</span></span>

<span data-ttu-id="0896f-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0896f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0896f-105">name</span><span class="sxs-lookup"><span data-stu-id="0896f-105">Name</span></span>

<span data-ttu-id="0896f-106">`dotnet remove package` - 프로젝트 파일에서 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0896f-107">개요</span><span class="sxs-lookup"><span data-stu-id="0896f-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="0896f-108">설명</span><span class="sxs-lookup"><span data-stu-id="0896f-108">Description</span></span>

<span data-ttu-id="0896f-109">`dotnet remove package` 명령은 프로젝트에서 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="0896f-110">인수</span><span class="sxs-lookup"><span data-stu-id="0896f-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="0896f-111">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-111">Specifies the project file.</span></span> <span data-ttu-id="0896f-112">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="0896f-113">제거할 패키지 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="0896f-114">옵션</span><span class="sxs-lookup"><span data-stu-id="0896f-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0896f-115">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0896f-116">예</span><span class="sxs-lookup"><span data-stu-id="0896f-116">Examples</span></span>

- <span data-ttu-id="0896f-117">현재 디렉터리의 프로젝트에서 `Newtonsoft.Json` NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0896f-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
