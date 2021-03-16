---
title: 콘솔 로그 서식 지정
description: 사용 가능한 콘솔 로그 서식을 사용하거나 .NET 애플리케이션에 대한 사용자 지정 로그 서식을 구현하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 12/17/2020
ms.openlocfilehash: 0ec8fc2018febe4273aa646d1682be197933f925
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "102402116"
---
# <a name="console-log-formatting"></a>콘솔 로그 서식 지정

.NET 5에서 `Microsoft.Extensions.Logging.Console` 네임스페이스의 콘솔 로그에 사용자 지정 서식에 대한 지원이 추가되었습니다. 세 가지 서식 옵션 [`Simple`](#simple), [`Systemd`](#systemd) 및 [`Json`](#json)이 미리 정의되어 있습니다.

> [!IMPORTANT]
> 이전에는 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> 열거형에서 사람이 읽을 수 있는 로그 형식(`Default`) 또는 한 줄 로그 형식(`Systemd`라고도 함)에서 원하는 대로 선택할 수 있었습니다. 그러나 이러한 로그 형식은 사용자 지정이 **불가능** 했으며 이제는 사용되지 않습니다.

이 문서에서는 콘솔 로그 포맷터에 대해 알아봅니다. 샘플 소스 코드에서는 다음 작업을 수행하는 방법을 보여 줍니다.

- 새 포맷터를 등록
- 사용할 등록된 포맷터를 선택
  - 코드 또는 [구성](configuration.md)을 통해
- 사용자 지정 포맷터를 구현
  - <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>를 통해 구성을 업데이트
  - 사용자 지정 색 서식을 사용하도록 설정

## <a name="register-formatter"></a>포맷터 등록

[`Console` 로깅 공급자](logging-providers.md#console)는 미리 정의된 포맷터를 여러 개 포함하고 사용자 지정 포맷터를 작성하는 기능을 제공합니다. 사용 가능한 포맷터를 등록하려면 해당 `Add{Type}Console` 확장 메서드를 사용합니다.

| 사용 가능한 형식 | 형식을 등록하는 메서드 |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a>단순

`Simple` 콘솔 포맷터를 사용하려면 `AddSimpleConsole`을 사용하여 포맷터를 등록합니다.

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

위의 샘플 소스 코드에서는 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> 포맷터가 등록되었습니다. 이 포맷터는 각 로그 메시지에 시간 및 로그 수준과 같은 정보를 래핑할 수 있는 기능을 제공하지만, ANSI 색 포함 및 메시지 들여쓰기도 허용합니다.

### <a name="systemd"></a>Systemd

<xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> 콘솔 로거:

- ‘Syslog’ 로그 수준 형식 및 심각도를 사용합니다.
- 색을 사용한 메시지 서식 지정을 제공하지 **않습니다**.
- 메시지를 항상 한 줄로 기록합니다.

`Systemd` 콘솔 로깅을 흔히 사용하는 컨테이너에 유용합니다. .NET 5에서는 `Simple` 콘솔 로거를 사용하여 한 줄로 로깅하는 압축 버전을 사용할 수도 있으며, 이전 샘플에 표시된 대로 색을 사용하지 않도록 설정할 수도 있습니다.

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a>Json

JSON 형식으로 로그를 작성하려면 `Json` 콘솔 포맷터가 사용됩니다. 샘플 소스 코드에서는 ASP.NET Core 앱에서 이 포맷터를 등록하는 방법을 보여 줍니다. `webapp` 템플릿을 사용하여 [dotnet new](../tools/dotnet-new.md) 명령으로 새 ASP.NET Core 앱을 만듭니다.

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

앱이 실행되는 동안 템플릿 코드를 사용하여 아래 기본 로그 형식을 가져옵니다.

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

기본적으로 `Simple` 콘솔 로그 포맷터는 기본 구성으로 선택됩니다. *Program.cs* 에서 `AddJsonConsole`을 호출하여 이를 변경합니다.

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

위의 변경 내용으로 앱을 다시 실행합니다. 이제 로그 메시지는 JSON 형식으로 기록됩니다.

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> `Json` 콘솔 포맷터는 기본적으로 각 메시지를 한 줄에 기록합니다. 포맷터를 구성하는 동안 보다 읽기 쉽게 만들려면 <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType>를 `true`로 설정합니다.

## <a name="set-formatter-with-configuration"></a>구성을 사용하여 포맷터 설정

이전 샘플에서는 프로그래밍 방식으로 포맷터를 등록하는 방법을 보여 주었습니다. [구성](configuration.md)을 사용하여 이 작업을 수행할 수도 있습니다. 이전 웹 애플리케이션 샘플 소스 코드를 생각해 보세요. *Program.cs* 파일에서 `ConfigureLogging`을 호출하는 대신 *appsettings.json* 파일을 업데이트하면 동일한 결과를 얻을 수 있습니다. 업데이트된 `appsettings.json` 파일은 다음과 같이 포맷터를 구성합니다.

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

설정해야 하는 두 가지 키 값은 `"FormatterName"` 및 `"FormatterOptions"`입니다. `"FormatterName"`에 대한 값이 설정된 포맷터가 이미 등록되어 있으면 해당 포맷터가 선택되고 `"FormatterOptions"` 노드 내에서 키로 제공되는 경우에 한해 해당 속성을 구성할 수 있습니다. 미리 정의된 포맷터 이름은 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>에 예약됩니다.

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a>사용자 지정 포맷터를 구현

사용자 지정 포맷터를 구현하려면 다음 작업을 수행해야 합니다.

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>의 하위 클래스를 만듭니다. 이는 사용자 지정 포맷터를 나타냅니다.
- 다음을 사용하여 사용자 지정 포맷터를 등록합니다.
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

이를 처리하는 확장 메서드를 만듭니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

`CustomOptions`는 아래와 같이 정의됩니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

위의 코드에서 옵션은 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>의 하위 클래스입니다.

`AddConsoleFormatter` API:

- `ConsoleFormatter`의 하위 클래스를 등록합니다.
- 다음과 같이 구성을 처리합니다.
  - 변경 토큰을 사용하여 [옵션 패턴](options.md) 및 [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) 인터페이스를 기반으로 업데이트를 동기화합니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

`ConsoleFormatter`의 `CustomerFormatter` 하위 클래스를 정의합니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

위의 `CustomFormatter.Write<TState>` API는 각 로그 메시지 주위에 래핑되는 텍스트를 지정합니다. 표준 `ConsoleFormatter`에서는 적어도 로그의 범위, 타임스탬프 및 심각도 수준을 래핑할 수 있어야 합니다. 또한 로그 메시지의 ANSI 색을 인코딩하고 원하는 들여쓰기도 제공할 수 있습니다. `CustomFormatter.Write<TState>`의 구현에는 이러한 기능이 없습니다.

서식을 추가로 사용자 지정하는 방법에 대한 자세한 내용은 `Microsoft.Extensions.Logging.Console` 네임스페이스의 기존 구현을 참조하세요.

- [SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).
- [SystemdConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [JsonConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a>사용자 지정 색 서식 구현

사용자 지정 로깅 포맷터에서 색 기능을 제대로 사용하려면 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>를 확장할 수 있습니다. 로그에서 색을 사용하도록 설정하는 데 유용할 수 있는 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> 속성이 있기 때문입니다.

`SimpleConsoleFormatterOptions`에서 파생되는 `CustomColorOptions`를 만듭니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

다음으로, `TextWriterExtensions` 클래스에서 서식 지정된 로그 메시지 내에 ANSI 코딩된 색을 편리하게 포함할 수 있도록 하는 몇몇 확장 메서드를 작성합니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

사용자 지정 색 적용을 처리하는 사용자 지정 색 포맷터는 다음과 같이 정의할 수 있습니다.

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

애플리케이션을 실행할 때 `FormatterOptions.ColorBehavior`가 `Enabled`인 경우 로그에서 `CustomPrefix` 메시지가 녹색으로 표시됩니다.

> [!NOTE]
> <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior>가 `Disabled`이면 로그 메시지는 로그 메시지에 포함된 ANSI 색 코드를 해석하지 ‘않습니다’. 대신 원시 메시지를 출력합니다. 다음 예를 살펴보십시오.
>
> ```csharp
> logger.LogInformation("Random log \x1B[42mwith green background\x1B[49m message");
> ```
>
> 축자 문자열이 출력되고 색이 지정되지 ‘않습니다’.
>
> ```output
> Random log \x1B[42mwith green background\x1B[49m message
> ```

## <a name="see-also"></a>참고 항목

- [.NET의 로깅](logging.md)
- [.NET에서 사용자 지정 로깅 공급자 구현](custom-logging-provider.md)
- [.NET의 고성능 로깅](high-performance-logging.md)
