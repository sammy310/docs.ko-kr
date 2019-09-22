---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117678"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="518df-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="518df-103">dotnet list reference</span></span>

<span data-ttu-id="518df-104">**이 항목 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="518df-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="518df-105">name</span><span class="sxs-lookup"><span data-stu-id="518df-105">Name</span></span>

<span data-ttu-id="518df-106">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="518df-107">개요</span><span class="sxs-lookup"><span data-stu-id="518df-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="518df-108">설명</span><span class="sxs-lookup"><span data-stu-id="518df-108">Description</span></span>

<span data-ttu-id="518df-109">`dotnet list reference` 명령은 지정된 프로젝트 또는 솔루션에 대한 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="518df-110">인수</span><span class="sxs-lookup"><span data-stu-id="518df-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="518df-111">참조를 나열하기 위해 사용할 프로젝트 또는 솔루션 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="518df-112">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="518df-113">옵션</span><span class="sxs-lookup"><span data-stu-id="518df-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="518df-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="518df-115">예제</span><span class="sxs-lookup"><span data-stu-id="518df-115">Examples</span></span>

* <span data-ttu-id="518df-116">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="518df-117">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="518df-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
