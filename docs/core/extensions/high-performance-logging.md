---
title: .NET의 고성능 로깅
author: IEvangelist
description: LoggerMessage를 사용하여 고성능 로깅 시나리오에 적은 개체 할당을 필요로 하는 캐시 가능한 대리자를 만드는 방법을 알아봅니다.
ms.author: dapine
ms.date: 01/04/2021
ms.openlocfilehash: 0031ff7a9f70cb0cf724fdf6dfa4fbe0a44af7c1
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "102402134"
---
# <a name="high-performance-logging-in-net"></a><span data-ttu-id="96272-103">.NET의 고성능 로깅</span><span class="sxs-lookup"><span data-stu-id="96272-103">High-performance logging in .NET</span></span>

<span data-ttu-id="96272-104"><xref:Microsoft.Extensions.Logging.LoggerMessage> 클래스는 <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> 및 <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>와 같은 [로거 확장 메서드](xref:Microsoft.Extensions.Logging.LoggerExtensions)에 비해 적은 개체 할당 및 감소된 계산 오버헤드를 필요로 하는 캐시 가능한 대리자를 만드는 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-104">The <xref:Microsoft.Extensions.Logging.LoggerMessage> class exposes functionality to create cacheable delegates that require fewer object allocations and reduced computational overhead compared to [logger extension methods](xref:Microsoft.Extensions.Logging.LoggerExtensions), such as <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> and <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>.</span></span> <span data-ttu-id="96272-105">고성능 로깅 시나리오의 경우 <xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-105">For high-performance logging scenarios, use the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

<span data-ttu-id="96272-106"><xref:Microsoft.Extensions.Logging.LoggerMessage>는 로거 확장 메서드에 비해 다음과 같은 성능 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-106"><xref:Microsoft.Extensions.Logging.LoggerMessage> provides the following performance advantages over Logger extension methods:</span></span>

- <span data-ttu-id="96272-107">로거 확장 메서드는 `object`에 대한 `int`와 같은 "boxing"(변환) 값 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-107">Logger extension methods require "boxing" (converting) value types, such as `int`, into `object`.</span></span> <span data-ttu-id="96272-108"><xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴은 정적 <xref:System.Action> 필드 및 강력한 형식의 매개 변수가 있는 확장 메서드를 사용하여 boxing을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-108">The <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern avoids boxing by using static <xref:System.Action> fields and extension methods with strongly-typed parameters.</span></span>
- <span data-ttu-id="96272-109">로거 확장 메서드는 로그 메시지가 기록될 때마다 메시지 템플릿(명명된 형식 문자열)을 구문 분석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-109">Logger extension methods must parse the message template (named format string) every time a log message is written.</span></span> <span data-ttu-id="96272-110"><xref:Microsoft.Extensions.Logging.LoggerMessage>는 메시지가 정의될 때 템플릿 구문 분석이 한번만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-110"><xref:Microsoft.Extensions.Logging.LoggerMessage> only requires parsing a template once when the message is defined.</span></span>

<span data-ttu-id="96272-111">샘플 앱에서는 우선 순위 큐 처리 작업자 서비스를 사용하는 <xref:Microsoft.Extensions.Logging.LoggerMessage> 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96272-111">The sample app demonstrates <xref:Microsoft.Extensions.Logging.LoggerMessage> features with a priority queue processing worker service.</span></span> <span data-ttu-id="96272-112">이 앱은 작업 항목을 우선 순위에 따라 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-112">The app processes work items in priority order.</span></span> <span data-ttu-id="96272-113">이러한 작업이 발생하는 대로 로그 메시지는 <xref:Microsoft.Extensions.Logging.LoggerMessage> 패턴을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-113">As these operations occur, log messages are generated using the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

## <a name="define-a-logger-message"></a><span data-ttu-id="96272-114">로거 메시지 정의</span><span class="sxs-lookup"><span data-stu-id="96272-114">Define a logger message</span></span>

