---
title: dotnet-sos 진단 도구 - .NET CLI
description: Windows 및 Linux의 네이티브 디버거에서 사용되는 SOS 디버거 확장을 관리하기 위해 dotnet-sos CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825444"
---
# <a name="sos-installer-dotnet-sos"></a>SOS 설치 프로그램(dotnet-sos)

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="install"></a>설치

다음 두 가지 방법으로 `dotnet-sos`를 다운로드하고 설치할 수 있습니다.

- **dotnet 전역 도구:**

  `dotnet-sos` [NuGet 패키지](https://www.nuget.org/packages/dotnet-sos)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **직접 다운로드:**

  플랫폼에 맞는 도구 실행 파일을 다운로드합니다.

  | OS  | 플랫폼 |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

## <a name="synopsis"></a>개요

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>설명

`dotnet-sos` 글로벌 도구는 [SOS 디버거 확장](../../framework/tools/sos-dll-sos-debugging-extension.md)을 설치하여 WinDbg/cdb(Windows) 및 LLDB(Linux 및 macOS) 같은 네이티브 디버거에서 [관리되는 .NET Core 상태를 검사](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)할 수 있도록 합니다. 최신 버전의 Windows 디버거(버전 10.0.18317.1001 이상 WinDbg 또는 cdb)는 Microsoft 확장 갤러리에서 SOS를 자동 로드하므로, `dotnet-sos` 도구를 통해 SOS를 설치하는 작업은 Linux 및 macOS에서만 또는 이전 디버깅 도구를 사용하는 경우 Windows에서 필요합니다.

## <a name="options"></a>옵션

- **`--version`**

  버전 정보를 표시합니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## <a name="dotnet-sos-install"></a>dotnet-sos 설치

.NET Core 프로세스를 디버그하기 위해 [SOS 확장](../../framework/tools/sos-dll-sos-debugging-extension.md)을 로컬로 설치합니다. macOS 및 Linux에서 .lldbinit 파일은 LLDB 시작 시 확장이 자동으로 로드되도록 업데이트됩니다. 이전 디버깅 도구(버전 10.0.18317.1001 미만)를 사용하여 Windows에 SOS를 설치하는 경우 디버거에서 `.load %USERPROFILE%\.dotnet\sos\sos.dll`을 실행하여 WinDbg 또는 cdb에서 확장을 수동으로 로드해야 합니다.

### <a name="synopsis"></a>개요

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet-sos 제거

[SOS 확장](../../framework/tools/sos-dll-sos-debugging-extension.md)을 제거하고 Linux 또는 macOS의 경우 LLDB 구성에서 제거합니다.

### <a name="synopsis"></a>개요

```console
dotnet-sos uninstall
```
