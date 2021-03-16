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
# <a name="console-log-formatting"></a><span data-ttu-id="fa0b8-103">콘솔 로그 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fa0b8-103">Console log formatting</span></span>

<span data-ttu-id="fa0b8-104">.NET 5에서 `Microsoft.Extensions.Logging.Console` 네임스페이스의 콘솔 로그에 사용자 지정 서식에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-104">In .NET 5, support for custom formatting was added to console logs in the `Microsoft.Extensions.Logging.Console` namespace.</span></span> <span data-ttu-id="fa0b8-105">세 가지 서식 옵션 [`Simple`](#simple), [`Systemd`](#systemd) 및 [`Json`](#json)이 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-105">There are three predefined formatting options available: [`Simple`](#simple), [`Systemd`](#systemd), and [`Json`](#json).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa0b8-106">이전에는 <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> 열거형에서 사람이 읽을 수 있는 로그 형식(`Default`) 또는 한 줄 로그 형식(`Systemd`라고도 함)에서 원하는 대로 선택할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-106">Previously, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat> enum allowed for selecting the desired log format, either human readable which was the `Default`, or single line which is also known as `Systemd`.</span></span> <span data-ttu-id="fa0b8-107">그러나 이러한 로그 형식은 사용자 지정이 **불가능** 했으며 이제는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-107">However, these were **not** customizable, and are now deprecated.</span></span>

<span data-ttu-id="fa0b8-108">이 문서에서는 콘솔 로그 포맷터에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-108">In this article, you will learn about console log formatters.</span></span> <span data-ttu-id="fa0b8-109">샘플 소스 코드에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-109">The sample source code demonstrates how to:</span></span>

- <span data-ttu-id="fa0b8-110">새 포맷터를 등록</span><span class="sxs-lookup"><span data-stu-id="fa0b8-110">Register a new formatter</span></span>
- <span data-ttu-id="fa0b8-111">사용할 등록된 포맷터를 선택</span><span class="sxs-lookup"><span data-stu-id="fa0b8-111">Select a registered formatter to use</span></span>
  - <span data-ttu-id="fa0b8-112">코드 또는 [구성](configuration.md)을 통해</span><span class="sxs-lookup"><span data-stu-id="fa0b8-112">Either through code, or [configuration](configuration.md)</span></span>
- <span data-ttu-id="fa0b8-113">사용자 지정 포맷터를 구현</span><span class="sxs-lookup"><span data-stu-id="fa0b8-113">Implement a custom formatter</span></span>
  - <span data-ttu-id="fa0b8-114"><xref:Microsoft.Extensions.Options.IOptionsMonitor%601>를 통해 구성을 업데이트</span><span class="sxs-lookup"><span data-stu-id="fa0b8-114">Update configuration via <xref:Microsoft.Extensions.Options.IOptionsMonitor%601></span></span>
  - <span data-ttu-id="fa0b8-115">사용자 지정 색 서식을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fa0b8-115">Enable custom color formatting</span></span>

## <a name="register-formatter"></a><span data-ttu-id="fa0b8-116">포맷터 등록</span><span class="sxs-lookup"><span data-stu-id="fa0b8-116">Register formatter</span></span>

<span data-ttu-id="fa0b8-117">[`Console` 로깅 공급자](logging-providers.md#console)는 미리 정의된 포맷터를 여러 개 포함하고 사용자 지정 포맷터를 작성하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-117">The [`Console` logging provider](logging-providers.md#console) has several predefined formatters, and exposes the ability to author your own custom formatter.</span></span> <span data-ttu-id="fa0b8-118">사용 가능한 포맷터를 등록하려면 해당 `Add{Type}Console` 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-118">To register any of the available formatters, use the corresponding `Add{Type}Console` extension method:</span></span>

| <span data-ttu-id="fa0b8-119">사용 가능한 형식</span><span class="sxs-lookup"><span data-stu-id="fa0b8-119">Available types</span></span> | <span data-ttu-id="fa0b8-120">형식을 등록하는 메서드</span><span class="sxs-lookup"><span data-stu-id="fa0b8-120">Method to register type</span></span> |
|--|--|
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddJsonConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSimpleConsole%2A?displayProperty=nameWithType> |
| <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> | <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddSystemdConsole%2A?displayProperty=nameWithType> |

### <a name="simple"></a><span data-ttu-id="fa0b8-121">단순</span><span class="sxs-lookup"><span data-stu-id="fa0b8-121">Simple</span></span>

<span data-ttu-id="fa0b8-122">`Simple` 콘솔 포맷터를 사용하려면 `AddSimpleConsole`을 사용하여 포맷터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-122">To use the `Simple` console formatter, register it with `AddSimpleConsole`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-simple/Program.cs" highlight="11-16":::

<span data-ttu-id="fa0b8-123">위의 샘플 소스 코드에서는 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> 포맷터가 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-123">In the preceding sample source code, the <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType> formatter was registered.</span></span> <span data-ttu-id="fa0b8-124">이 포맷터는 각 로그 메시지에 시간 및 로그 수준과 같은 정보를 래핑할 수 있는 기능을 제공하지만, ANSI 색 포함 및 메시지 들여쓰기도 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-124">It provides logs with the ability to not only wrap information such as time and log level in each log message, but also allows for ANSI color embedding and indentation of messages.</span></span>

### <a name="systemd"></a><span data-ttu-id="fa0b8-125">Systemd</span><span class="sxs-lookup"><span data-stu-id="fa0b8-125">Systemd</span></span>

<span data-ttu-id="fa0b8-126"><xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> 콘솔 로거:</span><span class="sxs-lookup"><span data-stu-id="fa0b8-126">The <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType> console logger:</span></span>

- <span data-ttu-id="fa0b8-127">‘Syslog’ 로그 수준 형식 및 심각도를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-127">Uses the "Syslog" log level format and severities</span></span>
- <span data-ttu-id="fa0b8-128">색을 사용한 메시지 서식 지정을 제공하지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-128">Does **not** format messages with colors</span></span>
- <span data-ttu-id="fa0b8-129">메시지를 항상 한 줄로 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-129">Always logs messages in a single line</span></span>

<span data-ttu-id="fa0b8-130">`Systemd` 콘솔 로깅을 흔히 사용하는 컨테이너에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-130">This is commonly useful for containers, which often make use of `Systemd` console logging.</span></span> <span data-ttu-id="fa0b8-131">.NET 5에서는 `Simple` 콘솔 로거를 사용하여 한 줄로 로깅하는 압축 버전을 사용할 수도 있으며, 이전 샘플에 표시된 대로 색을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-131">With .NET 5, the `Simple` console logger also enables a compact version that logs in a single line, and also allows for disabling colors as shown in an earlier sample.</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-systemd/Program.cs" highlight="11-15":::

### <a name="json"></a><span data-ttu-id="fa0b8-132">Json</span><span class="sxs-lookup"><span data-stu-id="fa0b8-132">Json</span></span>

<span data-ttu-id="fa0b8-133">JSON 형식으로 로그를 작성하려면 `Json` 콘솔 포맷터가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-133">To write logs in a JSON format, the `Json` console formatter is used.</span></span> <span data-ttu-id="fa0b8-134">샘플 소스 코드에서는 ASP.NET Core 앱에서 이 포맷터를 등록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-134">The sample source code shows how an ASP.NET Core app might register it.</span></span> <span data-ttu-id="fa0b8-135">`webapp` 템플릿을 사용하여 [dotnet new](../tools/dotnet-new.md) 명령으로 새 ASP.NET Core 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-135">Using the `webapp` template, create a new ASP.NET Core app with the [dotnet new](../tools/dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new webapp -o Console.ExampleFormatters.Json
```

<span data-ttu-id="fa0b8-136">앱이 실행되는 동안 템플릿 코드를 사용하여 아래 기본 로그 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-136">When running the app, using the template code, you get the default log format below:</span></span>

```
info: Microsoft.Hosting.Lifetime[0]
      Now listening on: https://localhost:5001
```

<span data-ttu-id="fa0b8-137">기본적으로 `Simple` 콘솔 로그 포맷터는 기본 구성으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-137">By default, the `Simple` console log formatter is selected with default configuration.</span></span> <span data-ttu-id="fa0b8-138">*Program.cs* 에서 `AddJsonConsole`을 호출하여 이를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-138">You change this by calling `AddJsonConsole` in the *Program.cs*:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-json/Program.cs" highlight="17-26":::

<span data-ttu-id="fa0b8-139">위의 변경 내용으로 앱을 다시 실행합니다. 이제 로그 메시지는 JSON 형식으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-139">Run the app again, with the above change, the log message is now formatted as JSON:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/example-output.json":::

> [!TIP]
> <span data-ttu-id="fa0b8-140">`Json` 콘솔 포맷터는 기본적으로 각 메시지를 한 줄에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-140">The `Json` console formatter, by default, logs each message in a single line.</span></span> <span data-ttu-id="fa0b8-141">포맷터를 구성하는 동안 보다 읽기 쉽게 만들려면 <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType>를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-141">In order to make it more readable while configuring the formatter, set <xref:System.Text.Json.JsonWriterOptions.Indented?displayProperty=nameWithType> to `true`.</span></span>

## <a name="set-formatter-with-configuration"></a><span data-ttu-id="fa0b8-142">구성을 사용하여 포맷터 설정</span><span class="sxs-lookup"><span data-stu-id="fa0b8-142">Set formatter with configuration</span></span>

<span data-ttu-id="fa0b8-143">이전 샘플에서는 프로그래밍 방식으로 포맷터를 등록하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-143">The previous samples have shown how to register a formatter programmatically.</span></span> <span data-ttu-id="fa0b8-144">[구성](configuration.md)을 사용하여 이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-144">Alternatively, this can be done with [configuration](configuration.md).</span></span> <span data-ttu-id="fa0b8-145">이전 웹 애플리케이션 샘플 소스 코드를 생각해 보세요. *Program.cs* 파일에서 `ConfigureLogging`을 호출하는 대신 *appsettings.json* 파일을 업데이트하면 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-145">Consider the previous web application sample source code, if you update the *appsettings.json* file rather than calling `ConfigureLogging` in the *Program.cs* file, you could get the same outcome.</span></span> <span data-ttu-id="fa0b8-146">업데이트된 `appsettings.json` 파일은 다음과 같이 포맷터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-146">The updated `appsettings.json` file would configure the formatter as follows:</span></span>

:::code language="json" source="snippets/logging/console-formatter-json/appsettings.json" highlight="14-23":::

<span data-ttu-id="fa0b8-147">설정해야 하는 두 가지 키 값은 `"FormatterName"` 및 `"FormatterOptions"`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-147">The two key values that need to be set are `"FormatterName"` and `"FormatterOptions"`.</span></span> <span data-ttu-id="fa0b8-148">`"FormatterName"`에 대한 값이 설정된 포맷터가 이미 등록되어 있으면 해당 포맷터가 선택되고 `"FormatterOptions"` 노드 내에서 키로 제공되는 경우에 한해 해당 속성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-148">If a formatter with the value set for `"FormatterName"` is already registered, that formatter is selected, and its properties can be configured as long as they are provided as a key inside the `"FormatterOptions"` node.</span></span> <span data-ttu-id="fa0b8-149">미리 정의된 포맷터 이름은 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>에 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-149">The predefined formatter names are reserved under <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames>:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Json?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Simple?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterNames.Systemd?displayProperty=nameWithType>

## <a name="implement-a-custom-formatter"></a><span data-ttu-id="fa0b8-150">사용자 지정 포맷터를 구현</span><span class="sxs-lookup"><span data-stu-id="fa0b8-150">Implement a custom formatter</span></span>

<span data-ttu-id="fa0b8-151">사용자 지정 포맷터를 구현하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-151">To implement a custom formatter, you need to:</span></span>

- <span data-ttu-id="fa0b8-152"><xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>의 하위 클래스를 만듭니다. 이는 사용자 지정 포맷터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-152">Create a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatter>, this represents your custom formatter</span></span>
- <span data-ttu-id="fa0b8-153">다음을 사용하여 사용자 지정 포맷터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-153">Register your custom formatter with</span></span>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsole%2A?displayProperty=nameWithType>
  - <xref:Microsoft.Extensions.Logging.ConsoleLoggerExtensions.AddConsoleFormatter%60%602(Microsoft.Extensions.Logging.ILoggingBuilder,System.Action{%60%601})?displayProperty=nameWithType>

<span data-ttu-id="fa0b8-154">이를 처리하는 확장 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-154">Create an extension method to handle this for you:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/ConsoleLoggerExtensions.cs" highlight="11-12":::

<span data-ttu-id="fa0b8-155">`CustomOptions`는 아래와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-155">The `CustomOptions` are defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomOptions.cs":::

<span data-ttu-id="fa0b8-156">위의 코드에서 옵션은 <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-156">In the preceding code, the options are a subclass of <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>.</span></span>

<span data-ttu-id="fa0b8-157">`AddConsoleFormatter` API:</span><span class="sxs-lookup"><span data-stu-id="fa0b8-157">The `AddConsoleFormatter` API:</span></span>

- <span data-ttu-id="fa0b8-158">`ConsoleFormatter`의 하위 클래스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-158">Registers a subclass of `ConsoleFormatter`</span></span>
- <span data-ttu-id="fa0b8-159">다음과 같이 구성을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-159">Handles configuration:</span></span>
  - <span data-ttu-id="fa0b8-160">변경 토큰을 사용하여 [옵션 패턴](options.md) 및 [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) 인터페이스를 기반으로 업데이트를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-160">Uses a change token to synchronize updates, based on the [options pattern](options.md), and the [IOptionsMonitor](xref:Microsoft.Extensions.Options.IOptionsMonitor%601) interface</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/Program.cs" highlight="11-12":::

<span data-ttu-id="fa0b8-161">`ConsoleFormatter`의 `CustomerFormatter` 하위 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-161">Define a `CustomerFormatter` subclass of `ConsoleFormatter`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomFormatter.cs" highlight="24-45":::

<span data-ttu-id="fa0b8-162">위의 `CustomFormatter.Write<TState>` API는 각 로그 메시지 주위에 래핑되는 텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-162">The preceding `CustomFormatter.Write<TState>` API dictates what text gets wrapped around each log message.</span></span> <span data-ttu-id="fa0b8-163">표준 `ConsoleFormatter`에서는 적어도 로그의 범위, 타임스탬프 및 심각도 수준을 래핑할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-163">A standard `ConsoleFormatter` should be able to wrap around scopes, time stamps, and severity level of logs at a minimum.</span></span> <span data-ttu-id="fa0b8-164">또한 로그 메시지의 ANSI 색을 인코딩하고 원하는 들여쓰기도 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-164">Additionally, you can encode ANSI colors in the log messages, and provide desired indentations as well.</span></span> <span data-ttu-id="fa0b8-165">`CustomFormatter.Write<TState>`의 구현에는 이러한 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-165">The implementation of the `CustomFormatter.Write<TState>` lacks these capabilities.</span></span>

<span data-ttu-id="fa0b8-166">서식을 추가로 사용자 지정하는 방법에 대한 자세한 내용은 `Microsoft.Extensions.Logging.Console` 네임스페이스의 기존 구현을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-166">For inspiration on further customizing formatting, see the existing implementations in the `Microsoft.Extensions.Logging.Console` namespace:</span></span>

- <span data-ttu-id="fa0b8-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span><span class="sxs-lookup"><span data-stu-id="fa0b8-167">[SimpleConsoleFormatter](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SimpleConsoleFormatter.cs).</span></span>
- [<span data-ttu-id="fa0b8-168">SystemdConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="fa0b8-168">SystemdConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/SystemdConsoleFormatter.cs)
- [<span data-ttu-id="fa0b8-169">JsonConsoleFormatter</span><span class="sxs-lookup"><span data-stu-id="fa0b8-169">JsonConsoleFormatter</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/Microsoft.Extensions.Logging.Console/src/JsonConsoleFormatter.cs)

## <a name="implement-custom-color-formatting"></a><span data-ttu-id="fa0b8-170">사용자 지정 색 서식 구현</span><span class="sxs-lookup"><span data-stu-id="fa0b8-170">Implement custom color formatting</span></span>

<span data-ttu-id="fa0b8-171">사용자 지정 로깅 포맷터에서 색 기능을 제대로 사용하려면 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>를 확장할 수 있습니다. 로그에서 색을 사용하도록 설정하는 데 유용할 수 있는 <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> 속성이 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-171">In order to properly enable color capabilities in your custom logging formatter, you can extend the <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> as it has a <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions.ColorBehavior?displayProperty=nameWithType> property that can be useful for enabling colors in logs.</span></span>

<span data-ttu-id="fa0b8-172">`SimpleConsoleFormatterOptions`에서 파생되는 `CustomColorOptions`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-172">Create a `CustomColorOptions` that derives from `SimpleConsoleFormatterOptions`:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorOptions.cs" highlight="5":::

<span data-ttu-id="fa0b8-173">다음으로, `TextWriterExtensions` 클래스에서 서식 지정된 로그 메시지 내에 ANSI 코딩된 색을 편리하게 포함할 수 있도록 하는 몇몇 확장 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-173">Next, write some extension methods in a `TextWriterExtensions` class that allow for conveniently embedding ANSI coded colors within formatted log messages:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/TextWriterExtensions.cs":::

<span data-ttu-id="fa0b8-174">사용자 지정 색 적용을 처리하는 사용자 지정 색 포맷터는 다음과 같이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-174">A custom color formatter that handles applying custom colors could be defined as follows:</span></span>

:::code language="csharp" source="snippets/logging/console-formatter-custom/CustomColorFormatter.cs" highlight="15-18,52-65":::

<span data-ttu-id="fa0b8-175">애플리케이션을 실행할 때 `FormatterOptions.ColorBehavior`가 `Enabled`인 경우 로그에서 `CustomPrefix` 메시지가 녹색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-175">When you run the application, the logs will show the `CustomPrefix` message in the color green when `FormatterOptions.ColorBehavior` is `Enabled`.</span></span>

> [!NOTE]
> <span data-ttu-id="fa0b8-176"><xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior>가 `Disabled`이면 로그 메시지는 로그 메시지에 포함된 ANSI 색 코드를 해석하지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-176">When <xref:Microsoft.Extensions.Logging.Console.LoggerColorBehavior> is `Disabled`, log messages do _not_ interpret embedded ANSI color codes within log messages.</span></span> <span data-ttu-id="fa0b8-177">대신 원시 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-177">Instead, they output the raw message.</span></span> <span data-ttu-id="fa0b8-178">다음 예를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-178">For example, consider the following:</span></span>
>
> ```csharp
> logger.LogInformation("Random log \x1B[42mwith green background\x1B[49m message");
> ```
>
> <span data-ttu-id="fa0b8-179">축자 문자열이 출력되고 색이 지정되지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-179">This would output the verbatim string, and it is _not_ colorized.</span></span>
>
> ```output
> Random log \x1B[42mwith green background\x1B[49m message
> ```

## <a name="see-also"></a><span data-ttu-id="fa0b8-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa0b8-180">See also</span></span>

- [<span data-ttu-id="fa0b8-181">.NET의 로깅</span><span class="sxs-lookup"><span data-stu-id="fa0b8-181">Logging in .NET</span></span>](logging.md)
- [<span data-ttu-id="fa0b8-182">.NET에서 사용자 지정 로깅 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="fa0b8-182">Implement a custom logging provider in .NET</span></span>](custom-logging-provider.md)
- [<span data-ttu-id="fa0b8-183">.NET의 고성능 로깅</span><span class="sxs-lookup"><span data-stu-id="fa0b8-183">High-performance logging in .NET</span></span>](high-performance-logging.md)
