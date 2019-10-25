---
title: Mac에서 .NET Core의 필수 구성 요소
description: macOS 컴퓨터에서.NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다.
author: thraka
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 10/11/2019
ms.openlocfilehash: 2d4fc0b37be08988440325db8b507124c36bf053
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318323"
---
# <a name="prerequisites-for-net-core-on-macos"></a>macOS에서 .NET Core의 필수 구성 요소

이 문서에서는 macOS 컴퓨터에서.NET Core 애플리케이션을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다. 다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에 적용됩니다.

## <a name="downloads-and-dependencies"></a>다운로드 및 종속성

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0은 **macOS High Sierra(버전 10.13)** 이상 버전에서 지원됩니다. **x64** CPU 아키텍처가 필요합니다.

[.NET Core 3.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.0) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다. .NET Core 3.0 지원 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 3.0 지원 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)을 참조하세요.

알려진 문제 목록은 [.NET Core 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md)를 참조하세요.

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2는 **macOS Sierra(버전 10.12)** 이상 버전에서 지원됩니다. **x64** CPU 아키텍처가 필요합니다.

[.NET Core 2.2 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.2) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다. .NET Core 2.2 지원 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.2 지원 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)을 참조하세요.

알려진 문제 목록은 [.NET Core 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md)를 참조하세요.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1은 **macOS Sierra(버전 10.12)** 이상 버전에서 지원됩니다. **x64** CPU 아키텍처가 필요합니다.

[.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1) 페이지에서 .NET Core SDK를 다운로드하여 설치합니다. .NET Core 2.1 지원 운영 체제, 배포 및 버전, 지원되지 않는 OS 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.1 지원 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)을 참조하세요.

알려진 문제 목록은 [.NET Core 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md)를 참조하세요.

---

## <a name="libgdiplus"></a>libgdiplus

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.

libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다. *brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.

```console
brew update
brew install libgdiplus
```

## <a name="visual-studio-for-mac"></a>Mac용 Visual Studio

.NET Core SDK를 사용하여 .NET Core 애플리케이션을 개발하기 위해 원하는 편집기를 사용할 수 있습니다. 그러나 통합 개발 환경의 Mac에서 .NET Core 애플리케이션을 개발하려는 경우 [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 사용할 수 있습니다.
