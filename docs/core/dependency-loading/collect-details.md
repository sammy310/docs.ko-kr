---
title: 자세한 어셈블리 로딩 정보 수집 - .NET Core
description: .NET Core에서 어셈블리 로딩 정보를 수집하는 방법에 대한 설명
author: elinor-fung
ms.author: elfung
ms.date: 11/17/2020
ms.openlocfilehash: b121982995b440ade6d72190f44f9b9d237c8af6
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506506"
---
# <a name="collect-detailed-assembly-loading-information"></a>자세한 어셈블리 로딩 정보 수집

.NET 5.0부터 런타임은 어셈블리 로딩 문제를 진단하는 데 도움이 되도록 [관리되는 어셈블리 로딩](loading-managed.md)에 대한 자세한 정보와 함께 `EventPipe`를 통해 이벤트를 내보낼 수 있습니다. 이러한 [이벤트](../../fundamentals/diagnostics/runtime-loader-binder-events.md)는 `Microsoft-Windows-DotNETRuntime` 공급자가 `AssemblyLoader` 키워드(`0x4`)로 내보냅니다.

## <a name="prerequisites"></a>사전 준비 사항

- [.NET 5.0 SDK](https://dotnet.microsoft.com/download) 이상 버전
- [dotnet-trace](../diagnostics/dotnet-trace.md) 도구.

## <a name="collect-a-trace-with-assembly-loading-events"></a>어셈블리 로딩 이벤트를 사용하여 추적 수집

런타임에 어셈블리 로딩 이벤트를 사용하도록 설정하고 그 추적을 수집하려면 `dotnet-trace`를 다음 명령과 함께 사용합니다.

```console
dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id <pid>
```

그러면 지정된 `<pid>`의 추적이 수집되어 `Microsoft-Windows-DotNETRuntime` 공급자에서 `AssemblyLoader` 이벤트를 사용할 수 있습니다. 결과는 `.nettrace` 파일입니다.

## <a name="view-a-trace"></a>추적 보기

수집된 추적 파일은 Windows에서 [PerfView](https://github.com/microsoft/perfview)의 이벤트 보기를 사용하여 볼 수 있습니다. 모든 어셈블리 로딩 이벤트에는 접두사 `Microsoft-Windows-DotNETRuntime/AssemblyLoader`가 붙습니다.

## <a name="example-on-windows"></a>예제(Windows)

이 예제에서는 [어셈블리 로딩 확장 지점 샘플](https://github.com/dotnet/samples/tree/master/core/extensions/AssemblyLoading)을 사용합니다. 애플리케이션에서 어셈블리 `MyLibrary`를 로드하려고 합니다. 이 어셈블리는 애플리케이션에서 참조하지 않으므로 성공적으로 로드하려면 어셈블리 로딩 확장 지점에서 처리해야 합니다.

### <a name="collect-the-trace"></a>추적 수집

01. 다운로드한 샘플이 있는 디렉터리로 이동합니다. 다음을 사용하여 애플리케이션을 빌드합니다.

    ```console
    dotnet build
    ```

01. 키를 누를 때까지 대기하며 일시 중지해야 함을 나타내는 인수를 사용하여 애플리케이션을 시작합니다. 다시 시작할 때 애플리케이션이 성공적인 로드에 필요한 처리 없이 기본 `AssemblyLoadContext`에서 어셈블리를 로드하려고 합니다. 출력 디렉터리로 이동하여 다음을 실행합니다.

    ```console
    AssemblyLoading.exe /d default
    ```

01. 애플리케이션의 프로세스 ID를 찾습니다.

    ```console
    dotnet-trace ps
    ```

    출력에 사용 가능한 프로세스가 나열됩니다. 예를 들어:

    ```console
    35832 AssemblyLoading C:\src\AssemblyLoading\bin\Debug\net5.0\AssemblyLoading.exe
    ```

01. 실행 중인 애플리케이션에 `dotnet-trace`를 연결합니다.

    ```console
    dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id 35832
    ```

01. 애플리케이션을 실행하는 창에서 아무 키나 눌러 프로그램을 계속 실행합니다. 애플리케이션이 종료되면 추적이 자동으로 중지됩니다.

### <a name="view-the-trace"></a>추적 보기

[PerfView](https://github.com/microsoft/perfview)에서 수집된 추적을 열고 이벤트 보기를 엽니다. 이벤트 목록을 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 이벤트로 필터링합니다.

:::image type="content" source="media/collect-details/assembly-loader-filter.png" alt-text="PerfView 어셈블리 로더 필터 이미지":::

추적이 시작된 후 애플리케이션에서 발생한 모든 어셈블리 로드가 표시됩니다. 이 예제에 대한 원하는 어셈블리 로드 작업 `MyLibrary`를 검사하기 위해 몇 가지 추가 필터링을 수행할 수 있습니다.

### <a name="assembly-loads"></a>어셈블리 로드

왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`Start`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstart-event) 및 [`Stop`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstop-event) 이벤트로 보기를 필터링합니다. `AssemblyName`, `ActivityID` 및 `Success` 열을 보기에 추가합니다. `MyLibrary`를 포함하는 이벤트로 필터링합니다.

:::image type="content" source="media/collect-details/start-stop.png" alt-text="PerfView 시작 및 중지 이벤트 이미지":::

| 이벤트 이름             | AssemblyName                                      | ActivityID | Success |
| ---------------------- | ------------------------------------------------- | ---------- | ------- |
| `AssemblyLoader/Start` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     |         |
| `AssemblyLoader/Stop`  | `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     | False   |

`Stop` 이벤트에 하나의 `Start`/`Stop` 쌍과 `Success=False`가 표시되어 로드 작업이 실패했음을 나타냅니다. 두 이벤트의 활동 ID는 동일합니다. 활동 ID를 사용하여 다른 모든 어셈블리 로더 이벤트를 이 로드 작업에 해당하는 이벤트로만 필터링할 수 있습니다.

### <a name="breakdown-of-attempt-to-load"></a>로드 시도 분석

로드 작업에 대한 자세한 분석을 보려면 왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`ResolutionAttempted` 이벤트](../../fundamentals/diagnostics/runtime-loader-binder-events.md#resolutionattempted-event)로 보기를 필터링합니다. `AssemblyName`, `Stage` 및 `Result` 열을 보기에 추가합니다. `Start`/`Stop` 쌍의 활동 ID를 갖는 이벤트로 필터링합니다.

:::image type="content" source="media/collect-details/resolution-attempted.png" alt-text="PerfView ResolutionAttempted 이벤트 이미지":::

| 이벤트 이름                           | AssemblyName                                      | 단계                               | 결과             |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AppDomainAssemblyResolveEvent`     | `AssemblyNotFound` |

위의 이벤트는 어셈블리 로더가 현재 로드 컨텍스트를 확인하고, 관리되는 애플리케이션 어셈블리에 대한 기본 검색 논리를 실행하고, <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대해 처리기를 호출하고, <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>에 대해 처리기를 호출하여 어셈블리를 확인하려고 했음을 나타냅니다. 이러한 모든 단계에 대해 어셈블리를 찾을 수 없습니다.

### <a name="extension-points"></a>확장 지점

호출된 확장 지점을 확인하려면 왼쪽에 있는 이벤트 목록을 사용하여 `Microsoft-Windows-DotNETRuntime/AssemblyLoader` 아래의 [`AssemblyLoadContextResolvingHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadcontextresolvinghandlerinvoked-event) 및 [`AppDomainAssemblyResolveHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#appdomainassemblyresolvehandlerinvoked-event)로 보기를 필터링합니다. `AssemblyName` 및 `HandlerName` 열을 보기에 추가합니다. `Start`/`Stop` 쌍의 활동 ID를 갖는 이벤트로 필터링합니다.

:::image type="content" source="media/collect-details/extension-point.png" alt-text="PerfView 확장 지점 이벤트 이미지":::

| 이벤트 이름                                                  | AssemblyName                                      | HandlerName                      |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` |
| `AssemblyLoader/AppDomainAssemblyResolveHandlerInvoked`     | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAppDomainAssemblyResolve`     |

위의 이벤트는 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대해 `OnAssemblyLoadContextResolving`이라는 처리기가 호출되고 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트에 대해 `OnAppDomainAssemblyResolve`이라는 처리기가 호출되었음을 나타냅니다.

### <a name="collect-another-trace"></a>다른 추적 수집

<xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 이벤트에 대한 처리기가 `MyLibrary` 어셈블리를 로드하도록 인수를 사용하여 애플리케이션을 실행합니다.

```console
AssemblyLoading /d default alc-resolving
```

[위의 단계](#collect-the-trace)를 사용하여 다른 `.nettrace` 파일을 수집하고 엽니다.

다시 `MyLibrary`에 대한 `Start` 및 `Stop` 이벤트로 필터링합니다. `Start`/`Stop` 쌍과 그 사이에 또 다른 `Start`/`Stop`이 표시됩니다. 내부 로드 작업은 <xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType>을 호출했을 때 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>에 대한 처리기를 통해 트리거된 로드를 나타냅니다. 이번에는 `Stop` 이벤트에 `Success=True`가 표시되어 로드 작업이 성공했음을 나타냅니다. `ResultAssemblyPath` 필드는 결과 어셈블리의 경로를 표시합니다.

:::image type="content" source="media/collect-details/start-stop-success.png" alt-text="PerfView 성공한 이벤트 시작 및 중지 이벤트 이미지":::

| 이벤트 이름             | AssemblyName                                                       | ActivityID | Success | ResultAssemblyPath                                      |
| ---------------------- | ------------------------------------------------------------------ |------------|---------| ------------------------------------------------------- |
| `AssemblyLoader/Start` |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     |         |                                                         |
| `AssemblyLoader/Start` | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | //1/2/1/   |         |                                                         |
| `AssemblyLoader/Stop`  | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | //1/2/1/   | True    | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |
| `AssemblyLoader/Stop`  |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     | True    | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

그런 다음 외부 로드의 활동 ID를 갖는 `ResolutionAttempted` 이벤트를 살펴보고 어셈블리가 성공적으로 확인된 단계를 찾을 수 있습니다. 이번에는 이벤트에 `AssemblyLoadContextResolvingEvent` 단계가 성공했다고 표시될 것입니다. `ResultAssemblyPath` 필드는 결과 어셈블리의 경로를 표시합니다.

:::image type="content" source="media/collect-details/resolution-attempted-success.png" alt-text="PerfView 성공한 ResolutionAttempted 이벤트 이미지":::

| 이벤트 이름                           | AssemblyName                                      | 단계                               | 결과             | ResultAssemblyPath |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `Success`          | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

`AssemblyLoadContextResolvingHandlerInvoked` 이벤트를 살펴보면 `OnAssemblyLoadContextResolving`라는 처리기가 호출되었음을 알 수 있습니다. `ResultAssemblyPath` 필드는 처리기에서 반환된 어셈블리의 경로를 표시합니다.

:::image type="content" source="media/collect-details/extension-point-success.png" alt-text="PerfView 성공한 확장 지점 이벤트 이미지":::

| 이벤트 이름                                                  | AssemblyName                                      | HandlerName                      | ResultAssemblyPath |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- | ------------------ |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

어셈블리가 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 발생시키는 로딩 알고리즘 단계에 도달하기 전에 성공적으로 로드되었으므로 `AppDomainAssemblyResolveEvent` 단계 또는 `AppDomainAssemblyResolveHandlerInvoked` 이벤트가 포함된 `ResolutionAttempted` 이벤트가 더 이상 없습니다.

## <a name="see-also"></a>참고 항목

- [어셈블리 로더 이벤트](../../fundamentals/diagnostics/runtime-loader-binder-events.md)
- [dotnet-trace](../diagnostics/dotnet-trace.md)
- [PerfView](https://github.com/microsoft/perfview)
