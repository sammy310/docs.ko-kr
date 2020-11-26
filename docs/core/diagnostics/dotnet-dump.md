---
title: dotnet-dump 진단 도구 - .NET CLI
description: 네이티브 디버거 없이 Windows 및 Linux 덤프를 수집하고 분석하기 위해 dotnet-dump CLI 도구를 설치하고 사용하는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: ea9a70c4dc47b5006339e9a197712092eb66b241
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822206"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>덤프 수집 및 분석 유틸리티(dotnet-dump)

**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전

> [!NOTE]
> macOS용 `dotnet-dump`는 .NET 5.0 이상 버전에서만 지원됩니다.

## <a name="install"></a>설치

다음 두 가지 방법으로 `dotnet-dump`를 다운로드하고 설치할 수 있습니다.

- **dotnet 전역 도구:**

  `dotnet-dump` [NuGet 패키지](https://www.nuget.org/packages/dotnet-dump)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- **직접 다운로드:**

  플랫폼에 맞는 도구 실행 파일을 다운로드합니다.

  | OS  | 플랫폼 |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-dump/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64) |

## <a name="synopsis"></a>개요

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>설명

`dotnet-dump` 글로벌 도구는 Linux에서 `lldb`와 같은 네이티브 디버거 없이 Windows 및 Linux 덤프를 수집하고 분석하는 방법입니다. 이 도구는 완벽하게 작동하는 `lldb`를 사용할 수 없는 Alpine Linux와 같은 플랫폼에서 중요합니다. `dotnet-dump` 도구를 사용하면 충돌 및 GC(가비지 수집기)를 분석하기 위해 SOS 명령을 실행할 수 있지만 네이티브 디버거가 아니므로 네이티브 스택 프레임 표시와 같은 기능은 지원되지 않습니다.

## <a name="options"></a>옵션

- **`--version`**

  dotnet-dump 유틸리티의 버전을 표시합니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## <a name="commands"></a>명령

