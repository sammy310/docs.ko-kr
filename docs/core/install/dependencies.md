---
title: .NET Core SDK 및 런타임 종속성 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core SDK 및 런타임을 설치하기 위한 운영 체제 및 CPU 아키텍처 사전 요구 사항에 대해 설명합니다.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157814"
---
# <a name="net-core-dependencies-and-requirements"></a>.NET Core 종속성 및 요구 사항

이 문서에서는 .NET Core에서 지원하는 운영 체제 및 CPU 아키텍처에 대해 설명합니다.

## <a name="supported-operating-systems"></a>지원되는 운영 체제

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64, ARM32      |

.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64, ARM32      |

.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 SP1+                   | x64, x86        |
| Nano 서버                   | 버전 1803+                   | x64, ARM32      |

.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 SP1+                   | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64,            |

.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7 / Vista / 8.1 / Server 2008 R2

다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.

- Windows 7 SP1
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

다음을 설치합니다.

- [Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.

> 컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다. 프로그램을 다시 설치하여 이 문제를 해결하세요.
>
> \- 또는 -
>
> 라이브러리 *hostfxr.dll*을 찾았으나 *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1에서는 Linux를 단일 운영 체제로 취급합니다. 지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.

.NET Core 3.1은 다음과 같은 Linux 배포/버전에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                             | 버전               | 아키텍처    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SLES(SUSE Enterprise Linux)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.10+                 | x64, ARM64 |

.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.

ARM64(커널 4.14+)에 .NET Core 3.1을 설치하는 방법에 대한 자세한 내용은 [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)(Linux ARM64에 .NET Core 3.0 설치)를 참조하세요.

> [!IMPORTANT]
> ARM64 지원을 위해서는 Linux 커널 4.14 이상이 필요합니다. 몇몇 Linux 배포는 이 요구 사항을 충족하고, 그 밖의 배포는 충족하지 않습니다. 예를 들어, Ubuntu 18.04는 지원되지만 Ubuntu 16.04는 지원되지 않습니다.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0에서는 Linux를 단일 운영 체제로 처리합니다. 지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.

.NET Core 3.0은 다음과 같은 Linux 배포/버전에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                             | 버전               | 아키텍처    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SLES(SUSE Enterprise Linux)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.

ARM64에 .NET Core 3.0을 설치하는 방법에 대한 자세한 내용은 [Linux ARM64에 .NET Core 3.0 설치](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)를 참조하세요.

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2에서는 Linux를 단일 운영 체제로 처리합니다. 지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.

.NET Core 2.2는 다음 Linux 배포/버전에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                             |  버전                |  아키텍처   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | X64 |
| CentOS                         |  7                      | X64 |
| Oracle Linux                   |  7                      | X64 |
| Fedora                         |  29, 30                 | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 18.10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | X64 |
| openSUSE                       |  15+                    | X64 |
| SLES(SUSE Enterprise Linux)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1에서는 Linux를 단일 운영 체제로 처리합니다. 지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.

.NET Core 2.1은 다음 Linux 배포/버전에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                             |  버전                |  아키텍처   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | X64 |
| CentOS                         |  7+                     | X64 |
| Oracle Linux                   |  7+                     | X64 |
| Fedora                         |  29+                    | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 19.04, 19.10    | x64, ARM32 |
| Linux Mint                     |  17+                    | X64 |
| openSUSE                       |  15+                    | X64 |
| SLES(SUSE Enterprise Linux)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.

---

## <a name="linux-distribution-dependencies"></a>Linux 배포 종속성

Linux 배포에 따라 추가 종속성을 설치해야 할 수 있습니다.

> [!IMPORTANT]
> 정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.

### <a name="ubuntu"></a>Ubuntu

Ubuntu 배포의 경우 다음과 같은 라이브러리를 설치해야 합니다.

- liblttng-ust0
- libcurl3(14.x 및 16.x용)
- libcurl4(18.x용)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52(14.x용)
- libicu55(16.x용)
- libicu57(17.x용)
- libicu60(18.x용)

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.

- libgdiplus(버전 6.0.1 이상)

> [!WARNING]
> 대부분의 Ubuntu 버전은 libgdiplus의 이전 버전을 포함합니다. 시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다. 자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.

### <a name="centos-and-fedora"></a>CentOS 및 Fedora

CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Fedora 사용자: OpenSSL의 버전이 1.1보다 크거나 같은 경우 **compat-openssl10**을 설치해야 합니다.

.NET Core 2.0의 경우 다음과 같은 종속성도 필요합니다.

- libunwind
- libuuid

종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.

- libgdiplus(버전 6.0.1 이상)

> [!WARNING]
> CentOS와 Fedora의 대부분의 버전은 libgdiplus의 이전 버전을 포함합니다. 시스템에 Mono 리포지토리를 추가하여 최신 버전의 libgdiplus를 설치할 수 있습니다. 자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.

::: zone-end

::: zone pivot="os-macos"

.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| .NET Core 버전 | macOS                 | 아키텍처 |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra(10.13+)  | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra(10.13+)  | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra(10.12+)       | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra(10.12+)       | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다. 이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.

.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다. 그 전에 릴리스된 버전은 공증되지 않았습니다. 공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.

## <a name="libgdiplus"></a>libgdiplus

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.

libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다. *brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>다음 단계

- 앱을 개발하고 실행하려면 [.NET Core SDK](sdk.md)(런타임이 포함되어 있음)를 설치하세요.
- 다른 사용자가 만든 앱을 실행하려면 [.NET Core 런타임](runtime.md)을 설치하세요.
