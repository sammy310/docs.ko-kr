---
title: dotnet nuget locals 명령
description: dotnet nuget locals 명령은 http-request 캐시, 임시 캐시 또는 컴퓨터 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 0a9fd7876aa4d1907eb37e6bac54295d938d36d3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632418"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="9392b-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="9392b-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9392b-104">name</span><span class="sxs-lookup"><span data-stu-id="9392b-104">Name</span></span>

<span data-ttu-id="9392b-105">`dotnet nuget locals` - 로컬 NuGet 리소스를 지우거나 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9392b-106">개요</span><span class="sxs-lookup"><span data-stu-id="9392b-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9392b-107">설명</span><span class="sxs-lookup"><span data-stu-id="9392b-107">Description</span></span>

<span data-ttu-id="9392b-108">`dotnet nuget locals` 명령은 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더에서 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="9392b-109">인수</span><span class="sxs-lookup"><span data-stu-id="9392b-109">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="9392b-110">나열하거나 지울 캐시 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-110">The cache location to list or clear.</span></span> <span data-ttu-id="9392b-111">다음 값 중 하나를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-111">It accepts one of the following values:</span></span>

  * <span data-ttu-id="9392b-112">`all` - 지정된 작업이 모든 캐시 형식 즉, http-request 캐시, 전역 패키지 캐시 및 임시 캐시에 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="9392b-113">`http-cache` - 지정된 작업이 http-request 캐시에만 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="9392b-114">다른 캐시 위치는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-114">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="9392b-115">`global-packages` - 지정된 작업이 전역 패키지 캐시에만 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="9392b-116">다른 캐시 위치는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-116">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="9392b-117">`temp` - 지정된 작업이 임시 캐시에만 적용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="9392b-118">다른 캐시 위치는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="9392b-119">옵션</span><span class="sxs-lookup"><span data-stu-id="9392b-119">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="9392b-120">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-120">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="9392b-121">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-121">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="9392b-122">지우기 옵션은 지정된 캐시 유형에 지우기 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="9392b-123">캐시 디렉터리의 콘텐츠는 재귀적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="9392b-124">실행 중인 사용자/그룹에게 캐시 디렉터리의 파일에 대한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="9392b-125">그렇지 않은 경우에는 지우지 않은 파일/폴더가 있음을 나타내는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="9392b-126">목록 옵션은 지정된 캐시 형식의 위치를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="9392b-127">예제</span><span class="sxs-lookup"><span data-stu-id="9392b-127">Examples</span></span>

* <span data-ttu-id="9392b-128">모든 로컬 캐시 디렉터리(http-cache 디렉터리, 전역 패키지 캐시 디렉터리 및 임시 캐시 디렉터리)의 경로를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals –l all
  ```

* <span data-ttu-id="9392b-129">로컬 http-cache 디렉터리의 경로를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-129">Displays the path for the local http-cache directory:</span></span>

  ```console
  dotnet nuget locals --list http-cache
  ```

* <span data-ttu-id="9392b-130">모든 로컬 캐시 디렉터리(http-cache 디렉터리, 전역 패키지 캐시 디렉터리 및 임시 캐시 디렉터리)에서 모든 파일을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals --clear all
  ```

* <span data-ttu-id="9392b-131">로컬 글로벌 패키지 캐시 디렉터리에 있는 모든 파일을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-131">Clears all files in local global-packages cache directory:</span></span>

  ```console
  dotnet nuget locals -c global-packages
  ```

* <span data-ttu-id="9392b-132">로컬 임시 캐시 디렉터리에 있는 모든 파일을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9392b-132">Clears all files in local temporary cache directory:</span></span>

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a><span data-ttu-id="9392b-133">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9392b-133">Troubleshooting</span></span>

<span data-ttu-id="9392b-134">`dotnet nuget locals` 명령을 사용하는 동안 가장 일반적으로 나타나는 문제와 오류에 대한 자세한 내용은 [NuGet 캐시 관리](/nuget/consume-packages/managing-the-nuget-cache)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9392b-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