| 명령                                     |
| ------------------------------------------- |
| [dotnet-dump collect](#dotnet-dump-collect) |
| [dotnet-dump analyze](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>dotnet-dump collect

프로세스에서 덤프를 캡처합니다.

### <a name="synopsis"></a>개요

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>옵션

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

- **`-p|--process-id <PID>`**

  덤프를 수집할 프로세스 ID 번호를 지정합니다.

- **`-n|--name <name>`**

  덤프를 수집할 프로세스의 이름을 지정합니다.

- **`--type <Full|Heap|Mini>`**

  프로세스에서 수집되는 정보의 종류를 결정하는 덤프 형식을 지정합니다. 다음 세 가지 유형이 있습니다.

  - `Full` - 모듈 이미지를 포함하여 모든 메모리를 포함하는 가장 큰 덤프입니다.
  - `Heap` - 모듈 목록, 스레드 목록, 모든 스택, 예외 정보, 핸들 정보 및 매핑된 이미지를 제외한 모든 메모리를 포함하는 크고 비교적 포괄적인 덤프입니다.
  - `Mini` - 모듈 목록, 스레드 목록, 예외 정보 및 모든 스택을 포함하는 작은 덤프입니다.

  지정하지 않으면 `Full`이 기본값입니다.

- **`-o|--output <output_dump_path>`**

  수집된 덤프를 기록해야 하는 전체 경로 및 파일 이름입니다.

  지정하지 않으면 다음과 같이 설정됩니다.

  - Windows의 경우 기본적으로 *.\dump_YYYYMMDD_HHMMSS.dmp* 로 설정됩니다.
  - Linux의 경우 기본적으로 *./core_YYYYMMDD_HHMMSS* 로 설정됩니다.

  YYYYMMDD는 년/월/일이고, HHMMSS는 시간/분/초입니다.

- **`--diag`**

  덤프 수집 진단 로깅을 사용하도록 설정합니다.

## <a name="dotnet-dump-analyze"></a>dotnet-dump analyze

덤프를 검색하기 위해 대화형 셸을 시작합니다. 셸에는 다양한 [SOS 명령](#analyze-sos-commands)이 허용됩니다.

### <a name="synopsis"></a>개요

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>인수

- **`<dump_path>`**

  분석할 덤프 파일의 경로를 지정합니다.

### <a name="options"></a>옵션

- **`-c|--command <debug_command>`**

  시작할 때 셸에서 실행할 [명령](#analyze-sos-commands)을 지정합니다.

### <a name="analyze-sos-commands"></a>SOS 명령 분석

| 명령                             | 기능                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | 사용 가능한 모든 명령을 표시합니다.                                                               |
| `soshelp|help <command>`            | 지정된 명령을 표시합니다.                                                               |
| `exit|quit`                         | 대화형 모드를 종료합니다.                                                                       |
| `clrstack <arguments>`              | 관리 코드의 스택 추적만 제공합니다.                                                  |
| `clrthreads <arguments>`            | 실행 중인 관리형 스레드를 나열합니다.                                                            |
| `dumpasync <arguments>`             | 가비지가 수집된 힙의 비동기 상태 머신에 대한 정보를 표시합니다.                |
| `dumpassembly <arguments>`          | 어셈블리에 대한 세부 정보를 표시합니다.                                                           |
| `dumpclass <arguments>`             | 지정된 주소의 EE 클래스 구조체에 대한 정보를 표시합니다.                     |
| `dumpdelegate <arguments>`          | 대리자에 대한 정보를 표시합니다.                                                        |
| `dumpdomain <arguments>`            | 모든 AppDomains 및 도메인 내의 모든 어셈블리에 대한 정보를 표시합니다.                |
| `dumpheap <arguments>`              | 가비지가 수집된 힙에 대한 정보와 개체에 대한 수집 통계를 표시합니다.       |
| `dumpil <arguments>`                | 관리되는 메서드와 연관된 MSIL(Microsoft intermediate language)을 표시합니다. |
| `dumplog <arguments>`               | 메모리 내 스트레스 로그의 내용을 지정된 파일에 씁니다.                         |
| `dumpmd <arguments>`                | 지정된 주소의 MethodDesc 구조체에 대한 정보를 표시합니다.                   |
| `dumpmodule <arguments>`            | 지정된 주소의 EE 모듈 구조체에 대한 정보를 표시합니다.                    |
| `dumpmt <arguments>`                | 지정된 주소의 메서드 테이블에 대한 정보를 표시합니다.                           |
| `dumpobj <arguments>`               | 지정된 주소의 개체에 대한 정보를 표시합니다.                                       |
| `dso|dumpstackobjects <arguments>`  | 현재 스택의 범위 내에 있는 관리되는 모든 개체를 표시합니다.                    |
| `eeheap <arguments>`                | 내부 런타임 데이터 구조에서 사용하는 프로세스 메모리에 대한 정보를 표시합니다.              |
| `finalizequeue <arguments>`         | 종료하도록 등록된 모든 개체를 표시합니다.                                             |
| `gcroot <arguments>`                | 지정된 주소의 개체에 대한 참조(또는 루트)에 대한 정보를 표시합니다.              |
| `gcwhere <arguments>`               | 전달된 인수의 GC 힙에 있는 위치를 표시합니다.                               |
| `ip2md <arguments>`                 | JIT 코드의 지정된 주소에 있는 MethodDesc 구조체를 표시합니다.                       |
| `histclear <arguments>`             | `hist*` 명령의 패밀리에서 사용하는 모든 리소스를 해제합니다.                                |
| `histinit <arguments>`              | 디버기에 저장된 스트레스 로그에서 SOS 구조를 초기화합니다.                     |
| `histobj <arguments>`               | `<arguments>`와 관련된 가비지 수집 스트레스 로그 재배치를 표시합니다.              |
| `histobjfind <arguments>`           | 지정된 주소의 개체를 참조하는 모든 로그 항목을 표시합니다.               |
| `histroot <arguments>`              | 지정된 루트의 승격 및 재배치와 관련된 정보를 표시합니다.        |
| `lm|modules`                        | 프로세스의 네이티브 모듈을 표시합니다.                                                   |
| `name2ee <arguments>`               | `<argument>`에 대한 MethodTable 구조체와 EEClass 구조체를 표시합니다.                |
| `pe|printexception <arguments>`     | `<argument>` 주소의 Exception 클래스에서 파생된 개체를 표시합니다.             |
| `setsymbolserver <arguments>`       | 기호 서버 지원을 사용하도록 설정합니다.                                                             |
| `syncblk <arguments>`               | SyncBlock 표시자 정보를 표시합니다.                                                           |
| `threads|setthread <threadid>`      | SOS 명령의 현재 스레드 ID를 설정하거나 표시합니다.                                  |

## <a name="using-dotnet-dump"></a>`dotnet-dump` 사용

첫 번째 단계는 덤프를 수집하는 것입니다. 코어 덤프가 이미 생성된 경우 이 단계를 건너뛸 수 있습니다. 운영 체제 또는 .NET Core 런타임의 기본 제공 [dump 생성 기능](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)은 각각 코어 덤프를 만들 수 있습니다.

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

이제 `analyze` 명령을 사용하여 코어 덤프를 분석합니다.

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

이 작업을 수행하면 다음과 같은 명령을 허용하는 대화형 세션이 열립니다.

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

앱을 종료한 처리되지 않은 예외를 보려면 다음을 수행합니다.

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a>Docker에 대한 특별 지침

Docker에서 실행되는 경우 덤프 수집에 `SYS_PTRACE` 기능(`--cap-add=SYS_PTRACE` 또는 `--privileged`)이 필요합니다.

Microsoft .NET Core SDK Linux Docker 이미지에서 일부 `dotnet-dump` 명령은 다음과 같은 예외를 throw할 수 있습니다.

> 처리되지 않은 예외: System.DllNotFoundException: 'libdl.so' 공유 라이브러리 또는 해당 종속성 예외 중 하나를 로드할 수 없습니다.

이 문제를 해결하려면 "libc6-dev" 패키지를 설치하세요.

## <a name="see-also"></a>참고 항목

- [메모리 덤프 수집 및 분석 블로그](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [힙 분석 도구(dotnet-gcdump)](dotnet-gcdump.md)
