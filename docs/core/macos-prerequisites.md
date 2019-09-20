---
title: Mac에서 .NET Core의 필수 구성 요소
description: macOS 컴퓨터에서.NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다.
author: mairaw
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 07/13/2019
ms.openlocfilehash: d391c18a371d721419c298f2987894f16ecbd169
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969918"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="68038-103">macOS에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="68038-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="68038-104">이 문서에서는 macOS 컴퓨터에서.NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68038-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="68038-105">다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68038-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="68038-106">지원되는 macOS 버전</span><span class="sxs-lookup"><span data-stu-id="68038-106">Supported macOS versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68038-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68038-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="68038-108">.NET Core 2.x는 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="68038-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="68038-109">macOS 10.12 "Sierra" 이상 버전</span><span class="sxs-lookup"><span data-stu-id="68038-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="68038-110">.NET Core 2.1 및 .NET Core 2.2가 지원되는 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.1이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) 및 [.NET Core 2.2가 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="68038-111">다운로드 링크 및 자세한 내용은 [.NET Core 2.2 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.2) 또는 [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-111">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68038-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68038-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="68038-113">.NET Core 1.x는 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="68038-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="68038-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="68038-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="68038-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="68038-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="68038-116">.NET Core 1.1 및 .NET Core 1.0이 지원되는 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 1.1이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) 및 [.NET Core 1.0이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="68038-117">다운로드 링크 및 자세한 내용은 [.NET Core 1.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/1.1) 또는 [.NET Core 1.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/1.0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-117">For download links and more information, see [.NET Core 1.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="68038-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="68038-118">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="68038-119">.NET Core 3.0은 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="68038-119">.NET Core 3.0 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="68038-120">macOS 10.13 “High Sierra” 이상 버전</span><span class="sxs-lookup"><span data-stu-id="68038-120">macOS 10.13 "High Sierra" and later versions</span></span>

<span data-ttu-id="68038-121">지원 OS 버전 중 .NET Core 3.0이 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 3.0이 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="68038-122">다운로드 링크 및 자세한 내용은 [.NET Core 3.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-122">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="68038-123">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="68038-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68038-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68038-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="68038-125">[.NET 다운로드](https://dotnet.microsoft.com/download) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-125">Download and install the .NET Core SDK from the [.NET Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="68038-126">macOS에 설치하는 데 문제가 있는 경우 설치된 버전에 해당하는 [알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.1) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68038-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68038-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="68038-128">.NET Core 1.x를 macOS에서 실행할 때는 OpenSSL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="68038-129">OpenSSL을 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68038-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="68038-130">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 OpenSSL을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="68038-131">[.NET 다운로드](https://dotnet.microsoft.com/download) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-131">Download and install the .NET Core SDK from the [.NET Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="68038-132">macOS에 설치하는 데 문제가 있는 경우 [1.0.0 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) 및 [1.0.1 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="68038-133">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="68038-133">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="68038-134">[.NET 다운로드](https://dotnet.microsoft.com/download) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-134">Download and install the .NET Core SDK from the [.NET Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="68038-135">macOS에 설치하는 데 문제가 있는 경우 설치된 버전에 해당하는 [릴리스 정보](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68038-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="68038-136">열려 있는 최대 파일 제한 늘리기(.NET Core SDK 2.0.2 이전 .NET Core 버전)</span><span class="sxs-lookup"><span data-stu-id="68038-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span>

<span data-ttu-id="68038-137">.NET Core 버전(.NET Core SDK 2.0.2 이전)에서 macOS에서 열려 있는 기본 파일 제한은 프로젝트를 복원하거나 단위 테스트를 실행하는 등 일부 .NET Core 작업에 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68038-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="68038-138">다음 단계를 수행하여 이 제한을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68038-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="68038-139">텍스트 편집기를 사용하여 새 파일 _/Library/LaunchDaemons/limit.maxfiles.plist_를 만들고 이 콘텐츠로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
      <dict>
        <key>Label</key>
        <string>limit.maxfiles</string>
        <key>ProgramArguments</key>
        <array>
          <string>launchctl</string>
          <string>limit</string>
          <string>maxfiles</string>
          <string>2048</string>
          <string>4096</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>ServiceIPC</key>
        <false/>
      </dict>
    </plist>
    ```

2. <span data-ttu-id="68038-140">터미널 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="68038-141">Mac을 다시 부팅하여 이 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="68038-142">Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68038-142">Visual Studio for Mac</span></span>

<span data-ttu-id="68038-143">.NET Core SDK를 사용하여 .NET Core 애플리케이션을 개발하기 위해 원하는 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68038-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="68038-144">그러나 통합 개발 환경의 Mac에서 .NET Core 애플리케이션을 개발하려는 경우 [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68038-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

<span data-ttu-id="68038-145">Mac용 Visual Studio을 사용하여 macOS에서 .NET Core로 개발하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68038-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="68038-146">지원되는 macOS 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="68038-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="68038-147">OpenSSL(.NET Core 1.x 전용, .NET Core 2.x는 macOS에서 기본적으로 제공되는 보안 서비스를 사용함)</span><span class="sxs-lookup"><span data-stu-id="68038-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="68038-148">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="68038-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="68038-149">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="68038-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
