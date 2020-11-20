---
title: dotnet store 명령
description: "'dotnet store' 명령은 지정된 어셈블리를 런타임 패키지 저장소에 저장합니다."
ms.date: 02/14/2020
ms.openlocfilehash: 8efb11c6bf648bc7787d5627e02b180abb8a0afd
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634339"
---
# <a name="dotnet-store"></a><span data-ttu-id="2233b-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2233b-103">dotnet store</span></span>

<span data-ttu-id="2233b-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="2233b-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2233b-105">name</span><span class="sxs-lookup"><span data-stu-id="2233b-105">Name</span></span>

<span data-ttu-id="2233b-106">`dotnet store` - 지정된 어셈블리를 [런타임 패키지 저장소](../deploying/runtime-store.md)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="2233b-107">개요</span><span class="sxs-lookup"><span data-stu-id="2233b-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest <PATH_TO_MANIFEST_FILE>
    -f|--framework <FRAMEWORK_VERSION> -r|--runtime <RUNTIME_IDENTIFIER>
    [--framework-version <FRAMEWORK_VERSION>] [--output <OUTPUT_DIRECTORY>]
    [--skip-optimization] [--skip-symbols] [-v|--verbosity <LEVEL>]
    [--working-dir <WORKING_DIRECTORY>]

dotnet store -h|--help
```

## <a name="description"></a><span data-ttu-id="2233b-108">설명</span><span class="sxs-lookup"><span data-stu-id="2233b-108">Description</span></span>

<span data-ttu-id="2233b-109">`dotnet store`는 지정된 어셈블리를 [런타임 패키지 저장소](../deploying/runtime-store.md)에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="2233b-110">기본적으로 어셈블리는 대상 런타임 및 프레임워크에 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="2233b-111">자세한 내용은 [런타임 패키지 저장소](../deploying/runtime-store.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2233b-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="2233b-112">필수 옵션</span><span class="sxs-lookup"><span data-stu-id="2233b-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2233b-113">[대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2233b-114">대상 프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="2233b-115">*패키지 저장소 매니페스트 파일* 은 저장할 패키지 목록이 포함된 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="2233b-116">매니페스트 파일 형식은 SDK 스타일 프로젝트 형식과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="2233b-117">따라서 원하는 패키지를 참조하는 프로젝트 파일을 `-m|--manifest` 옵션과 함께 사용하여 런타임 패키지 저장소에 어셈블리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="2233b-118">여러 매니페스트 파일을 지정하려면 각 파일에 대해 옵션 및 경로를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="2233b-119">예: `--manifest packages1.csproj --manifest packages2.csproj`</span><span class="sxs-lookup"><span data-stu-id="2233b-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="2233b-120">대상으로 지정할 [런타임 식별자](../rid-catalog.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="2233b-121">선택적 옵션</span><span class="sxs-lookup"><span data-stu-id="2233b-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="2233b-122">.NET SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-122">Specifies the .NET SDK version.</span></span> <span data-ttu-id="2233b-123">이 옵션을 사용하여 `-f|--framework` 옵션을 통해 지정된 프레임워크가 아닌 특정 프레임워크 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2233b-124">도움말 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2233b-125">런타임 패키지 저장소의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="2233b-126">지정하지 않으면 기본적으로 사용자 프로필 .NET 설치 디렉터리의 *store* 하위 디렉터리로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="2233b-127">최적화 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="2233b-128">기호 생성을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-128">Skips symbol generation.</span></span> <span data-ttu-id="2233b-129">현재 Windows 및 Linux에서만 기호를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="2233b-130">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2233b-131">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="2233b-132">명령에서 사용되는 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-132">The working directory used by the command.</span></span> <span data-ttu-id="2233b-133">지정하지 않으면 현재 디렉터리의 *obj* 하위 디렉터리가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="2233b-134">예</span><span class="sxs-lookup"><span data-stu-id="2233b-134">Examples</span></span>

- <span data-ttu-id="2233b-135">지정된 패키지를 .NET Core 2.0.0에 대한 *packages.csproj* 프로젝트 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="2233b-136">지정된 패키지를 최적화 없이 *packages.csproj* 에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2233b-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="2233b-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2233b-137">See also</span></span>

- [<span data-ttu-id="2233b-138">런타임 패키지 저장소</span><span class="sxs-lookup"><span data-stu-id="2233b-138">Runtime package store</span></span>](../deploying/runtime-store.md)
