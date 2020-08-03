---
title: dotnet tool restore 명령
description: dotnet tool restore 명령은 현재 디렉터리에 대한 범위에 있는 .NET Core 로컬 도구를 컴퓨터에 설치합니다.
ms.date: 02/14/2020
ms.openlocfilehash: ceef3274ec9d337f8c51009d5a8c27e808b14035
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302674"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="5f01f-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="5f01f-103">dotnet tool restore</span></span>

<span data-ttu-id="5f01f-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="5f01f-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5f01f-105">이름</span><span class="sxs-lookup"><span data-stu-id="5f01f-105">Name</span></span>

<span data-ttu-id="5f01f-106">`dotnet tool restore` - 현재 디렉터리에 대한 범위에 있는 .NET Core 로컬 도구를 컴퓨터에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5f01f-107">개요</span><span class="sxs-lookup"><span data-stu-id="5f01f-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="5f01f-108">설명</span><span class="sxs-lookup"><span data-stu-id="5f01f-108">Description</span></span>

<span data-ttu-id="5f01f-109">`dotnet tool restore` 명령은 현재 디렉터리에 대한 범위에 있는 도구 매니페스트 파일을 찾아 여기에 나열된 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="5f01f-110">매니페스트 파일에 대한 자세한 내용은 [로컬 도구 설치](global-tools.md#install-a-local-tool) 및 [로컬 도구 호출](global-tools.md#invoke-a-local-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f01f-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="5f01f-111">옵션</span><span class="sxs-lookup"><span data-stu-id="5f01f-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="5f01f-112">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="5f01f-113">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="5f01f-114">매니페스트 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="5f01f-115">여러 프로젝트를 병렬로 복원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="5f01f-116">패키지 소스 오류를 경고로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="5f01f-117">패키지 및 http 요청을 캐시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="5f01f-118">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="5f01f-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="5f01f-119">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5f01f-120">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5f01f-121">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="5f01f-122">예제</span><span class="sxs-lookup"><span data-stu-id="5f01f-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="5f01f-123">현재 디렉터리에 대한 로컬 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="5f01f-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f01f-124">참조</span><span class="sxs-lookup"><span data-stu-id="5f01f-124">See also</span></span>

- [<span data-ttu-id="5f01f-125">.NET Core 도구</span><span class="sxs-lookup"><span data-stu-id="5f01f-125">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="5f01f-126">자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="5f01f-126">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
