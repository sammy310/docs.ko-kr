---
title: '호환성이 손상되는 변경: ConsoleLoggerOptions에서 사용되지 않는 속성'
description: ConsoleLoggerFormat 형식 및 ConsoleLoggerOptions의 일부 속성이 이제 사용되지 않는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: c6ee294f90e304cebd517bd0139c58a6c7a41e0c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257312"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="5926f-103">ConsoleLoggerOptions에서 사용되지 않는 속성</span><span class="sxs-lookup"><span data-stu-id="5926f-103">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="5926f-104"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> 형식과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>의 일부 속성은 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-104">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

## <a name="change-description"></a><span data-ttu-id="5926f-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="5926f-105">Change description</span></span>

<span data-ttu-id="5926f-106">.NET 5부터 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> 형식과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>의 여러 속성은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-106">Starting in .NET 5, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="5926f-107">사용되지 않는 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-107">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="5926f-108">새 포맷터가 도입됨에 따라 이제 개별 포맷터에서 해당 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-108">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5926f-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="5926f-109">Reason for change</span></span>

<span data-ttu-id="5926f-110"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> 속성은 사용자 지정 포맷터를 나타낼 수 없는 열거형 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-110">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="5926f-111">나머지 속성은 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions>에서 설정되어 콘솔 로그의 기본 제공 형식에 모두 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-111">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="5926f-112">그러나 새 포맷터 API가 도입되었으므로 포맷터별 옵션에 서식을 포함하는 것이 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-112">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="5926f-113">이렇게 변경하면 로거와 로커 포맷터를 더 명확하게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-113">This change provides better separation between the logger and logger formatters.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5926f-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="5926f-114">Version introduced</span></span>

<span data-ttu-id="5926f-115">5.0</span><span class="sxs-lookup"><span data-stu-id="5926f-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5926f-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="5926f-116">Recommended action</span></span>

- <span data-ttu-id="5926f-117"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> 속성 대신 새로운 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-117">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5926f-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-118">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="5926f-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName>과 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> 간에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-119">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="5926f-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>에는 `Default`와 `Systemd`의 두 가지 옵션만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="5926f-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName>은 대/소문자를 구분하지 않으며 임의 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="5926f-122">예약된 기본 제공 이름은 `Simple`, `Systemd`, `Json`(.NET 5 이상)입니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-122">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5 and later).</span></span>
  - <span data-ttu-id="5926f-123">`"Format": "Systemd"`은 `"FormatterName": "Systemd"`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-123">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="5926f-124">`"Format": "Default"`은 `"FormatterName": "Simple"`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-124">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="5926f-125"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> 속성의 경우 새로운 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> 또는 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> 형식의 해당 속성을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-125">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="5926f-126">예를 들어 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>에 해당하는 설정은 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-126">For example, the corresponding setting for <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType> is <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType>.</span></span>

  <span data-ttu-id="5926f-127">이전 코드:</span><span class="sxs-lookup"><span data-stu-id="5926f-127">Previous code:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

  <span data-ttu-id="5926f-128">새로운 코드:</span><span class="sxs-lookup"><span data-stu-id="5926f-128">New code:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.ColorBehavior = LoggerColorBehavior.Disabled;
  });
  ```

<span data-ttu-id="5926f-129">다음 두 가지 JSON 코드 조각에서는 구성 파일의 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5926f-129">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="5926f-130">이전 구성 파일:</span><span class="sxs-lookup"><span data-stu-id="5926f-130">Old configuration file:</span></span>

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

<span data-ttu-id="5926f-131">새 구성 파일:</span><span class="sxs-lookup"><span data-stu-id="5926f-131">New configuration file:</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="5926f-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5926f-132">Affected APIs</span></span>

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
