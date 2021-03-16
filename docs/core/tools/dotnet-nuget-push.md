---
title: dotnet nuget push 명령
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 92e2593633343bda6990ca51d593455ff13f0df7
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478189"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="4e634-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4e634-103">dotnet nuget push</span></span>

<span data-ttu-id="4e634-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="4e634-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4e634-105">이름</span><span class="sxs-lookup"><span data-stu-id="4e634-105">Name</span></span>

<span data-ttu-id="4e634-106">`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e634-107">개요</span><span class="sxs-lookup"><span data-stu-id="4e634-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="4e634-108">설명</span><span class="sxs-lookup"><span data-stu-id="4e634-108">Description</span></span>

<span data-ttu-id="4e634-109">`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="4e634-110">push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="4e634-111">구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e634-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="4e634-112">NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config* 를 로드하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="4e634-113">이 명령은 기존 패키지를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-113">The command pushes an existing package.</span></span> <span data-ttu-id="4e634-114">패키지를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-114">It doesn't create a package.</span></span> <span data-ttu-id="4e634-115">패키지를 만들려면 [`dotnet pack`](dotnet-pack.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="4e634-116">인수</span><span class="sxs-lookup"><span data-stu-id="4e634-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="4e634-117">푸시되는 패키지에 대한 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="4e634-118">옵션</span><span class="sxs-lookup"><span data-stu-id="4e634-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="4e634-119">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="4e634-120">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4e634-121">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="4e634-122">명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="4e634-123">.NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4e634-124">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-124">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="4e634-125">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="4e634-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="4e634-126">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4e634-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="4e634-127">.NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="4e634-128">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-128">Specifies the server URL.</span></span> <span data-ttu-id="4e634-129">NuGet은 UNC 또는 로컬 폴더 소스를 식별하며, HTTP를 사용하여 파일을 푸시하는 대신 단순히 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-129">NuGet identifies a UNC or local folder source and simply copies the file there instead of pushing it using HTTP.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="4e634-130">NuGet 3.4.2부터는 NuGet 구성 파일이 `DefaultPushSource` 값을 지정하지 않는 한 이것이 필수 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-130">Starting with NuGet 3.4.2, this is a mandatory parameter unless the NuGet config file specifies a `DefaultPushSource` value.</span></span> <span data-ttu-id="4e634-131">자세한 내용은 참조 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e634-131">For more information, see [Configuring NuGet behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="4e634-132">여러 패키지를 HTTP(S) 서버로 푸시할 때 푸시를 계속할 수 있도록 409 충돌 응답을 경고로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-132">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="4e634-133">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-133">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="4e634-134">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-134">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="4e634-135">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-135">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="4e634-136">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-136">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="4e634-137">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-137">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="4e634-138">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-138">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="4e634-139">예</span><span class="sxs-lookup"><span data-stu-id="4e634-139">Examples</span></span>

- <span data-ttu-id="4e634-140">API 키를 사용하여 NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-140">Push *foo.nupkg* to the default push source specified in the NuGet config file, using an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="4e634-141">공식 NuGet 서버에 *foo.nupkg* 를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-141">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="4e634-142">사용자 지정 푸시 소스 `https://customsource`에 *foo.nupkg* 를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-142">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="4e634-143">NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-143">Push *foo.nupkg* to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="4e634-144">기본 기호 소스에 *foo.symbols.nupkg* 를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-144">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="4e634-145">360초 시간 제한을 사용하여 NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-145">Push *foo.nupkg* to the default push source specified in the NuGet config file, with a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="4e634-146">NuGet 구성 파일에 지정된 기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-146">Push all *.nupkg* files in the current directory to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg"
  ```

  > [!NOTE]
  > <span data-ttu-id="4e634-147">이 명령이 작동하지 않는 경우 이전 버전의 SDK(.NET Core 2.1 SDK 및 이전 버전)에 존재했던 버그 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-147">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="4e634-148">이 문제를 해결하려면 SDK 버전을 업그레이드하거나 대신 `dotnet nuget push "**/*.nupkg"` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-148">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push "**/*.nupkg"`</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="4e634-149">파일 와일드카드 사용을 수행하는 bash와 같은 셸에는 묶는 따옴표를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-149">The enclosing quotes are required for shells such as bash that perform file globbing.</span></span> <span data-ttu-id="4e634-150">자세한 내용은 [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e634-150">For more information, see [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).</span></span>

- <span data-ttu-id="4e634-151">HTTP(S) 서버에서 409 충돌 응답이 반환되는 경우에도 NuGet 구성 파일에 지정된 기본 푸시 소스에 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-151">Push all *.nupkg* files to the default push source specified in the NuGet config file, even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" --skip-duplicate
  ```

- <span data-ttu-id="4e634-152">로컬 피드 디렉터리에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-152">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" -s c:\mydir
  ```

  <span data-ttu-id="4e634-153">이 명령은 성능 최적화를 위해 권장되는 계층 구조 폴더 구조로 패키지를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e634-153">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="4e634-154">자세한 내용은 [로컬 피드](/nuget/hosting-packages/local-feeds)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e634-154">For more information, see [Local feeds](/nuget/hosting-packages/local-feeds).</span></span>  
