---
title: dotnet add reference 명령
description: dotnet add reference 명령은 프로젝트 간 참조를 추가하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: b261e24ed6a9d5bd489d317d2663b1420b5c34ff
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158322"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="4e644-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="4e644-103">dotnet add reference</span></span>

<span data-ttu-id="4e644-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="4e644-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4e644-105">이름</span><span class="sxs-lookup"><span data-stu-id="4e644-105">Name</span></span>

<span data-ttu-id="4e644-106">`dotnet add reference` - 프로젝트 간(P2P) 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e644-107">개요</span><span class="sxs-lookup"><span data-stu-id="4e644-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="4e644-108">설명</span><span class="sxs-lookup"><span data-stu-id="4e644-108">Description</span></span>

<span data-ttu-id="4e644-109">`dotnet add reference` 명령은 프로젝트에 프로젝트 참조를 추가하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="4e644-110">명령을 실행한 후 `<ProjectReference>` 요소가 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="4e644-111">인수</span><span class="sxs-lookup"><span data-stu-id="4e644-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="4e644-112">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-112">Specifies the project file.</span></span> <span data-ttu-id="4e644-113">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="4e644-114">추가할 프로젝트 간(P2P) 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="4e644-115">하나 이상의 프로젝트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-115">Specify one or more projects.</span></span> <span data-ttu-id="4e644-116">Unix/Linux 기반 시스템에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="4e644-117">옵션</span><span class="sxs-lookup"><span data-stu-id="4e644-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="4e644-118">TFM 형식을 사용하여 특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md) using the TFM format.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4e644-119">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="4e644-120">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(일반적으로 인증을 완료하는 데 사용됨).</span><span class="sxs-lookup"><span data-stu-id="4e644-120">Allows the command to stop and wait for user input or action (typically used to complete authentication).</span></span> <span data-ttu-id="4e644-121">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="4e644-122">예</span><span class="sxs-lookup"><span data-stu-id="4e644-122">Examples</span></span>

- <span data-ttu-id="4e644-123">프로젝트 참조 추가:</span><span class="sxs-lookup"><span data-stu-id="4e644-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="4e644-124">현재 디렉터리의 프로젝트에 여러 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e644-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="4e644-125">Linux/Unix에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조 추가:</span><span class="sxs-lookup"><span data-stu-id="4e644-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
