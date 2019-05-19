---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 12/03/2018
ms.openlocfilehash: c0b88c4a0af4469d7ddc9e0a9368bb1b2d9d20b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632403"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="4e832-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4e832-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4e832-104">name</span><span class="sxs-lookup"><span data-stu-id="4e832-104">Name</span></span>

<span data-ttu-id="4e832-105">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e832-106">개요</span><span class="sxs-lookup"><span data-stu-id="4e832-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="4e832-107">설명</span><span class="sxs-lookup"><span data-stu-id="4e832-107">Description</span></span>

<span data-ttu-id="4e832-108">`dotnet list reference` 명령은 지정된 프로젝트 또는 솔루션에 대한 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="4e832-109">인수</span><span class="sxs-lookup"><span data-stu-id="4e832-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="4e832-110">참조를 나열하기 위해 사용할 프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="4e832-111">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="4e832-112">옵션</span><span class="sxs-lookup"><span data-stu-id="4e832-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="4e832-113">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="4e832-114">예제</span><span class="sxs-lookup"><span data-stu-id="4e832-114">Examples</span></span>

* <span data-ttu-id="4e832-115">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="4e832-116">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4e832-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