<span data-ttu-id="96272-115">[Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A)을 사용하여 메시지 로깅을 위한 <xref:System.Action> 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96272-115">Use [Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) to create an <xref:System.Action> delegate for logging a message.</span></span> <span data-ttu-id="96272-116"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 오버로드는 명명된 형식 문자열(템플릿)로 최대 6개의 형식 매개 변수 전달을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-116"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> overloads permit passing up to six type parameters to a named format string (template).</span></span>

<span data-ttu-id="96272-117"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 메서드에 제공된 문자열은 템플릿이며 보간된 문자열이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96272-117">The string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="96272-118">자리 표시자는 형식이 지정된 순서로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="96272-118">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="96272-119">템플릿의 자리 표시자 이름은 템플릿에서 알기 쉽고 일관되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-119">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="96272-120">구조적 로그 데이터 내에서 속성 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-120">They serve as property names within structured log data.</span></span> <span data-ttu-id="96272-121">자리 표시자 이름으로 [파스칼식 대/소문자](../../standard/design-guidelines/capitalization-conventions.md)를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-121">We recommend [Pascal casing](../../standard/design-guidelines/capitalization-conventions.md) for placeholder names.</span></span> <span data-ttu-id="96272-122">예: `{Item}`, `{DateTime}`</span><span class="sxs-lookup"><span data-stu-id="96272-122">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="96272-123">각 로그 메시지는 [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A)에서 만들어진 정적 필드에 보관된 <xref:System.Action>입니다.</span><span class="sxs-lookup"><span data-stu-id="96272-123">Each log message is an <xref:System.Action> held in a static field created by [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A).</span></span> <span data-ttu-id="96272-124">예를 들어 샘플 앱은 작업 항목 처리에 대한 로그 메시지를 설명하는 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96272-124">For example, the sample app creates a field to describe a log message for the processing of work items:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingField":::

<span data-ttu-id="96272-125"><xref:System.Action>의 경우 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-125">For the <xref:System.Action>, specify:</span></span>

- <span data-ttu-id="96272-126">로그 수준</span><span class="sxs-lookup"><span data-stu-id="96272-126">The log level.</span></span>
- <span data-ttu-id="96272-127">정적 확장 메서드의 이름이 있는 고유한 이벤트 식별자(<xref:Microsoft.Extensions.Logging.EventId>)입니다.</span><span class="sxs-lookup"><span data-stu-id="96272-127">A unique event identifier (<xref:Microsoft.Extensions.Logging.EventId>) with the name of the static extension method.</span></span>
- <span data-ttu-id="96272-128">메시지 템플릿(명명된 형식 문자열)</span><span class="sxs-lookup"><span data-stu-id="96272-128">The message template (named format string).</span></span>

<span data-ttu-id="96272-129">작업 항목이 처리를 위해 큐에서 제거될 때 작업자 서비스 앱이 다음을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-129">As work items are dequeued for processing the worker service app sets the:</span></span>

- <span data-ttu-id="96272-130">로그 수준을 <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>으로</span><span class="sxs-lookup"><span data-stu-id="96272-130">Log level to <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="96272-131">이벤트 ID를 `FailedToProcessWorkItem` 메서드의 이름이 있는 `13`로</span><span class="sxs-lookup"><span data-stu-id="96272-131">Event id to `13` with the name of the `FailedToProcessWorkItem` method.</span></span>
- <span data-ttu-id="96272-132">메시지 템플릿(명명된 형식 문자열)을 문자열로</span><span class="sxs-lookup"><span data-stu-id="96272-132">Message template (named format string) to a string.</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingAssignment":::

