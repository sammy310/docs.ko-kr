---
title: 덤프 - .NET
description: .NET의 덤프에 대한 소개입니다.
ms.date: 10/12/2020
ms.openlocfilehash: f68d9bd804350366625df014df4d9ca0641d5d4d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188558"
---
# <a name="dumps"></a>덤프

덤프는 프로세스가 생성된 시점의 프로세스 스냅샷을 포함하는 파일이며, 애플리케이션의 상태를 검사하는 데 유용합니다. 프로덕션 환경이나 CI 환경과 같이 디버거를 연결하기 어려운 경우에는 덤프를 사용하여 .NET 애플리케이션을 디버그할 수 있습니다. 덤프를 사용하면 문제가 있는 프로세스의 상태를 캡처하여 애플리케이션을 중지하지 않고도 검사할 수 있습니다.

## <a name="collect-dumps"></a>덤프 수집

덤프는 앱을 실행하는 플랫폼에 따라 다양한 방법으로 수집할 수 있습니다.

> [!NOTE]
> 컨테이너 내에서 덤프를 수집하려면 PTRACE 기능이 필요하며, 이 기능은 `--cap-add=SYS_PTRACE` 또는 `--privileged`를 통해 추가할 수 있습니다.
> [!NOTE]
> 덤프는 실행 중인 프로세스의 전체 메모리를 포함할 수 있기 때문에 중요한 정보를 포함할 수 있습니다. 덤프를 처리할 때는 모든 보안 제한 사항과 지침을 고려해야 합니다.

### <a name="collecting-dumps-on-crash"></a>크래시 발생 시 덤프 수집

환경 변수를 사용하여 크래시 발생 시 덤프를 수집하도록 애플리케이션을 구성할 수 있습니다. 그러면 크래시가 발생한 이유를 파악하려는 경우에 유용합니다. 예를 들어 예외가 throw될 때 덤프를 캡처하면 크래시된 앱의 상태를 검사하여 문제를 식별하는 데 도움이 됩니다.

다음 표에서는 크래시 발생 시 덤프를 수집하기 위해 구성할 수 있는 환경 변수를 보여 줍니다.

|환경 변수|Description|기본값|
|-------|---------|---|
|`COMPlus_DbgEnableMiniDump`|1로 설정하면 코어 덤프 생성을 사용하도록 설정합니다.|0|
|`COMPlus_DbgMiniDumpType`|수집할 덤프의 유형입니다. 자세한 내용은 아래 표를 참조하세요.|2(`MiniDumpWithPrivateReadWriteMemory`)|
|`COMPlus_DbgMiniDumpName`|덤프를 쓸 대상 파일의 경로입니다.|`/tmp/coredump.<pid>`|
|`COMPlus_CreateDumpDiagnostics`|1로 설정하면 덤프 프로세스의 진단 로깅을 사용하도록 설정합니다.|0|

다음 표에서는 값으로 지정할 수 있는 `COMPlus_DbgMiniDumpType`에 사용할 수 있는 모든 옵션을 보여 줍니다. 예를 들어 `COMPlus_DbgMiniDumpType`을 1로 설정하면 크래시 발생 시 `MiniDumpNormal` 유형 덤프가 수집됩니다.

|값|Name|설명|
|-----|----|-----------|
|1|`MiniDumpNormal`|프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 정보만 포함합니다. 제한된 GC 힙 메모리 및 정보입니다.|
|2|`MiniDumpWithPrivateReadWriteMemory`|프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 GC 힙 및 정보를 포함합니다.|
|3|`MiniDumpFilterTriage`|프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 정보만 포함합니다. 제한된 GC 힙 메모리 및 정보입니다.|
|4|`MiniDumpWithFullMemory`|프로세스의 액세스할 수 있는 모든 메모리를 포함합니다. 원시 메모리 데이터는 끝에 포함되므로 원시 메모리 정보 없이 초기 구조를 직접 매핑할 수 있습니다. 이 옵션을 선택하면 매우 큰 파일이 생성될 수 있습니다.|

### <a name="collecting-dumps-at-specific-point-in-time"></a>특정 시점에 덤프 수집

앱이 아직 크래시되지 않은 경우에 덤프를 수집하는 것이 좋습니다. 예를 들어 교착 상태에 있는 것으로 보이는 애플리케이션의 상태를 검사하려는 경우 크래시 발생 시 덤프를 수집하도록 환경 변수를 구성하면 앱이 계속 실행되고 있기 때문에 유용하지 않게 됩니다.

직접적인 요청에 따라 덤프를 수집하려면 덤프를 수집하고 분석하는 CLI 도구인 `dotnet-dump`를 사용할 수 있습니다. `dotnet-dump`를 사용하여 덤프를 수집하는 방법에 대한 자세한 내용은 [Dump collection and analysis utility](dotnet-dump.md)(덤프 수집 및 분석 유틸리티)를 참조하세요.

## <a name="analyze-dumps"></a>덤프 분석

[`dotnet-dump`](dotnet-dump.md) CLI 도구를 사용하거나 [Visual Studio](/visualstudio/debugger/using-dump-files)에서 덤프를 분석할 수 있습니다.

> [!NOTE]
> Visual Studio 버전 16.8 이상에서는 .NET Core 3.1.7 이상에서 생성된 [Linux 덤프를 열](https://devblogs.microsoft.com/visualstudio/linux-managed-memory-dump-debugging/) 수 있습니다.  
> [!NOTE]
> 네이티브 디버깅이 필요한 경우 [SOS 디버거 확장](sos-debugging-extension.md)을 [Linux 및 macOS의 LLDB](debug-linux-dumps.md#analyze-dumps-on-linux)와 함께 사용할 수 있습니다. SOS는 Windows의 [Windbg/cdb](/windows-hardware/drivers/debugger/debugger-download-tools)와 함께 사용할 수도 있지만 Visual Studio와 함께 사용하는 것이 좋습니다.

## <a name="see-also"></a>참조

덤프를 활용하여 .NET 애플리케이션에서 문제를 진단하는 방법에 대해 자세히 알아보세요.

* [Debug Linux dumps](debug-linux-dumps.md)(Linux 덤프 디버그) 자습서에서는 Linux에서 수집된 덤프를 디버그하는 방법을 안내합니다.

* [Debug deadlock](debug-deadlock.md)(교착 상태 디버그) 자습서에서는 .NET 애플리케이션에서 덤프를 사용하여 교착 상태를 디버그하는 방법을 안내합니다.
