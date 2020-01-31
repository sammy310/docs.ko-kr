---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 06/26/2019
ms.openlocfilehash: 496cbcd8fa4d921e30b363904ad0273bd5ebacd5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733228"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="d3f7e-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="d3f7e-103">dotnet list reference</span></span>

<span data-ttu-id="d3f7e-104">**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d3f7e-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="d3f7e-105">이름</span><span class="sxs-lookup"><span data-stu-id="d3f7e-105">Name</span></span>

<span data-ttu-id="d3f7e-106">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d3f7e-107">개요</span><span class="sxs-lookup"><span data-stu-id="d3f7e-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="d3f7e-108">설명</span><span class="sxs-lookup"><span data-stu-id="d3f7e-108">Description</span></span>

<span data-ttu-id="d3f7e-109">`dotnet list reference` 명령은 지정된 프로젝트 또는 솔루션에 대한 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="d3f7e-110">인수</span><span class="sxs-lookup"><span data-stu-id="d3f7e-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="d3f7e-111">참조를 나열하기 위해 사용할 프로젝트 또는 솔루션 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="d3f7e-112">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="d3f7e-113">옵션</span><span class="sxs-lookup"><span data-stu-id="d3f7e-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="d3f7e-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d3f7e-115">예</span><span class="sxs-lookup"><span data-stu-id="d3f7e-115">Examples</span></span>

* <span data-ttu-id="d3f7e-116">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="d3f7e-117">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f7e-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