<span data-ttu-id="96272-133">구조적 로깅 저장소는 로깅을 보강하도록 이벤트 ID로 제공될 경우 이벤트 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96272-133">Structured logging stores may use the event name when it's supplied with the event id to enrich logging.</span></span> <span data-ttu-id="96272-134">예를 들어 [Serilog](https://github.com/serilog/serilog-extensions-logging)는 이벤트 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-134">For example, [Serilog](https://github.com/serilog/serilog-extensions-logging) uses the event name.</span></span>

<span data-ttu-id="96272-135"><xref:System.Action>은 강력한 형식의 확장 메서드를 통해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-135">The <xref:System.Action> is invoked through a strongly-typed extension method.</span></span> <span data-ttu-id="96272-136">`PriorityItemProcessed` 메서드는 작업 항목이 처리될 때마다 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-136">The `PriorityItemProcessed` method logs a message every time a work item is being processed.</span></span> <span data-ttu-id="96272-137">반면, 예외가 발생하는 경우 `FailedToProcessWorkItem`이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-137">Whereas, `FailedToProcessWorkItem` is called when (and if) an exception occurs:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

<span data-ttu-id="96272-138">앱의 콘솔 출력을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-138">Inspect the app's console output:</span></span>

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

<span data-ttu-id="96272-139">로그 메시지에 매개 변수를 전달하려면 정적 필드를 만들 때 최대 6개의 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-139">To pass parameters to a log message, define up to six types when creating the static field.</span></span> <span data-ttu-id="96272-140">샘플 앱에서는 <xref:System.Action> 필드의 `WorkItem` 형식을 정의하여 항목을 처리할 때 작업 항목 세부 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-140">The sample app logs the work item details when processing items by defining a `WorkItem` type for the <xref:System.Action> field:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

<span data-ttu-id="96272-141">대리자의 로그 메시지 템플릿은 제공되는 형식에서 해당 자리 표시자 값을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="96272-141">The delegate's log message template receives its placeholder values from the types provided.</span></span> <span data-ttu-id="96272-142">샘플 앱은 항목 매개 변수가 `WorkItem`인 작업 항목을 추가하기 위한 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-142">The sample app defines a delegate for adding a work item where the item parameter is a `WorkItem`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

<span data-ttu-id="96272-143">작업 항목을 처리 중임을 기록하는 정적 확장 메서드 `PriorityItemProcessed`는 작업 항목 인수 값을 받아 <xref:System.Action> 대리자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-143">The static extension method for logging that a work item is being processed, `PriorityItemProcessed`, receives the work item argument value and passes it to the <xref:System.Action> delegate:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

<span data-ttu-id="96272-144">작업자 서비스의 `ExecuteAsync` 메서드에서 메시지를 기록하기 위해 `PriorityItemProcessed`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-144">In the worker service's `ExecuteAsync` method, `PriorityItemProcessed` is called to log the message:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

<span data-ttu-id="96272-145">앱의 콘솔 출력을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-145">Inspect the app's console output:</span></span>

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a><span data-ttu-id="96272-146">로거 메시지 범위 정의</span><span class="sxs-lookup"><span data-stu-id="96272-146">Define logger message scope</span></span>

<span data-ttu-id="96272-147">[DefineScope(String)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) 메서드는 [로그 범위](logging.md#log-scopes)를 정의하기 위한 <xref:System.Func%601> 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96272-147">The [DefineScope(string)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) method creates a <xref:System.Func%601> delegate for defining a [log scope](logging.md#log-scopes).</span></span> <span data-ttu-id="96272-148"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 오버로드는 명명된 형식 문자열(템플릿)로 최대 3개의 형식 매개 변수 전달을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-148"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> overloads permit passing up to three type parameters to a named format string (template).</span></span>

<span data-ttu-id="96272-149"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> 메서드의 경우와 마찬가지로 <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 메서드에 제공된 문자열은 템플릿이며 보간된 문자열이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96272-149">As is the case with the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method, the string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="96272-150">자리 표시자는 형식이 지정된 순서로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="96272-150">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="96272-151">템플릿의 자리 표시자 이름은 템플릿에서 알기 쉽고 일관되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-151">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="96272-152">구조적 로그 데이터 내에서 속성 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96272-152">They serve as property names within structured log data.</span></span> <span data-ttu-id="96272-153">자리 표시자 이름으로 [파스칼식 대/소문자](../../standard/design-guidelines/capitalization-conventions.md)를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-153">We recommend [Pascal casing](../../standard/design-guidelines/capitalization-conventions.md) for placeholder names.</span></span> <span data-ttu-id="96272-154">예: `{Item}`, `{DateTime}`</span><span class="sxs-lookup"><span data-stu-id="96272-154">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="96272-155"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> 메서드를 사용하여 일련의 로그 메시지에 적용하도록 [로그 범위](logging.md#log-scopes)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-155">Define a [log scope](logging.md#log-scopes) to apply to a series of log messages using the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method.</span></span> <span data-ttu-id="96272-156">*appsettings.json* 의 콘솔 로거 섹션에서 `IncludeScopes`를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-156">Enable `IncludeScopes` in the console logger section of *appsettings.json*:</span></span>

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

<span data-ttu-id="96272-157">로그 범위를 만들려면 범위에 대한 <xref:System.Func%601> 대리자를 보유하는 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-157">To create a log scope, add a field to hold a <xref:System.Func%601> delegate for the scope.</span></span> <span data-ttu-id="96272-158">샘플 앱은 `_processingWorkScope`라는 필드를 만듭니다(*Internal/LoggerExtensions.cs*).</span><span class="sxs-lookup"><span data-stu-id="96272-158">The sample app creates a field called `_processingWorkScope` (*Internal/LoggerExtensions.cs*):</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

<span data-ttu-id="96272-159"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A>를 사용하여 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96272-159">Use <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> to create the delegate.</span></span> <span data-ttu-id="96272-160">대리자가 호출되는 경우 템플릿 인수로 사용하기 위해 최대 세 개의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96272-160">Up to three types can be specified for use as template arguments when the delegate is invoked.</span></span> <span data-ttu-id="96272-161">샘플 앱에서는 처리가 시작된 날짜/시간을 포함하는 메시지 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-161">The sample app uses a message template that includes the date time in which processing started:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

<span data-ttu-id="96272-162">로그 메시지에 대한 정적 확장 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-162">Provide a static extension method for the log message.</span></span> <span data-ttu-id="96272-163">메시지 템플릿에 표시되는 명명된 속성에 대한 모든 형식 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-163">Include any type parameters for named properties that appear in the message template.</span></span> <span data-ttu-id="96272-164">샘플 앱은 기록할 사용자 지정 타임스탬프에 `DateTime`을 사용하고 `_processingWorkScope`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-164">The sample app takes in a `DateTime` for a custom time stamp to log and returns `_processingWorkScope`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

<span data-ttu-id="96272-165">범위는 [using](../../csharp/language-reference/keywords/using-statement.md) 블록에서 로깅 확장 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-165">The scope wraps the logging extension calls in a [using](../../csharp/language-reference/keywords/using-statement.md) block:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

<span data-ttu-id="96272-166">앱의 콘솔 출력에서 로그 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="96272-166">Inspect the log messages in the app's console output.</span></span> <span data-ttu-id="96272-167">다음 결과에는 로그 범위 메시지가 포함된 로그 메시지의 우선 순위가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96272-167">The following result shows priority ordering of log messages with the log scope message included:</span></span>

```console
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Extreme (f5090ede-a337-4041-b914-f6bc0db5ae64): 'Verify communications'
info: Microsoft.Hosting.Lifetime[0]
      Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
      Hosting environment: Development
info: Microsoft.Hosting.Lifetime[0]
      Content root path: ..\worker-service-options
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-High (496d440f-2007-4391-b179-09d75ab52373): 'Validate collection'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (dea9e3f4-d7df-46d2-b7cd-5e0232eb98a5): 'Propagate selections'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (089d7f0d-da72-4b55-92fe-57b147838056): 'Enter pooling [contention]'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Low (6e68c4be-089f-4450-9080-1ea63fcbb686): 'Health check network'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (6f324134-6bb6-455f-81d4-553ab307c421): 'Ping weather service'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (37bf736c-7a26-4a2a-9e56-e89bcf3b8f35): 'Set process state'
```

## <a name="see-also"></a><span data-ttu-id="96272-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96272-168">See also</span></span>

- [<span data-ttu-id="96272-169">.NET의 로깅</span><span class="sxs-lookup"><span data-stu-id="96272-169">Logging in .NET</span></span>](logging.md)
