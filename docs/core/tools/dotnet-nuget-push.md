---
title: dotnet nuget push 명령
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: d4ef8e58908fe488c712debff3b313ac0908b43e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503663"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="3cbda-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="3cbda-103">dotnet nuget push</span></span>

<span data-ttu-id="3cbda-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="3cbda-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3cbda-105">이름</span><span class="sxs-lookup"><span data-stu-id="3cbda-105">Name</span></span>

<span data-ttu-id="3cbda-106">`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3cbda-107">개요</span><span class="sxs-lookup"><span data-stu-id="3cbda-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3cbda-108">설명</span><span class="sxs-lookup"><span data-stu-id="3cbda-108">Description</span></span>

<span data-ttu-id="3cbda-109">`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="3cbda-110">push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="3cbda-111">구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cbda-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="3cbda-112">NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="3cbda-113">인수</span><span class="sxs-lookup"><span data-stu-id="3cbda-113">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="3cbda-114">푸시되는 패키지에 대한 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="3cbda-115">옵션</span><span class="sxs-lookup"><span data-stu-id="3cbda-115">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="3cbda-116">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="3cbda-117">고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-117">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3cbda-118">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-118">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="3cbda-119">명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="3cbda-120">.NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-120">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="3cbda-121">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-121">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="3cbda-122">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="3cbda-122">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="3cbda-123">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3cbda-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="3cbda-124">.NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-124">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="3cbda-125">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-125">Specifies the server URL.</span></span> <span data-ttu-id="3cbda-126">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="3cbda-127">여러 패키지를 HTTP(S) 서버로 푸시할 때 푸시를 계속할 수 있도록 409 충돌 응답을 경고로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-127">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="3cbda-128">.NET Core 3.1 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-128">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="3cbda-129">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-129">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="3cbda-130">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-130">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="3cbda-131">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="3cbda-132">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="3cbda-133">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-133">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="3cbda-134">예</span><span class="sxs-lookup"><span data-stu-id="3cbda-134">Examples</span></span>

- <span data-ttu-id="3cbda-135">기본 푸시 소스에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-135">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="3cbda-136">공식 NuGet 서버에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-136">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="3cbda-137">사용자 지정 푸시 소스 `https://customsource`에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-137">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="3cbda-138">기본 푸시 소스 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-138">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="3cbda-139">기본 기호 소스에 *foo.symbols.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-139">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="3cbda-140">360초 시간 제한을 지정하여 기본 푸시 소스에 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-140">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="3cbda-141">기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-141">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="3cbda-142">이 명령이 작동하지 않는 경우 이전 버전의 SDK(.NET Core 2.1 SDK 및 이전 버전)에 존재했던 버그 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-142">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="3cbda-143">이 문제를 해결하려면 SDK 버전을 업그레이드하거나 대신 `dotnet nuget push **/*.nupkg` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-143">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="3cbda-144">HTTP(S) 서버가 409 충돌 응답을 반환하더라도 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbda-144">Pushes all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
