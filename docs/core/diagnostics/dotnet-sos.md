---
title: dotnet-sos 진단 도구 - .NET CLI
description: Windows 및 Linux의 네이티브 디버거에서 사용되는 SOS 디버거 확장을 관리하기 위해 dotnet-sos CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 09e8228c47bdc632bccf3c9ad2296d55fe420060
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765009"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="f0d57-103">SOS 설치 프로그램(dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="f0d57-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="f0d57-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f0d57-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="f0d57-105">설치</span><span class="sxs-lookup"><span data-stu-id="f0d57-105">Install</span></span>

<span data-ttu-id="f0d57-106">다음 두 가지 방법으로 `dotnet-sos`를 다운로드하고 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="f0d57-107">**dotnet 전역 도구:**</span><span class="sxs-lookup"><span data-stu-id="f0d57-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="f0d57-108">`dotnet-sos` [NuGet 패키지](https://www.nuget.org/packages/dotnet-sos)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="f0d57-109">**직접 다운로드:**</span><span class="sxs-lookup"><span data-stu-id="f0d57-109">**Direct download:**</span></span>

  <span data-ttu-id="f0d57-110">플랫폼에 맞는 도구 실행 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="f0d57-111">OS</span><span class="sxs-lookup"><span data-stu-id="f0d57-111">OS</span></span>  | <span data-ttu-id="f0d57-112">플랫폼</span><span class="sxs-lookup"><span data-stu-id="f0d57-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="f0d57-113">Windows</span><span class="sxs-lookup"><span data-stu-id="f0d57-113">Windows</span></span> | <span data-ttu-id="f0d57-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="f0d57-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="f0d57-115">macOS</span><span class="sxs-lookup"><span data-stu-id="f0d57-115">macOS</span></span>   | [<span data-ttu-id="f0d57-116">x64</span><span class="sxs-lookup"><span data-stu-id="f0d57-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="f0d57-117">Linux</span><span class="sxs-lookup"><span data-stu-id="f0d57-117">Linux</span></span>   | <span data-ttu-id="f0d57-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="f0d57-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="f0d57-119">개요</span><span class="sxs-lookup"><span data-stu-id="f0d57-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="f0d57-120">설명</span><span class="sxs-lookup"><span data-stu-id="f0d57-120">Description</span></span>

<span data-ttu-id="f0d57-121">`dotnet-sos` 전역 도구는 [SOS 디버거 확장](sos-debugging-extension.md)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-121">The `dotnet-sos` global tool installs the [SOS debugger extension](sos-debugging-extension.md).</span></span> <span data-ttu-id="f0d57-122">이 확장을 사용하면 lldb, windbg 등과 같은 네이티브 디버거에서 관리형 .NET Core 상태를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-122">This extension lets you inspect managed .NET Core state from native debuggers like lldb and windbg.</span></span>

> [!NOTE]
> <span data-ttu-id="f0d57-123">Linux나 macOS에서만 `dotnet-sos` 도구를 통해 SOS를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-123">Installing SOS via the `dotnet-sos` tool is only needed on Linux or macOS.</span></span>  <span data-ttu-id="f0d57-124">Windows에서도 이전 디버깅 도구를 사용하는 경우 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-124">It may also be needed on Windows if you're using older debugging tools.</span></span> <span data-ttu-id="f0d57-125">최신 버전의 [Windows 디버거](/windows-hardware/drivers/debugger/debugger-download-tools)(WinDbg 또는 cdb의 버전 10.0.18317.1001 이상)는 Microsoft 확장 갤러리에서 SOS를 자동으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-125">Recent versions of the [Windows Debugger](/windows-hardware/drivers/debugger/debugger-download-tools) (>= version 10.0.18317.1001 of WinDbg or cdb) load SOS automatically from the Microsoft extension gallery.</span></span>  

## <a name="options"></a><span data-ttu-id="f0d57-126">옵션</span><span class="sxs-lookup"><span data-stu-id="f0d57-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="f0d57-127">버전 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-127">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f0d57-128">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-128">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="f0d57-129">dotnet-sos 설치</span><span class="sxs-lookup"><span data-stu-id="f0d57-129">dotnet-sos install</span></span>

<span data-ttu-id="f0d57-130">.NET Core 프로세스를 디버그하기 위해 [SOS 확장](sos-debugging-extension.md)을 로컬로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-130">Installs the [SOS extension](sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="f0d57-131">macOS 및 Linux에서 *.lldbinit* 파일은 LLDB 시작 시 확장이 자동으로 로드되도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-131">On macOS and Linux, the *.lldbinit* file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="f0d57-132">이전 디버깅 도구(버전 10.0.18317.1001 미만)를 사용하여 Windows에 SOS를 설치하는 경우 디버거에서 `.load %USERPROFILE%\.dotnet\sos\sos.dll`을 실행하여 WinDbg 또는 cdb에서 확장을 수동으로 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-132">If you're installing SOS on Windows with older debugging tools (prior to version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f0d57-133">개요</span><span class="sxs-lookup"><span data-stu-id="f0d57-133">Synopsis</span></span>

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a><span data-ttu-id="f0d57-134">옵션</span><span class="sxs-lookup"><span data-stu-id="f0d57-134">Options</span></span>

- **`--architecture <arch>`**

  <span data-ttu-id="f0d57-135">설치할 SOS 이진 파일의 프로세서 아키텍처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-135">Specifies the processor architecture of the SOS binaries to install.</span></span> <span data-ttu-id="f0d57-136">기본적으로 `dotnet-sos`는 호스트 머신의 아키텍처를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-136">By default, `dotnet-sos` installs the architecture of the host machine.</span></span> <span data-ttu-id="f0d57-137">dotnet 호스트 아키텍처와 다른 아키텍처에 SOS를 설치 하려는 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-137">Use this option when you want to install SOS for an architecture that's different from the dotnet host architecture.</span></span> <span data-ttu-id="f0d57-138">예를 들어 Arm64 호스트에서 Arm32 이진 파일을 실행하는 경우 `dotnet-sos install --architecture Arm`을 사용하여 SOS를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-138">For example, if you're running Arm32 binaries from an Arm64 host, you will need to install SOS with `dotnet-sos install --architecture Arm`.</span></span>

  <span data-ttu-id="f0d57-139">사용할 수 있는 아키텍처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-139">The following architectures are available:</span></span>

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="f0d57-140">dotnet-sos 제거</span><span class="sxs-lookup"><span data-stu-id="f0d57-140">dotnet-sos uninstall</span></span>

<span data-ttu-id="f0d57-141">[SOS 확장](sos-debugging-extension.md)을 제거하고 Linux와 macOS의 경우 LLDB 구성에서 해당 확장을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d57-141">Uninstalls the [SOS extension](sos-debugging-extension.md) and, on Linux and macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f0d57-142">개요</span><span class="sxs-lookup"><span data-stu-id="f0d57-142">Synopsis</span></span>

```console
dotnet-sos uninstall
```
