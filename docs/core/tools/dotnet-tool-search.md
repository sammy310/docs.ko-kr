---
title: dotnet tool search 명령
description: dotnet tool search 명령은 NuGet.org에 게시된 .NET 도구를 검색합니다.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634144"
---
# <a name="dotnet-tool-search"></a><span data-ttu-id="1d74e-103">dotnet tool search</span><span class="sxs-lookup"><span data-stu-id="1d74e-103">dotnet tool search</span></span>

<span data-ttu-id="1d74e-104">**이 문서의 적용 대상:** ✔️ .NET 5.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="1d74e-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1d74e-105">Name</span><span class="sxs-lookup"><span data-stu-id="1d74e-105">Name</span></span>

<span data-ttu-id="1d74e-106">`dotnet tool search` - NuGet에 게시된 모든 [.NET 도구](global-tools.md)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1d74e-107">개요</span><span class="sxs-lookup"><span data-stu-id="1d74e-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="1d74e-108">Description</span><span class="sxs-lookup"><span data-stu-id="1d74e-108">Description</span></span>

<span data-ttu-id="1d74e-109">`dotnet tool search` 명령은 NuGet에서 .NET 전역 도구, 도구 경로 또는 로컬 도구로 사용할 수 있는 도구를 검색하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="1d74e-110">이 명령은 도구 이름 및 메타데이터(예: 제목, 설명, 태그)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="1d74e-111">이 명령은 [NuGet 검색 API](/nuget/api/search-query-service-resource#search-for-packages)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="1d74e-112">`packageType=dotnettool`을 필터링하여 .NET 도구 패키지만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="1d74e-113">옵션</span><span class="sxs-lookup"><span data-stu-id="1d74e-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="1d74e-114">쿼리에서 자세한 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="1d74e-115">시험판 패키지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="1d74e-116">건너뛸 쿼리 결과 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="1d74e-117">페이지 매김에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="1d74e-118">표시할 쿼리 결과 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="1d74e-119">페이지 매김에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1d74e-120">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="1d74e-121">예</span><span class="sxs-lookup"><span data-stu-id="1d74e-121">Examples</span></span>

- <span data-ttu-id="1d74e-122">NuGet.org에서 패키지 이름 또는 설명에 “format”이 포함된 .NET 도구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="1d74e-123">출력은 다음 예와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="1d74e-124">NuGet.org에서 패키지 이름 또는 메타데이터에 “format”이 포함된 .NET 도구를 검색하고 첫 번째 결과만 표시하고 자세한 보기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="1d74e-125">출력은 다음 예와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d74e-125">The output looks like the following example:</span></span>

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a><span data-ttu-id="1d74e-126">참조</span><span class="sxs-lookup"><span data-stu-id="1d74e-126">See also</span></span>

- [<span data-ttu-id="1d74e-127">.NET 도구</span><span class="sxs-lookup"><span data-stu-id="1d74e-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="1d74e-128">자습서: .NET CLI를 사용하여 .NET 전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="1d74e-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="1d74e-129">자습서: .NET CLI를 사용하여 .NET 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="1d74e-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
