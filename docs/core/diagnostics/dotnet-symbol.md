---
title: dotnet-symbol - .NET Core
description: dotnet-symbol 명령줄 도구 설치 및 사용
ms.date: 08/26/2020
ms.openlocfilehash: 5a96306fc96525b00e57eda089a45b730a7e3e8c
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679190"
---
# <a name="symbol-downloader-dotnet-symbol"></a>기호 다운로더(dotnet-symbol)

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="install-dotnet-symbol"></a>dotnet-symbol 설치

`dotnet-symbol` [NuGet 패키지](https://www.nuget.org/packages/dotnet-symbol)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

```dotnetcli
dotnet tool install -g dotnet-symbol
```

## <a name="synopsis"></a>개요

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a>설명

`dotnet-symbol` 전역 도구는 코어 덤프 및 미니덤프를 디버그하는 데 필요한 파일(기호, DAC, 모듈 등)을 다운로드합니다. 해당 도구는 다른 머신에서 캡처된 덤프를 디버그할 때 유용할 수 있습니다. `dotnet-symbol`은 덤프를 분석하는 데 필요한 모듈 및 기호를 다운로드할 수 있습니다.

## <a name="options"></a>옵션

- **`--microsoft-symbol-server`**

  'http://msdl.microsoft.com/download/symbols’ 기호 서버 경로를 추가합니다(기본값).

- **`--server-path <symbol server path>`**

  서버 경로에 기호 서버를 추가합니다.

- **`authenticated-server-path <pat> <server path>`**

  PAT(개인용 액세스 토큰)를 사용하여 서버 경로에 인증된 기호 서버를 추가합니다.

- **`--cache-directory <file cache directory>`**

  캐시 디렉터리를 추가합니다.

- **`--recurse-subdirectories`**

  모든 하위 디렉터리의 입력 파일을 처리합니다.

- **`--host-only`**

  LLDB에서 코어 덤프를 로드하는 데 필요한 호스트 프로그램(즉, dotnet)만 다운로드합니다.

- **`--symbols`**

  기호 파일(.pdb, .dbg, .dwarf)을 다운로드합니다.

- **`--modules`**

  모듈 파일(.dll, .so, .dylib)을 다운로드합니다.

- **`--debugging`**

  특수 디버깅 모듈(DAC, DBI, SOS)을 다운로드합니다.

- **`--windows-pdbs`**

  이식 가능 PDB도 사용할 수 있을 때 Windows PDB를 강제로 다운로드합니다.

- **`-o, --output <output directory>`**

  출력 디렉터리를 설정합니다. 그러지 않으면 입력 파일 옆에 씁니다(기본값).

- **`-d, --diagnostics`**

  진단 출력을 사용합니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## <a name="download-symbols"></a>기호 다운로드

덤프 파일에 대해 `dotnet-symbol`을 실행하면 기본적으로 관리형 어셈블리를 포함하여 덤프를 디버그하는 데 필요한 모든 모듈, 기호 및 DAC/DBI 파일이 다운로드됩니다. 이제 SOS는 필요할 때 기호를 다운로드할 수 있으므로 호스트(dotnet) 및 디버깅 모듈에서만 LLDB를 사용하여 대부분의 Linux 코어 덤프를 분석할 수 있습니다. LLDB를 실행하여 코어 덤프를 진단하는 데 필요한 해당 파일을 가져오려면:

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a>문제 해결

- 기호를 다운로드하는 동안 발생한 404 찾을 수 없음

   기호 다운로드는 [공식 웹 사이트](https://dotnet.microsoft.com/download/dotnet-core)와 같은 공식 채널을 통해 획득한 공식 .NET Core 런타임 버전 및 [dotnet 설치 스크립트의 기본 소스](../tools/dotnet-install-script.md)에서만 지원됩니다. 디버깅 파일을 다운로드하는 동안 404 오류는 로컬로 또는 특정 Linux 배포판용으로 소스에서 빌드되거나 archlinux 같은 커뮤니티 사이트에서 빌드된 덤프와 같이 또 다른 소스에서 .NET Core 런타임을 통해 덤프가 생성되었음을 나타낼 수 있습니다. 이 경우 디버깅에 필요한 파일(dotnet, libcoreclr.so 및 libmscordaccore.so)은 해당 소스에서 복사하거나 덤프 파일이 생성된 환경에서 복사해야 합니다.
