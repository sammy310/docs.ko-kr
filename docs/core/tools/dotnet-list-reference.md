---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 43c4dbc94b33e717c6ba0a1c1c5317ac006f5bba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503707"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="c4f73-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c4f73-103">dotnet list reference</span></span>

<span data-ttu-id="c4f73-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="c4f73-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c4f73-105">name</span><span class="sxs-lookup"><span data-stu-id="c4f73-105">Name</span></span>

<span data-ttu-id="c4f73-106">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c4f73-107">개요</span><span class="sxs-lookup"><span data-stu-id="c4f73-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="c4f73-108">설명</span><span class="sxs-lookup"><span data-stu-id="c4f73-108">Description</span></span>

<span data-ttu-id="c4f73-109">`dotnet list reference` 명령은 지정된 프로젝트 또는 솔루션에 대한 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="c4f73-110">인수</span><span class="sxs-lookup"><span data-stu-id="c4f73-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="c4f73-111">참조를 나열하기 위해 사용할 프로젝트 또는 솔루션 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="c4f73-112">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="c4f73-113">옵션</span><span class="sxs-lookup"><span data-stu-id="c4f73-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c4f73-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c4f73-115">예</span><span class="sxs-lookup"><span data-stu-id="c4f73-115">Examples</span></span>

* <span data-ttu-id="c4f73-116">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="c4f73-117">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c4f73-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
