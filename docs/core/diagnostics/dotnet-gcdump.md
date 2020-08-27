---
title: dotnet-gcdump - .NET Core
description: dotnet-gcdump 명령줄 도구 설치 및 사용
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656653"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>힙 분석 도구(dotnet-gcdump)

**이 문서의 적용 대상:** ✔️ .NET Core 3.1 SDK 이상 버전

## <a name="install-dotnet-gcdump"></a>dotnet-gcdump 설치

`dotnet-gcdump` [NuGet 패키지](https://www.nuget.org/packages/dotnet-gcdump)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a>개요

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>설명

`dotnet-gcdump` 전역 도구를 통해 라이브 .NET 프로세스의 GC(가비지 수집기) 덤프를 수집할 수 있습니다. 이 도구는 Windows의 ETW에 해당하는 플랫폼 간 EventPipe 기술을 사용합니다. GC 덤프는 대상 프로세스에서 GC를 트리거하고 특수 이벤트를 켠 후 이벤트 스트림에서 개체 루트의 그래프를 다시 생성하여 만듭니다. 이 프로세스를 통해 프로세스가 실행되는 동안 최소한의 오버헤드로 GC 덤프를 수집할 수 있습니다. 해당 덤프는 다음을 비롯한 여러 시나리오에서 유용합니다.

- 여러 시점에 힙의 개체 수 비교
- 개체 루트 분석(“이 형식에 대한 참조를 여전히 포함하는 것은 무엇인가요?” 등의 질문에 답변)
- 힙의 개체 수에 대한 일반 통계 수집

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a>dotnet-gcdump에서 캡처된 GC 덤프 보기

Windows의 `.gcdump` 파일은 분석을 위해 [PerfView](https://github.com/microsoft/perfview)에서 보거나 Visual Studio에서 볼 수 있습니다. Windows 이외의 플랫폼에서는 현재 `.gcdump`를 열 수 없습니다.

`.gcdump`를 여러 개 수집하고 Visual Studio에서 동시에 열어 비교할 수 있습니다.

## <a name="options"></a>옵션

- **`--version`**

  `dotnet-gcdump` 유틸리티의 버전을 표시합니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## `dotnet-gcdump collect`

현재 실행 중인 프로세스에서 GC 덤프를 수집합니다.

### <a name="synopsis"></a>개요

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a>옵션

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

- **`-p|--process-id <pid>`**

  GC 덤프를 수집할 프로세스 ID입니다.

- **`-o|--output <gcdump-file-path>`**

  수집된 GC 덤프를 작성해야 하는 경로입니다. 기본값은 *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*입니다.

- **`-v|--verbose`**

  GC 덤프를 수집하는 동안 로그를 출력합니다.

- **`-t|--timeout <timeout>`**

  이 시간(초)보다 오래 걸릴 경우 GC 덤프 수집을 포기합니다. 기본값은 30입니다.

- **`-n|--name <name>`**

  GC 덤프를 수집할 프로세스의 이름입니다.

## `dotnet-gcdump ps`

GC 덤프를 수집할 수 있는 dotnet 프로세스를 나열합니다.

### <a name="synopsis"></a>개요

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

이전에 생성된 GC 덤프 또는 실행 중인 프로세스에서 보고서를 생성하고 `stdout`에 씁니다.

### <a name="synopsis"></a>개요

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a>옵션

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

- **`-p|--process-id <pid>`**

  GC 덤프를 수집할 프로세스 ID입니다.

- **`-t|--report-type <HeapStat>`**

  생성할 보고서의 유형입니다. 사용 가능한 옵션: heapstat(기본값)

## <a name="troubleshoot"></a>문제 해결

- gcdump에 형식 정보가 없습니다.

   .NET Core 3.1 이전에는 EventPipe를 사용하여 호출된 gcdumps 사이에 형식 캐시가 지워지지 않는 문제가 있었습니다. 이 때문에 두 번째 및 후속 gcdumps에서는 형식 정보를 확인하는 데 필요한 이벤트가 전송되지 않았습니다. 이 문제는 .NET Core 3.1-preview2에서 해결되었습니다.

- GC 덤프에 COM 및 정적 형식이 없습니다.

   .NET Core 3.1-preview2 이전에는 EventPipe를 통해 GC 덤프를 호출할 경우 정적 및 COM 형식이 전송되지 않는 문제가 있었습니다. 이 문제는 .NET Core 3.1-preview2에서 해결되었습니다.
