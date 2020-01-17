---
title: 메모리 누수 디버그 자습서
description: .NET Core의 메모리 누수를 디버그하는 방법을 알아봅니다.
ms.topic: tutorial
ms.date: 12/17/2019
ms.openlocfilehash: cb137503cbc81f5ab9438dadcf1dc1c6750a1ca8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715601"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a>자습서: .NET Core의 메모리 누수 디버그

**이 문서의 적용 대상: ✓** .NET Core 3.0 SDK 이상 버전

이 자습서에서는 .NET Core 메모리 누수를 분석하는 도구를 보여줍니다.

이 자습서에서는 의도적으로 메모리가 누수되도록 설계된 샘플 앱을 사용합니다. 이 샘플은 연습용으로 제공됩니다. 의도치 않게 메모리 누수가 발생하는 앱을 분석할 수 있습니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
>
> - [dotnet-counters](dotnet-counters.md)를 사용하여 관리되는 메모리 사용량을 검사합니다.
> - 덤프 파일을 생성합니다.
> - 덤프 파일을 사용하여 메모리 사용량을 분석합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 자습서에서는 다음을 사용합니다.

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전
- 프로세스를 나열하는 [dotnet-trace](dotnet-trace.md).
- 관리되는 메모리 사용량을 검사하는 [dotnet-counters](dotnet-counters.md).
- 덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md).
- 진단할 [샘플 디버그 대상](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) 앱.

이 자습서에서는 샘플 및 도구가 설치되고 사용할 준비가 되었다고 가정합니다.

## <a name="examine-managed-memory-usage"></a>관리되는 메모리 사용량 검사

이 시나리오의 근본 원인을 해결하는 데 도움이 되도록 진단 데이터 수집을 시작하기 전에 실제로 메모리 누수(메모리 증가)가 발생하는지 확인해야 합니다. [dotnet-counters](dotnet-counters.md) 도구를 사용하여 이를 확인할 수 있습니다.

콘솔 창을 열고 [샘플 디버그 대상](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)을 다운로드하고 압축을 푼 디렉터리로 이동합니다. 대상을 실행합니다.

```dotnetcli
dotnet run
```

별도의 콘솔에서 [dotnet-trace](dotnet-trace.md) 도구를 사용하여 프로세스 ID를 찾습니다.

```console
dotnet-trace ps
```

출력은 다음과 비슷해야 합니다.

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

이제 [dotnet-counters](dotnet-counters.md) 도구를 사용하여 관리되는 메모리 사용량을 검사합니다. `--refresh-interval`을 새로 고침 간격(초)을 지정합니다.

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

라이브 출력은 다음과 비슷해야 합니다.

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

이 줄에 집중합니다.

```console
    GC Heap Size (MB)                                  4
```

시작 직후 관리되는 힙 메모리가 4MB인 것을 알 수 있습니다.

이제 URL `http://localhost:5000/api/diagscenario/memleak/20000`을 입력합니다.

메모리 사용량이 30MB로 증가하는 것을 확인합니다.

```console
    GC Heap Size (MB)                                 30
```

메모리 사용량을 확인하여 메모리가 증가 또는 감소하는지를 확실히 알 수 있습니다. 다음 단계는 메모리 분석에 적합한 데이터를 수집하는 것입니다.

### <a name="generate-memory-dump"></a>메모리 덤프 생성

가능한 메모리 누수를 분석할 때 앱의 메모리 힙에 액세스해야 합니다. 그런 다음 메모리 내용을 분석할 수 있습니다. 개체 간의 관계를 살펴보면 메모리가 확보되지 않는 이유에 대하여 이론을 만들 수 있습니다. 일반적인 진단 데이터 원본은 Windows의 메모리 덤프 또는 Linux의 해당 코어 덤프입니다. .NET Core 애플리케이션의 덤프를 생성하려면 [dotnet-dump)](dotnet-dump.md) 도구를 사용할 수 있습니다.

이전에 시작된 [샘플 디버그 대상](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)을 사용하여 다음 명령을 실행하고 Linux 코어 덤프를 생성합니다.

```dotnetcli
dotnet-dump collect -p 4807
```

그 결과, 동일한 폴더에 코어 덤프가 생성됩니다.

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a>실패한 프로세스 다시 시작

덤프가 수집되면 실패한 프로세스를 진단하는 데 충분한 정보가 확보될 것입니다. 실패한 프로세스가 프로덕션 서버에서 실행 중이라면 프로세스를 다시 시작하여 단기 수정하기에 가장 적합한 때입니다.

이 자습서에서는 [샘플 디버그 대상](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)이 완료되었으므로 이를 종료할 수 있습니다. 서버를 시작한 터미널로 이동하고 `Control-C`를 누릅니다.

### <a name="analyze-the-core-dump"></a>코어 덤프 분석

이제 코어 덤프가 생성되었으므로 [dotnet-dump)](dotnet-dump.md) 도구를 사용하여 덤프를 분석합니다.

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

여기서 `core_20190430_185145`는 분석하려는 코어 덤프의 이름입니다.

> [!NOTE]
> *libdl.so*를 찾을 수 없다는 오류가 표시되는 경우 *libc6-dev* 패키지를 설치해야 할 수 있습니다. 자세한 내용은 [Linux에서 .NET Core의 필수 조건](../linux-prerequisites.md)을 참조하세요.

SOS 명령을 입력할 수 있는 프롬프트가 표시됩니다. 일반적으로는 관리되는 힙의 전반적인 상태를 확인하는 것이 가장 좋습니다.

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

여기에서 대부분의 개체는 `String` 또는 `Customer` 개체임을 확인할 수 있습니다.

MT(메서드 테이블)와 함께 `dumpheap` 명령을 사용하여 모든 `String` 인스턴스의 목록을 가져올 수 있습니다.

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

이제 `System.String` 인스턴스에 `gcroot` 명령을 사용하여 개체가 루팅된 방법과 이유를 확인할 수 있습니다. 이 명령은 30MB 힙까지 몇 분이 걸리므로 잠시 기다려 주세요.

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

`Customer` 개체에서 직접적으로, `CustomerCache` 개체에서 간접적으로 `String`을 보유하는 것을 알 수 있습니다.

개체를 계속 덤프하여 대부분의 `String` 개체가 비슷한 패턴을 따르는지 확인할 수 있습니다. 이 시점에서 조사를 통해 코드에서 근본 원인을 식별하는 데 충분한 정보가 제공됩니다.

이 일반적인 절차를 사용하면 주요 메모리 누수의 원인을 식별할 수 있습니다.

## <a name="clean-up-resources"></a>리소스 정리

이 자습서에서 샘플 웹 서버를 시작했습니다. 이 서버는 [실패한 프로세스 다시 시작](#restart-the-failed-process) 섹션에서 설명한 것과 같이 종료되어 있어야 합니다.

또한 생성된 덤프 파일을 삭제할 수 있습니다.

## <a name="next-steps"></a>다음 단계

축하합니다. 이 자습서를 마쳤습니다.

더 많은 진단 자습서가 게시되어 있습니다. [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) 리포지토리에서 초안 버전을 읽을 수 있습니다.

이 자습서에서는 핵심 .NET 진단 도구의 기본 사항을 설명했습니다. 고급 사용은 다음 참조 설명서를 참조하세요.

* 프로세스를 나열하는 [dotnet-trace](dotnet-trace.md).
* 관리되는 메모리 사용량을 검사하는 [dotnet-counters](dotnet-counters.md).
* 덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md).
