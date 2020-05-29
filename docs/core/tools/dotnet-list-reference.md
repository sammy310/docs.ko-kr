---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802760"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="969cb-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="969cb-103">dotnet list reference</span></span>

<span data-ttu-id="969cb-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="969cb-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="969cb-105">이름</span><span class="sxs-lookup"><span data-stu-id="969cb-105">Name</span></span>

<span data-ttu-id="969cb-106">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="969cb-107">개요</span><span class="sxs-lookup"><span data-stu-id="969cb-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="969cb-108">설명</span><span class="sxs-lookup"><span data-stu-id="969cb-108">Description</span></span>

<span data-ttu-id="969cb-109">`dotnet list reference` 명령은 지정한 프로젝트에 대해 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="969cb-110">인수</span><span class="sxs-lookup"><span data-stu-id="969cb-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="969cb-111">작동할 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-111">The project file to operate on.</span></span> <span data-ttu-id="969cb-112">파일이 지정되지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="969cb-113">옵션</span><span class="sxs-lookup"><span data-stu-id="969cb-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="969cb-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="969cb-115">예</span><span class="sxs-lookup"><span data-stu-id="969cb-115">Examples</span></span>

* <span data-ttu-id="969cb-116">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="969cb-117">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="969cb-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
