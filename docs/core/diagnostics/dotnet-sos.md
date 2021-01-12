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

`dotnet-sos` 전역 도구는 [SOS 디버거 확장](sos-debugging-extension.md)을 설치합니다. 이 확장을 사용하면 lldb, windbg 등과 같은 네이티브 디버거에서 관리형 .NET Core 상태를 검사할 수 있습니다.

> [!NOTE]
> Linux나 macOS에서만 `dotnet-sos` 도구를 통해 SOS를 설치해야 합니다.  Windows에서도 이전 디버깅 도구를 사용하는 경우 필요할 수 있습니다. 최신 버전의 [Windows 디버거](/windows-hardware/drivers/debugger/debugger-download-tools)(WinDbg 또는 cdb의 버전 10.0.18317.1001 이상)는 Microsoft 확장 갤러리에서 SOS를 자동으로 로드합니다.  

## <a name="options"></a>옵션

- **`--version`**

  버전 정보를 표시합니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## <a name="dotnet-sos-install"></a>dotnet-sos 설치

.NET Core 프로세스를 디버그하기 위해 [SOS 확장](sos-debugging-extension.md)을 로컬로 설치합니다. macOS 및 Linux에서 *.lldbinit* 파일은 LLDB 시작 시 확장이 자동으로 로드되도록 업데이트됩니다. 이전 디버깅 도구(버전 10.0.18317.1001 미만)를 사용하여 Windows에 SOS를 설치하는 경우 디버거에서 `.load %USERPROFILE%\.dotnet\sos\sos.dll`을 실행하여 WinDbg 또는 cdb에서 확장을 수동으로 로드해야 합니다.

### <a name="synopsis"></a>개요

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a>옵션

- **`--architecture <arch>`**

  설치할 SOS 이진 파일의 프로세서 아키텍처를 지정합니다. 기본적으로 `dotnet-sos`는 호스트 머신의 아키텍처를 설치합니다. dotnet 호스트 아키텍처와 다른 아키텍처에 SOS를 설치 하려는 경우 이 옵션을 사용합니다. 예를 들어 Arm64 호스트에서 Arm32 이진 파일을 실행하는 경우 `dotnet-sos install --architecture Arm`을 사용하여 SOS를 설치해야 합니다.

  사용할 수 있는 아키텍처는 다음과 같습니다.

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a>dotnet-sos 제거

[SOS 확장](sos-debugging-extension.md)을 제거하고 Linux와 macOS의 경우 LLDB 구성에서 해당 확장을 제거합니다.

### <a name="synopsis"></a>개요

```console
dotnet-sos uninstall
```
