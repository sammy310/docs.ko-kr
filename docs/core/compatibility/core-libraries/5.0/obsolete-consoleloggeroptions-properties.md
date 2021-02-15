---
title: '호환성이 손상되는 변경: ConsoleLoggerOptions에서 사용되지 않는 속성'
description: ConsoleLoggerFormat 형식 및 ConsoleLoggerOptions의 일부 속성이 이제 사용되지 않는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: bd039dfa84ae3399d7fb36f992010a9a3c9f6ddf
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99548385"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a>ConsoleLoggerOptions에서 사용되지 않는 속성

<xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> 형식과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>의 일부 속성은 더 이상 사용되지 않습니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5.0부터 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> 형식과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>의 여러 속성은 사용되지 않습니다. 사용되지 않는 속성은 다음과 같습니다.

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

새 포맷터가 도입됨에 따라 이제 개별 포맷터에서 해당 속성을 사용할 수 있습니다.

## <a name="reason-for-change"></a>변경 이유

<xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> 속성은 사용자 지정 포맷터를 나타낼 수 없는 열거형 형식입니다.

나머지 속성은 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>에서 설정되어 콘솔 로그의 기본 제공 형식에 모두 적용되었습니다. 그러나 새 포맷터 API가 도입되었으므로 포맷터별 옵션에 서식을 포함하는 것이 더 적합합니다. 이렇게 변경하면 로거와 로커 포맷터를 더 명확하게 구분할 수 있습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> 속성 대신 새로운 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> 속성을 사용합니다. 예를 들면 다음과 같습니다.

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName>과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> 간에는 몇 가지 차이점이 있습니다.

  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>에는 `Default`와 `Systemd`의 두 가지 옵션만 사용할 수 있습니다.
  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName>은 대/소문자를 구분하지 않으며 임의 문자열일 수 있습니다. 예약된 기본 제공 이름은 `Simple`, `Systemd`, `Json`(.NET 5.0 이상)입니다.
  - `"Format": "Systemd"`은 `"FormatterName": "Systemd"`에 매핑됩니다.
  - `"Format": "Default"`은 `"FormatterName": "Simple"`에 매핑됩니다.

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> 속성의 경우 새로운 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> 또는 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> 형식의 해당 속성을 대신 사용합니다. 예를 들어 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>에 해당하는 설정은 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>입니다.

  이전 코드:

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

  새로운 코드:

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.ColorBehavior = LoggerColorBehavior.Disabled;
  });
  ```

다음 두 가지 JSON 코드 조각에서는 구성 파일의 변경 내용을 보여 줍니다. 이전 구성 파일:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

새 구성 파일:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET

### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
