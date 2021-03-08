---
title: dotnet-symbol 진단 도구 - .NET CLI
description: .NET 덤프 및 미니덤프를 디버그하는 데 필요한 파일을 다운로드하기 위해 dotnet-symbol CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 5cc304a3917921a964ceb61bc2c58e942b0baa85
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105325"
---
# <a name="symbol-downloader-dotnet-symbol"></a><span data-ttu-id="436ab-103">기호 다운로더(dotnet-symbol)</span><span class="sxs-lookup"><span data-stu-id="436ab-103">Symbol downloader (dotnet-symbol)</span></span>

<span data-ttu-id="436ab-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="436ab-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="436ab-105">설치</span><span class="sxs-lookup"><span data-stu-id="436ab-105">Install</span></span>

<span data-ttu-id="436ab-106">`dotnet-symbol` [NuGet 패키지](https://www.nuget.org/packages/dotnet-symbol)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-106">To install the latest release version of the `dotnet-symbol` [NuGet package](https://www.nuget.org/packages/dotnet-symbol), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a><span data-ttu-id="436ab-107">개요</span><span class="sxs-lookup"><span data-stu-id="436ab-107">Synopsis</span></span>

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a><span data-ttu-id="436ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="436ab-108">Description</span></span>

<span data-ttu-id="436ab-109">`dotnet-symbol` 전역 도구는 코어 덤프 및 미니덤프를 디버그하는 데 필요한 파일(기호, DAC, 모듈 등)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-109">The `dotnet-symbol` global tool downloads files (symbols, DAC, modules, etc.) needed for debugging core dumps and minidumps.</span></span> <span data-ttu-id="436ab-110">해당 도구는 다른 머신에서 캡처된 덤프를 디버그할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-110">This can be useful when debugging dumps captured on another machine.</span></span> <span data-ttu-id="436ab-111">`dotnet-symbol`은 덤프를 분석하는 데 필요한 모듈 및 기호를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-111">`dotnet-symbol` can download modules and symbols needed to analyze the dump.</span></span>

## <a name="options"></a><span data-ttu-id="436ab-112">옵션</span><span class="sxs-lookup"><span data-stu-id="436ab-112">Options</span></span>

- **`--microsoft-symbol-server`**

  <span data-ttu-id="436ab-113">'http://msdl.microsoft.com/download/symbols’ 기호 서버 경로를 추가합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="436ab-113">Add 'http://msdl.microsoft.com/download/symbols' symbol server path (default).</span></span>

- **`--server-path <symbol server path>`**

  <span data-ttu-id="436ab-114">서버 경로에 기호 서버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-114">Add a symbol server to the server path.</span></span>

- **`authenticated-server-path <pat> <server path>`**

  <span data-ttu-id="436ab-115">PAT(개인용 액세스 토큰)를 사용하여 서버 경로에 인증된 기호 서버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-115">Add an authenticated symbol server to the server path using a personal access token (PAT).</span></span>

- **`--cache-directory <file cache directory>`**

  <span data-ttu-id="436ab-116">캐시 디렉터리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-116">Adds a cache directory.</span></span>

- **`--recurse-subdirectories`**

  <span data-ttu-id="436ab-117">모든 하위 디렉터리의 입력 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-117">Process input files in all subdirectories.</span></span>

- **`--host-only`**

  <span data-ttu-id="436ab-118">LLDB에서 코어 덤프를 로드하는 데 필요한 호스트 프로그램(즉, dotnet)만 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-118">Download only the host program (that is, dotnet) that lldb needs for loading core dumps.</span></span>

- **`--symbols`**

  <span data-ttu-id="436ab-119">기호 파일(.pdb, .dbg, .dwarf)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-119">Download symbol files (.pdb, .dbg, .dwarf).</span></span>

- **`--modules`**

  <span data-ttu-id="436ab-120">모듈 파일(.dll, .so, .dylib)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-120">Download the module files (.dll, .so, .dylib).</span></span>

- **`--debugging`**

  <span data-ttu-id="436ab-121">특수 디버깅 모듈(DAC, DBI, SOS)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-121">Download the special debugging modules (DAC, DBI, SOS).</span></span>

- **`--windows-pdbs`**

  <span data-ttu-id="436ab-122">이식 가능 PDB도 사용할 수 있을 때 Windows PDB를 강제로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-122">Force the downloading of the Windows PDBs when Portable PDBs are also available.</span></span>

- **`-o, --output <output directory>`**

  <span data-ttu-id="436ab-123">출력 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-123">Set the output directory.</span></span> <span data-ttu-id="436ab-124">그러지 않으면 입력 파일 옆에 씁니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="436ab-124">Otherwise, write next to the input file (default).</span></span>

- **`-d, --diagnostics`**

  <span data-ttu-id="436ab-125">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-125">Enable diagnostic output.</span></span>

- **`-h|--help`**

  <span data-ttu-id="436ab-126">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-126">Shows command-line help.</span></span>

## <a name="download-symbols"></a><span data-ttu-id="436ab-127">기호 다운로드</span><span class="sxs-lookup"><span data-stu-id="436ab-127">Download symbols</span></span>

<span data-ttu-id="436ab-128">덤프 파일에 대해 `dotnet-symbol`을 실행하면 기본적으로 관리형 어셈블리를 포함하여 덤프를 디버그하는 데 필요한 모든 모듈, 기호 및 DAC/DBI 파일이 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-128">Running `dotnet-symbol` against a dump file will, by default, download all the modules, symbols, and DAC/DBI files needed to debug the dump including the managed assemblies.</span></span> <span data-ttu-id="436ab-129">이제 SOS는 필요할 때 기호를 다운로드할 수 있으므로 호스트(dotnet) 및 디버깅 모듈에서만 LLDB를 사용하여 대부분의 Linux 코어 덤프를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-129">Because SOS can now download symbols when needed, most Linux core dumps can be analyzed using lldb with only the host (dotnet) and debugging modules.</span></span> <span data-ttu-id="436ab-130">LLDB를 실행하여 코어 덤프를 진단하는 데 필요한 해당 파일을 가져오려면:</span><span class="sxs-lookup"><span data-stu-id="436ab-130">To get these files necessary for diagnosing a core dump with lldb run:</span></span>

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a><span data-ttu-id="436ab-131">문제 해결</span><span class="sxs-lookup"><span data-stu-id="436ab-131">Troubleshoot</span></span>

- <span data-ttu-id="436ab-132">기호를 다운로드하는 동안 발생한 404 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="436ab-132">404 Not Found while downloading symbols.</span></span>

   <span data-ttu-id="436ab-133">기호 다운로드는 [공식 웹 사이트](https://dotnet.microsoft.com/download/dotnet)와 같은 공식 채널을 통해 획득한 공식 .NET Core 런타임 버전 및 [dotnet 설치 스크립트의 기본 소스](../tools/dotnet-install-script.md)에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-133">Symbol download is only supported for official .NET Core runtime versions acquired through official channels such as [the official web site](https://dotnet.microsoft.com/download/dotnet) and the [default sources in the dotnet installation scripts](../tools/dotnet-install-script.md).</span></span> <span data-ttu-id="436ab-134">디버깅 파일을 다운로드하는 동안 404 오류는 로컬로 또는 특정 Linux 배포판용으로 소스에서 빌드되거나 archlinux 같은 커뮤니티 사이트에서 빌드된 덤프와 같이 또 다른 소스에서 .NET Core 런타임을 통해 덤프가 생성되었음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-134">A 404 error while downloading debugging files may indicate that the dump was created with a .NET Core runtime from another source, such as one built from source locally or for a particular Linux distro, or from community sites like archlinux.</span></span> <span data-ttu-id="436ab-135">이 경우 디버깅에 필요한 파일(dotnet, libcoreclr.so 및 libmscordaccore.so)은 해당 소스에서 복사하거나 덤프 파일이 생성된 환경에서 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="436ab-135">In such cases, file necessary for debugging (dotnet, libcoreclr.so, and libmscordaccore.so) should be copied from those sources or from the environment the dump file was created in.</span></span>

## <a name="see-also"></a><span data-ttu-id="436ab-136">참조</span><span class="sxs-lookup"><span data-stu-id="436ab-136">See also</span></span>

* [<span data-ttu-id="436ab-137">기호를 사용하여 디버깅</span><span class="sxs-lookup"><span data-stu-id="436ab-137">Debugging with symbols</span></span>](/windows/win32/dxtecharts/debugging-with-symbols)
* [<span data-ttu-id="436ab-138">이식 가능 PDB</span><span class="sxs-lookup"><span data-stu-id="436ab-138">Portable PDBs</span></span>](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md)
