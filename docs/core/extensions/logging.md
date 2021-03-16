---
title: .NET의 로깅
author: IEvangelist
description: Microsoft.Extensions.Logging NuGet 패키지에서 제공하는 로깅 프레임워크 사용법을 알아보세요.
ms.author: dapine
ms.date: 02/19/2021
ms.openlocfilehash: 834331b9e103138012bbe91586d0d5a7c08654ce
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102402169"
---
# <a name="logging-in-net"></a>.NET의 로깅

.NET는 다양한 기본 제공 및 타사 로깅 공급자에서 작동하는 로깅 API를 지원합니다. 이 문서에서는 기본 제공 공급자를 이용하여 로깅 API를 사용하는 방법을 보여줍니다. 이 문서에 표시된 대부분의 코드 예제는 [제네릭 호스트](generic-host.md)를 사용하는 모든 .NET 앱에 적용됩니다. 제네릭 호스트를 사용하지 않는 앱의 경우 [비호스트 콘솔 앱](#non-host-console-app)을 참조하세요.

## <a name="create-logs"></a>로그 만들기

로그를 만들려면 [DI(종속성 주입)](dependency-injection.md)의 <xref:Microsoft.Extensions.Logging.ILogger%601> 개체를 사용합니다.

다음 예제가 하는 일:

- 형식이 `Worker`인 정규화된 이름의 로그 ‘범주’를 사용하는 `ILogger<Worker>` 로거를 만듭니다. 로그 범주는 각 로그와 연결된 문자열입니다.
- <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A>을 호출하여 `Information` 수준에 로그합니다. 로그 *수준* 은 기록된 이벤트의 심각도를 나타냅니다.

:::code language="csharp" source="snippets/configuration/worker-service/Worker.cs" range="9-24" highlight="12":::

[수준](#log-level) 및 [범주](#log-category)는 이 문서의 뒷부분에 자세히 설명되어 있습니다.

## <a name="configure-logging"></a>로깅 구성

로깅 구성은 일반적으로 *appsettings*.`{Environment}` *.json* 파일의 `Logging` 섹션에서 제공됩니다. 다음 *appsettings.Development.json* 파일은 .NET 작업자 서비스 템플릿으로 생성되었습니다.

:::code language="json" source="snippets/configuration/worker-service/appsettings.Development.json":::

앞의 JSON에서:

- `"Default"`, `"Microsoft"` 및 `"Microsoft.Hosting.Lifetime"` 범주가 지정되었습니다.
- `"Microsoft"` 범주는 `"Microsoft"`로 시작하는 모든 범주에 적용됩니다.
- `"Microsoft"` 범주는 로그 수준 `Warning` 이상에 로그됩니다.
- `"Microsoft.Hosting.Lifetime"` 범주는 `"Microsoft"` 범주보다 구체적이므로 `"Microsoft.Hosting.Lifetime"` 범주는 로그 수준 “정보” 이상에 로그됩니다.
- 특정 로그 공급자를 지정하지 않았으므로 `LogLevel`은 [Windows EventLog](logging-providers.md#windows-eventlog)를 제외하고 사용하도록 설정한 모든 로깅 공급자에 적용됩니다.

`Logging` 속성은 <xref:Microsoft.Extensions.Logging.LogLevel> 및 로그 공급자 속성을 포함할 수 있습니다. `LogLevel` 속성은 선택한 범주에 대해 로그할 최소 [수준](#log-level)을 지정합니다. 위의 JSON에서는 `Information` 및 `Warning` 로그 수준을 지정했습니다. `LogLevel` 로그의 심각도를 나타내며 0에서 6 사이의 범위입니다.

`Trace` = 0, `Debug` = 1, `Information` = 2, `Warning` = 3, `Error` = 4, `Critical` = 5 및 `None` = 6

`LogLevel`을 지정하면 지정된 수준 이상의 메시지에 대해 로깅을 사용하도록 설정됩니다. 위의 JSON에서 `Default` 범주는 `Information` 이상에 대해 로그됩니다. 예를 들어 `Information`, `Warning`, `Error` 및 `Critical` 메시지가 로그됩니다. `LogLevel` 지정하지 않으면 로깅은 `Information` 수준으로 기본 설정됩니다. 자세한 내용은 [로그 수준](#log-level)을 참조하세요.

공급자 속성에서 `LogLevel` 속성을 지정할 수 있습니다. 공급자 아래의 `LogLevel`은 해당 공급자에 대해 로그할 수준을 지정하고 공급자 이외의 로그 설정을 재정의합니다. 다음 *appsettings.json* 파일을 고려하세요.

:::code language="json" source="snippets/configuration/worker-service/appsettings.Staging.json":::

`Logging.{ProviderName}.LogLevel`의 설정은 `Logging.LogLevel`의 설정을 재정의합니다. 위의 JSON에서는 `Debug` 공급자의 기본 로그 수준이 `Information`로 설정되었습니다.

`Logging:Debug:LogLevel:Default:Information`

위 설정은 `Microsoft.Hosting`을 제외하고 모든 `Logging:Debug:` 범주에 대해 `Information` 로그 수준을 지정합니다. 특정 범주를 나열하면 특정 범주로 기본 범주가 재정의됩니다. 위의 JSON에서 `Logging:Debug:LogLevel` 범주 `"Microsoft.Hosting"` 및 `"Default"`는 `Logging:LogLevel`의 설정을 재정의합니다.

최소 로그 수준은 다음에 대해 지정할 수 있습니다.

- 특정 공급자:  예를 들면 `Logging:EventSource:LogLevel:Default:Information`과 같습니다.
- 특정 범주: 예를 들면 `Logging:LogLevel:Microsoft:Warning`과 같습니다.
- 모든 공급자와 모든 범주: `Logging:LogLevel:Default:Warning`

최소 수준 이하의 모든 로그는 다음과 같이 ***되지 않습니다***.

- 공급자에 전달됩니다.
- 로그되거나 표시됩니다.

모든 로그를 표시하지 않으려면 [LogLevel.None](xref:Microsoft.Extensions.Logging.LogLevel)을 지정합니다. `LogLevel.None`의 값은 `LogLevel.Critical`(5)보다 높은 6입니다.

공급자가 [로그 범위](#log-scopes)를 지원하는 경우 `IncludeScopes`는 사용 가능 여부를 나타냅니다. 자세한 내용은 [로그 범위](#log-scopes)를 참조하세요.

다음 *appsettings.json* 파일에는 모든 기본 제공 공급자에 대한 설정이 포함되어 있습니다.

:::code language="json" source="snippets/configuration/worker-service/appsettings.Production.json":::

앞의 예제에서:

- 범주 및 수준은 제안된 값이 아닙니다. 기본 공급자를 모두 표시하기 위해 제공되는 샘플입니다.
- `Logging.{ProviderName}.LogLevel`의 설정은 `Logging.LogLevel`의 설정을 재정의합니다. 예를 들어 `Debug.LogLevel.Default` 수준은 `LogLevel.Default`수준을 재정의합니다.
- 각 기본 공급자의 ‘별칭’을 사용합니다. 각 공급자는 정규화된 형식 이름 대신 구성에서 사용할 수 있는 *별칭* 을 정의합니다. 기본 제공 공급자의 별칭은 다음과 같습니다.
  - Console
  - Debug
  - EventSource
  - EventLog
  - AzureAppServicesFile
  - AzureAppServicesBlob
  - ApplicationInsights

### <a name="set-log-level-by-command-line-environment-variables-and-other-configuration"></a>명령줄, 환경 변수 및 기타 구성으로 로그 수준 설정

로그 수준은 [구성 공급자](configuration-providers.md) 중 하나로 설정할 수 있습니다. 예를 들어 값이 `Information`인 `Logging:LogLevel:Microsoft`라는 지속형 환경 변수를 만들 수 있습니다.

## <a name="command-line"></a>[명령줄](#tab/command-line)

로그 수준 값이 지정되면 지속형 환경 변수를 만들고 할당합니다.

```CMD
:: Assigns the env var to the value
setx "Logging__LogLevel__Microsoft" "Information" /M
```

**명령 프롬프트** 의 ‘새’ 인스턴스에서 환경 변수를 읽습니다.

```CMD
:: Prints the env var value
echo %Logging__LogLevel__Microsoft%
```

## <a name="powershell"></a>[PowerShell](#tab/powershell)

로그 수준 값이 지정되면 지속형 환경 변수를 만들고 할당합니다.

```powershell
# Assigns the env var to the value
[System.Environment]::SetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Information", "Machine")
```

**PowerShell** 의 ‘새’ 인스턴스에서 환경 변수를 읽습니다.

```powershell
# Prints the env var value
[System.Environment]::GetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Machine")
```

## <a name="bash"></a>[Bash](#tab/bash)

로그 수준 값이 지정되면 지속형 환경 변수를 만들고 할당합니다.

```Bash
# Assigns the env var to the value, persists it across sessions
echo export Logging__LogLevel__Microsoft="Information" >> ~/.bashrc && source ~/.bashrc
```

환경 변수를 읽는 방법.

```Bash
# Prints the env var value
echo $Logging__LogLevel__Microsoft

# Or use printenv:
# printenv Logging__LogLevel__Microsoft
```

> [!NOTE]
> `.`(마침표)를 포함하는 이름을 사용하여 환경 변수를 구성하는 경우 **Stack Exchange** 에 대한 "점(.)이 포함된 변수 내보내기" 질문 및 해당 [채택된 답변](https://unix.stackexchange.com/a/93533)을 참조하세요.

---

이전의 환경 설정은 환경에서 지속됩니다. .NET 작업자 서비스 템플릿을 사용하여 만든 앱을 사용할 때 설정을 테스트하려면 환경 변수가 할당된 후에 프로젝트 디렉터리에서 `dotnet run` 명령을 사용합니다.

```dotnetcli
dotnet run
```

> [!TIP]
> 환경 변수를 설정한 후에는 IDE(통합 개발 환경)를 다시 시작하여 새로 추가된 환경 변수를 사용할 수 있는지 확인하세요.

[Azure App Service](https://azure.microsoft.com/services/app-service/)의 **설정 > 구성** 페이지에서 **새 애플리케이션 설정** 을 선택합니다. Azure App Service 애플리케이션 설정은,

- 미사용 시 암호화되고 암호화된 채널을 통해 전송됩니다.
- 환경 변수로 노출됩니다.

환경 변수를 사용하여 .NET 구성 값을 설정하는 방법에 대한 자세한 내용은 [환경 변수](configuration-providers.md#environment-variable-configuration-provider)를 참조하세요.

## <a name="how-filtering-rules-are-applied"></a>필터링 규칙 적용 방식

<xref:Microsoft.Extensions.Logging.ILogger%601> 개체를 만들 때 <xref:Microsoft.Extensions.Logging.ILoggerFactory> 개체는 공급자마다 해당 로거에 적용할 단일 규칙을 선택합니다. `ILogger` 인스턴스에서 작성된 모든 메시지는 선택한 규칙에 따라 필터링됩니다. 사용 가능한 규칙 중에서 각 공급자 및 범주 쌍과 가장 관련이 많은 규칙이 선택됩니다.

지정된 범주에 대한 `ILogger`가 생성되면 다음 알고리즘이 각 공급자에 사용됩니다.

- 공급자 또는 공급자의 별칭과 일치하는 모든 규칙을 선택합니다. 일치하는 규칙이 없는 경우 빈 공급자가 있는 모든 규칙을 선택합니다.
- 앞 단계의 결과에서 일치하는 범주 접두사가 가장 긴 규칙을 선택합니다. 일치하는 규칙이 없는 경우 범주를 지정하지 않는 규칙을 모두 선택합니다.
- 여러 규칙을 선택하는 경우 **마지막** 규칙을 사용합니다.
- 규칙을 선택하지 않은 경우 <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.SetMinimumLevel(Microsoft.Extensions.Logging.ILoggingBuilder,Microsoft.Extensions.Logging.LogLevel)?displayProperty=nameWithType>를 사용하여 최소 로깅 수준을 지정합니다.

## <a name="log-category"></a>로그 범주

`ILogger` 개체가 생성되면 ‘범주’가 지정됩니다. 해당 범주는 `ILogger`의 해당 인스턴스에서 만든 각 로그 메시지에 포함됩니다. 범주 문자열은 임의로 지정되지만 규칙은 클래스 이름을 사용하는 것입니다. 예를 들어 서비스가 다음 개체와 같이 정의된 애플리케이션에서 범주는 `"Example.DefaultService"`일 수 있습니다.

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger<DefaultService> _logger;

        public DefaultService(ILogger<DefaultService> logger) =>
            _logger = logger;

        // ...
    }
}
```

범주를 명시적으로 지정하려면 <xref:Microsoft.Extensions.Logging.LoggerFactory.CreateLogger%2A?displayProperty=nameWithType>를 호출합니다.

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger _logger;

        public DefaultService(ILoggerFactory loggerFactory) =>
            _logger = loggerFactory.CreateLogger("CustomCategory");

        // ...
    }
}
```

고정 이름을 사용하여 `CreateLogger`를 호출하면 여러 클래스/형식에서 사용할 때 유용할 수 있으므로 이벤트를 범주별로 구성할 수 있습니다.

`ILogger<T>`는 `T`의 정규화된 형식 이름으로 `CreateLogger`를 호출하는 것과 동일합니다.

## <a name="log-level"></a>로그 수준

다음 표에서는 <xref:Microsoft.Extensions.Logging.LogLevel> 값, 편리한 `Log{LogLevel}` 확장 메서드 및 추천 사용법을 설명합니다.

| LogLevel | 값 | 메서드 | Description |
|--|--|--|--|
| [추적](xref:Microsoft.Extensions.Logging.LogLevel) | 0 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogTrace%2A> | 가장 자세한 메시지를 포함합니다. 해당 메시지는 중요한 앱 데이터를 포함할 수 있습니다. 해당 메시지는 기본적으로 사용하지 않도록 설정되며 프로덕션에서 사용하도록 설정하면 ***안 됩니다***. |
| [디버그](xref:Microsoft.Extensions.Logging.LogLevel) | 1 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A> | 디버깅 및 개발을 위한 수준입니다. 너무 많으므로 프로덕션에서는 주의해서 사용합니다. |
| [정보](xref:Microsoft.Extensions.Logging.LogLevel) | 2 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> | 앱의 일반적인 흐름을 추적합니다. 장기적인 값이 있을 수 있습니다. |
| [경고](xref:Microsoft.Extensions.Logging.LogLevel) | 3 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogWarning%2A> | 비정상적이거나 예기치 않은 이벤트를 위한 수준입니다. 일반적으로 앱의 오류를 발생시키지 않는 오류 또는 조건을 포함합니다. |
| [오류](xref:Microsoft.Extensions.Logging.LogLevel) | 4 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogError%2A> | 처리할 수 없는 오류 및 예외를 위한 수준입니다. 해당 메시지는 전체 앱 오류가 아닌 현재 작업 또는 요청의 오류를 의미합니다. |
| [심각](xref:Microsoft.Extensions.Logging.LogLevel) | 5 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogCritical%2A> | 즉각적인 대응이 필요한 오류를 위한 수준입니다. 예: 데이터 손실 시나리오, 디스크 공간 부족. |
| [없음](xref:Microsoft.Extensions.Logging.LogLevel) | 6 |  | 메시지를 기록하지 않도록 지정합니다. |

위의 표에서는 `LogLevel`이 심각도가 낮은 것에서 높은 것 순으로 표시됩니다.

[Log](xref:Microsoft.Extensions.Logging.LoggerExtensions) 메서드의 첫 번째 매개 변수인 <xref:Microsoft.Extensions.Logging.LogLevel>은 로그의 심각도를 나타냅니다. 대부분의 개발자는 `Log(LogLevel, ...)` 대신 [Log{LogLevel}](xref:Microsoft.Extensions.Logging.LoggerExtensions) 확장 메서드를 호출합니다. `Log{LogLevel}` 확장 메서드는 [Log 메서드를 호출하고 LogLevel을 지정](https://github.com/dotnet/extensions/blob/release/3.1/src/Logging/Logging.Abstractions/src/LoggerExtensions.cs)합니다. 예를 들어 다음 두 로깅 호출은 기능이 동일하며 같은 로그를 생성합니다.

```csharp
public void LogDetails()
{
    var logMessage = "Details for log.";

    _logger.Log(LogLevel.Information, AppLogEvents.Details, logMessage);
    _logger.LogInformation(AppLogEvents.Details, logMessage);
}
```

`AppLogEvents.Details`는 이벤트 ID이며 상수 <xref:System.Int32> 값으로 암시적으로 표시됩니다. `AppLogEvents`는 여러 개의 명명된 식별자 상수를 노출하고 [로그 이벤트 ID](#log-event-id) 섹션에 표시되는 클래스입니다.

다음 코드는 `Information` 및 `Warning` 로그를 만듭니다.

```csharp
public async Task<T> GetAsync<T>(string id)
{
    _logger.LogInformation(AppLogEvents.Read, "Reading value for {Id}", id);

    var result = await _repository.GetAsync(id);
    if (result is null)
    {
        _logger.LogWarning(AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
    }

    return result;
}
```

위의 코드에서 첫 번째 `Log{LogLevel}` 매개 변수 `AppLogEvents.Read`은 [로그 이벤트 ID](#log-event-id)입니다. 두 번째 매개 변수는 나머지 메서드 매개 변수가 제공하는 인수 값에 대한 자리 표시자를 포함하고 있는 메시지 템플릿입니다. 메서드 매개 변수는 이 문서의 뒷부분에 있는 [메시지 템플릿](#log-message-template) 섹션에 설명되어 있습니다.

적절한 로그 수준을 구성하고 올바른 `Log{LogLevel}` 메서드를 호출하여 특정 스토리지 매체에 기록되는 로그 출력의 크기를 제어합니다. 예를 들어:

- 프로덕션:
  - `Trace` 또는 `Information` 수준 로깅은 자세한 로그 메시지를 대량으로 생성합니다. 비용을 관리하고 데이터 스토리지 제한을 초과하지 않으려면 `Trace` 및 `Information` 수준 메시지를 대용량, 저비용 데이터 저장소에 로그합니다. `Trace` 및 `Information`을 특정 범주로 제한하는 것이 좋습니다.
  - `Warning`~`Critical` 수준의 로깅은 적은 로그 메시지를 생성합니다.
    - 비용과 스토리지 제한이 일반적으로 문제가 되지 않습니다.
    - 로그가 적으므로 데이터 저장소를 더 유연하게 선택할 수 있습니다.
- 개발 중:
  - `Warning`로 설정합니다.
  - 문제를 해결할 때는 `Trace` 또는 `Information` 메시지를 추가합니다. 출력을 제한하려면 조사 중인 범주에 대해서만 `Trace` 또는 `Information`을 설정합니다.

다음 JSON에서는 `Logging:Console:LogLevel:Microsoft:Information`을 설정합니다.

:::code language="json" source="snippets/configuration/worker-service/appsettings.MSFT.json":::

## <a name="log-event-id"></a>로그 이벤트 ID

각 로그에서 ‘이벤트 식별자’를 지정할 수 있으며, <xref:Microsoft.Extensions.Logging.EventId>는 `Id` 및 선택적 `Name` 읽기 전용 속성을 포함하는 구조체입니다. 샘플 소스 코드는 `AppLogEvents` 클래스를 사용하여 이벤트 ID를 정의합니다.

```csharp
internal static class AppLogEvents
{
    internal const int Create = 1000;
    internal const int Read = 1001;
    internal const int Update = 1002;
    internal const int Delete = 1003;

    internal const int Details = 3000;
    internal const int Error = 3001;

    internal const int ReadNotFound = 4000;
    internal const int UpdateNotFound = 4001;

    // ...
}
```

이벤트 ID는 이벤트 집합을 연결합니다. 예를 들어 리포지토리에서 값 읽기와 관련된 모든 로그는 `1001`일 수 있습니다.

로깅 공급자는 이벤트 ID를 ID 필드에 기록하거나, 로그 메시지에 기록하거나, 전혀 기록하지 않을 수 있습니다. 디버그 공급자는 이벤트 ID를 표시하지 않습니다. 콘솔 공급자는 범주 뒤에 대괄호로 이벤트 ID를 표시합니다.

```console
info: Example.DefaultService.GetAsync[1001]
      Reading value for a1b2c3
warn: Example.DefaultService.GetAsync[4000]
      GetAsync(a1b2c3) not found
```

일부 로깅 공급자는 ID에 대한 필터링을 허용하는 필드에 이벤트 ID를 저장합니다.

## <a name="log-message-template"></a>로그 메시지 템플릿

각 로그 API는 메시지 템플릿을 사용합니다. 메시지 템플릿에는 인수가 제공되는 자리 표시자를 포함할 수 있습니다. 번호가 아닌 자리 표시자의 이름을 사용합니다. 값을 제공하는 데 사용되는 매개 변수를 결정하는 것은 자리 표시자의 이름이 아닌 순서입니다. 다음 코드에서는 매개 변수 이름이 메시지 템플릿의 순서와 일치하지 않습니다.

```csharp
string p1 = "param1";
string p2 = "param2";
_logger.LogInformation("Parameter values: {p2}, {p1}", p1, p2);
```

앞의 코드는 매개 변수 값을 순서대로 사용하여 로그 메시지를 만듭니다.

```text
Parameter values: param1, param2
```

해당 접근 방식을 통해 로깅 공급자는 [의미 체계 또는 구조적 로깅](https://github.com/NLog/NLog/wiki/How-to-use-structured-logging)를 구현할 수 있습니다. 인수 자체는 서식이 지정된 메시지 템플릿뿐만 아니라 로깅 시스템에 전달됩니다. 따라서 로깅 공급자는 매개 변수 값을 필드로 저장할 수 있습니다. 다음 로거 메서드를 살펴보세요.

```csharp
_logger.LogInformation("Getting item {Id} at {RunTime}", id, DateTime.Now);
```

Azure Table Storage에 로그할 경우를 예로 듭니다.

- 각 Azure Table 엔터티에는 `ID` 및 `RunTime` 속성이 있을 수 있습니다.
- 속성이 있는 테이블은 로그된 데이터의 쿼리를 쉽게 합니다. 예를 들어 문자 메시지의 시간 초과를 구문 분석하지 않고도 특정 `RunTime` 범위 내에 있는 모든 로그를 쿼리를 통해 찾을 수 있습니다.

## <a name="log-exceptions"></a>예외 로그

로거 메서드에는 예외 매개 변수를 사용하는 오버로드가 있습니다.

```csharp
public void Test(string id)
{
    try
    {
        if (id == "none")
        {
            throw new Exception("Default Id detected.");
        }
    }
    catch (Exception ex)
    {
        _logger.LogWarning(
            AppLogEvents.Error, ex,
            "Failed to process iteration: {Id}", id)
    }
}
```

예외 로깅은 공급자별로 다릅니다.

### <a name="default-log-level"></a>기본 로그 수준

기본 로그 수준을 설정하지 않으면 기본 로그 수준 값은 `Information`입니다.

예를 들어 다음 작업자 서비스 앱을 살펴보세요.

- .NET 작업자 템플릿을 사용하여 만들었습니다.
- *appsettings.json* 및 *appsettings.Development.json* 을 삭제하거나 이름을 변경했습니다.

이전 설정을 사용하여 개인정보처리방침이나 홈페이지로 이동하면 범주 이름에 `Microsoft`가 포함된 `Trace`, `Debug`및 `Information` 메시지가 많이 생성됩니다.

다음 코드에서는 구성에 기본 로그 수준이 설정되어 있지 않은 경우 기본 로그 수준을 설정합니다.

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging => logging.SetMinimumLevel(LogLevel.Warning));
}
```

### <a name="filter-function"></a>필터 함수

필터 함수는 구성 또는 코드를 통해 규칙이 할당되지 않은 모든 공급자와 범주에 대해 호출됩니다.

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddFilter((provider, category, logLevel) =>
                {
                    return provider.Contains("ConsoleLoggerProvider")
                        && (category.Contains("Example") || category.Contains("Microsoft"))
                        && logLevel >= LogLevel.Information;
                }));
}
```

앞의 코드는 범주에 `Example` 또는 `Microsoft`가 포함되어 있고 로그 수준이 `Information` 이상인 경우 콘솔 로그를 표시합니다.

## <a name="log-scopes"></a>로그 범위

 *범위* 는 논리적 작업 집합을 그룹화할 수 있습니다. 이 그룹화는 집합의 일부로 생성된 각 로그에 동일한 데이터를 연결하는 데 사용될 수 있습니다. 예를 들어 트랜잭션 처리의 일부로 생성되는 모든 로그에는 트랜잭션 ID가 포함될 수 있습니다.

범위:

- <xref:Microsoft.Extensions.Logging.ILogger.BeginScope%2A> 메서드에서 반환하는 <xref:System.IDisposable> 형식입니다.
- 삭제될 때까지 유지됩니다.

범위를 지원하는 공급자는 다음과 같습니다.

- `Console`
- [AzureAppServicesFile 및 AzureAppServicesBlob](xref:Microsoft.Extensions.Logging.AzureAppServices.BatchingLoggerOptions.IncludeScopes)

`using` 블록에 로거 호출을 래핑하여 범위를 사용합니다.

```csharp
public async Task<T> GetAsync<T>(string id)
{
    T result;

    using (_logger.BeginScope("using block message"))
    {
        _logger.LogInformation(
            AppLogEvents.Read, "Reading value for {Id}", id);

        var result = await _repository.GetAsync(id);
        if (result is null)
        {
            _logger.LogWarning(
                AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
        }
    }

    return result;
}
```

다음 JSON은 콘솔 공급자에 대해 범위를 사용하도록 설정합니다.

:::code language="json" source="snippets/configuration/worker-service/appsettings.IncludeScopes.json" highlight="9":::

다음은 콘솔 공급자에 대한 범위를 사용하도록 설정하는 코드입니다.

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging((_, logging) =>
                logging.ClearProviders()
                    .AddConsole(options => options.IncludeScopes = true));
}
```

## <a name="non-host-console-app"></a>비호스트 콘솔 앱

[제네릭 호스트](generic-host.md)를 사용하지 않는 앱의 로깅 코드는 [공급자 추가](logging-providers.md#built-in-logging-providers) 및 [로거 생성](#create-logs) 방식에 따라 달라집니다. 비 호스트 콘솔 앱에서는 `LoggerFactory`를 만드는 동안 공급자의 `Add{provider name}` 확장 메서드를 호출합니다.

```csharp
class Program
{
    static void Main(string[] args)
    {
        using var loggerFactory = LoggerFactory.Create(builder =>
        {
            builder
                .AddFilter("Microsoft", LogLevel.Warning)
                .AddFilter("System", LogLevel.Warning)
                .AddFilter("LoggingConsoleApp.Program", LogLevel.Debug)
                .AddConsole();
        });

        ILogger logger = loggerFactory.CreateLogger<Program>();
        logger.LogInformation("Example log message");
    }
}
```

`loggerFactory` 개체는 <xref:Microsoft.Extensions.Logging.ILogger> 인스턴스를 만드는 데 사용됩니다.

## <a name="create-logs-in-main"></a>Main에서 로그 만들기

다음 코드는 호스트를 빌드한 후 DI에서 `ILogger` 인스턴스를 가져와 `Main`에 로그합니다.

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;
using Microsoft.Extensions.Logging;

class Program
{
    static Task Main(string[] args)
    {
        IHost host = Host.CreateDefaultBuilder(args).Build();

        var logger = host.Services.GetRequiredService<ILogger<Program>>();
        logger.LogInformation("Host created.");

        return host.RunAsync();
    }
}
```

### <a name="no-asynchronous-logger-methods"></a>비동기 로거 메서드 미지원

로깅은 매우 빨라서 비동기 코드의 성능 비용을 들일 필요가 없습니다. 로깅 데이터 저장소가 느린 경우 직접 작성하지 마세요. 로그 메시지를 처음에 빠른 저장소에 작성한 다음, 나중에 느린 저장소로 이동하는 것이 좋습니다. 예를 들어 SQL Server에 로그하는 경우 `Log` 메서드는 동기식이므로 `Log` 메서드에서 직접 로그하지 마세요. 대신 동기적으로 로그 메시지를 메모리 내 큐에 추가하고 백그라운드 작업자가 큐에서 메시지를 풀하여 SQL Server에 대해 비동기 데이터 푸시 작업을 수행하도록 합니다.

## <a name="change-log-levels-in-a-running-app"></a>실행 중인 앱에서 로그 수준 변경

로깅 API는 앱이 실행되는 동안 로그 수준을 변경하는 시나리오를 포함하지 않습니다. 그러나 일부 구성 공급자는 구성을 다시 로드할 수 있으며 이는 로깅 구성에 대한 즉각적인 영향을 줍니다. 예를 들어 [파일 구성 공급자](configuration-providers.md#file-configuration-provider)는 기본적으로 로깅 구성을 다시 로드합니다. 앱이 실행되는 동안 코드에서 구성이 변경되면 앱 [IConfigurationRoot.Reload](xref:Microsoft.Extensions.Configuration.IConfigurationRoot.Reload%2A)를 호출하여 앱의 로깅 구성을 업데이트할 수 있습니다.

## <a name="nuget-packages"></a>NuGet 패키지

<xref:Microsoft.Extensions.Logging.ILogger%601> 및 <xref:Microsoft.Extensions.Logging.ILoggerFactory> 인터페이스와 구현은 .NET Core SDK에 포함되어 있습니다. 또한 다음 NuGet 패키지에서도 사용할 수 있습니다.

- 인터페이스는 [Microsoft.Extensions.Logging.Abstractions](https://www.nuget.org/packages/Microsoft.Extensions.Logging.Abstractions)에 있습니다.
- 기본 구현은 [Microsoft.Extensions.Logging](https://www.nuget.org/packages/microsoft.extensions.logging)에 있습니다.

## <a name="apply-log-filter-rules-in-code"></a>코드에서 로그 필터 규칙 적용

로그 필터 규칙을 설정하는 기본 방법은 [구성](configuration.md)을 사용하는 것입니다.

다음 예제는 코드에서 필터 규칙을 등록하는 방법을 보여줍니다.

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
               logging.AddFilter("System", LogLevel.Debug)
                  .AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)
                  .AddFilter<ConsoleLoggerProvider>("Microsoft", LogLevel.Trace));
}
```

`logging.AddFilter("System", LogLevel.Debug)`는 `System`범주 및 로그 수준`Debug`을 지정합니다. 특정 공급자를 구성하지 않았으므로 필터가 모든 공급자에 적용됩니다.

`AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)`은 다음을 지정합니다.

- `Debug` 로깅 공급자
- 로그 수준 `Information` 이상
- `"Microsoft"`로 시작하는 모든 범주

## <a name="see-also"></a>참고 항목

- [.NET의 로깅 공급자](logging-providers.md)
- [.NET에서 사용자 지정 로깅 공급자 구현](custom-logging-provider.md)
- [콘솔 로그 서식 지정](console-log-formatter.md)
- [.NET의 고성능 로깅](high-performance-logging.md)
- 로깅 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.
