---
title: .NET용 Azure SDK를 사용하여 로깅
description: .NET 용 Azure SDK 클라이언트 라이브러리를 사용하여 로깅을 사용하도록 설정하는 방법 알아보기
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: 0b255713bc9c13e0cbdaeb25a3d0fe46e91e815d
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416027"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="bf7e8-103">.NET용 Azure SDK를 사용하여 로깅</span><span class="sxs-lookup"><span data-stu-id="bf7e8-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="bf7e8-104">.NET용 [Azure SDK](https://azure.microsoft.com/downloads/) 클라이언트 라이브러리에는 클라이언트 라이브러리 작업을 로그하는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="bf7e8-105">이를 통해 클라이언트 라이브러리가 Azure 서비스에 대해 수행하는 I/O 요청 및 응답을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="bf7e8-106">일반적으로 로그는 통신 문제를 디버그하거나 진단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="bf7e8-107">이 문서에서는 .NET용 Azure SDK를 사용하여 로깅하도록 설정하는 세 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="bf7e8-108">콘솔 창에 로그</span><span class="sxs-lookup"><span data-stu-id="bf7e8-108">Log to the console window</span></span>
- <span data-ttu-id="bf7e8-109">.NET 진단 추적에 로그</span><span class="sxs-lookup"><span data-stu-id="bf7e8-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="bf7e8-110">사용자 지정 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="bf7e8-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf7e8-111">이 문서는 가장 최신 버전의 .NET용 Azure SDK를 사용하는 클라이언트 라이브러리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="bf7e8-112">라이브러리가 지원되는지 확인하려면 [Azure SDK 최신 릴리스](https://azure.github.io/azure-sdk/releases/latest/index.html) 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="bf7e8-113">애플리케이션에서 이전 버전의 Azure SDK 클라이언트 라이브러리를 사용하는 경우 해당 서비스 설명서의 특정 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="bf7e8-114">로그 정보</span><span class="sxs-lookup"><span data-stu-id="bf7e8-114">Log information</span></span>

<span data-ttu-id="bf7e8-115">SDK는 다음 정보를 로그하고, 매개 변수 쿼리 및 헤더 값을 삭제하여 개인 데이터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="bf7e8-116">HTTP 요청 로그 항목:</span><span class="sxs-lookup"><span data-stu-id="bf7e8-116">HTTP request log entry:</span></span>

- <span data-ttu-id="bf7e8-117">고유 ID</span><span class="sxs-lookup"><span data-stu-id="bf7e8-117">Unique ID</span></span>
- <span data-ttu-id="bf7e8-118">HTTP 메서드</span><span class="sxs-lookup"><span data-stu-id="bf7e8-118">HTTP method</span></span>
- <span data-ttu-id="bf7e8-119">URI</span><span class="sxs-lookup"><span data-stu-id="bf7e8-119">URI</span></span>
- <span data-ttu-id="bf7e8-120">나가는 요청 헤더</span><span class="sxs-lookup"><span data-stu-id="bf7e8-120">Outgoing request headers</span></span>

<span data-ttu-id="bf7e8-121">HTTP 응답 로그 항목:</span><span class="sxs-lookup"><span data-stu-id="bf7e8-121">HTTP response log entry:</span></span>

- <span data-ttu-id="bf7e8-122">I/O 작업 기간(경과 시간)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="bf7e8-123">요청 ID</span><span class="sxs-lookup"><span data-stu-id="bf7e8-123">Request ID</span></span>
- <span data-ttu-id="bf7e8-124">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="bf7e8-124">HTTP status code</span></span>
- <span data-ttu-id="bf7e8-125">HTTP 이유 구문</span><span class="sxs-lookup"><span data-stu-id="bf7e8-125">HTTP reason phrase</span></span>
- <span data-ttu-id="bf7e8-126">응답 헤더</span><span class="sxs-lookup"><span data-stu-id="bf7e8-126">Response headers</span></span>
- <span data-ttu-id="bf7e8-127">오류 정보(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="bf7e8-127">Error information, when applicable</span></span>

<span data-ttu-id="bf7e8-128">요청 및 응답 콘텐츠:</span><span class="sxs-lookup"><span data-stu-id="bf7e8-128">For request and response content:</span></span>

- <span data-ttu-id="bf7e8-129">콘텐츠 형식 헤더에 따라 텍스트 또는 바이트로된 콘텐츠 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="bf7e8-130">[!참고} 콘텐츠 로깅은 기본적으로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="bf7e8-131">사용하도록 설정하려면 `ClientOptions`에서 `Diagnostics.IsLoggingContentEnabled`를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="bf7e8-132">이벤트 로그는 일반적으로 다음 세 가지 수준 중 하나에서 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="bf7e8-133">요청 및 응답 이벤트에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="bf7e8-133">Informational for request and response events</span></span>
- <span data-ttu-id="bf7e8-134">오류에 대한 경고</span><span class="sxs-lookup"><span data-stu-id="bf7e8-134">Warning for errors</span></span>
- <span data-ttu-id="bf7e8-135">자세한 메시지 및 콘텐츠 로깅에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="bf7e8-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="bf7e8-136">기본 제공 메서드를 사용하여 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="bf7e8-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="bf7e8-137">.NET용 Azure SDK 클라이언트 라이브러리는 .NET에서 일반적인 [`EventSource` 클래스](/dotnet/api/system.diagnostics.tracing.eventsource)를 통해 ETW(Windows용 이벤트 추적)에 이벤트를 로그합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="bf7e8-138">이벤트 소스를 사용하면 최소한의 성능 오버헤드로 애플리케이션 코드에서 구조적 로깅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="bf7e8-139">이러한 이벤트 로그에 대한 액세스 권한을 얻으려면 이벤트 수신기를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="bf7e8-140">SDK에는 .NET 애플리케이션에 대한 포괄적인 로깅을 간소화하는 두 개의 정적 메서드인 `CreateConsoleLogger` 및 `CreateTraceLogger`를 포함하는 `Azure.Core.Diagnostics.AzureEventSourceListener` 클래스(Azure.Core NuGet 패키지에 정의됨)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="bf7e8-141">이러한 메서드는 로그 수준을 지정하는 선택적 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="bf7e8-142">콘솔 창에 로그</span><span class="sxs-lookup"><span data-stu-id="bf7e8-142">Log to the console window</span></span>

<span data-ttu-id="bf7e8-143">.NET용 Azure SDK 클라이언트 라이브러리의 핵심 개념은 실시간으로 포괄적인 로그를 보는 기능을 간소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="bf7e8-144">`CreateConsoleLogger` 메서드를 사용하면 한 줄의 코드로 로그를 콘솔 창에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="bf7e8-145">진단 추적에 로그</span><span class="sxs-lookup"><span data-stu-id="bf7e8-145">Log to diagnostic traces</span></span>

<span data-ttu-id="bf7e8-146">추적 수신기를 구현하는 경우 `CreateTraceLogger` 메서드를 사용하여 표준 .NET 이벤트 추적 메커니즘([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing))에 로그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="bf7e8-147">.NET의 이벤트 추적에 대한 자세한 내용은 [추적 수신기](../framework/debug-trace-profile/trace-listeners.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-147">For more information on event tracing in .NET, see [Trace Listeners](../framework/debug-trace-profile/trace-listeners.md).</span></span> <span data-ttu-id="bf7e8-148">이 예제에서는 자세한 로그 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="bf7e8-149">사용자 지정 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="bf7e8-149">Configure custom logging</span></span>

<span data-ttu-id="bf7e8-150">위에서 설명한 것처럼 .NET용 Azure SDK에서 로그 메시지를 수신하려면 이벤트 수신기를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="bf7e8-151">위의 단순화된 메서드 중 하나를 사용하여 포괄적인 로깅을 구현하지 않으려는 경우 `AzureEventSourceListener` 클래스의 인스턴스를 생성하고 작성한 콜백 함수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="bf7e8-152">이 메서드는 처리할 수 있는 로그 메시지를 수신하지만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="bf7e8-153">또한 인스턴스를 생성할 때 포함할 로그 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="bf7e8-154">다음 예제에서는 사용자 지정 메시지를 사용하여 콘솔에 로그하고 수준 세부 정보의 Azure 핵심 이벤트로 필터링되는 이벤트 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e8-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a><span data-ttu-id="bf7e8-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf7e8-155">Next steps</span></span>

- [<span data-ttu-id="bf7e8-156">Azure App Service에서 앱에 대한 진단 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="bf7e8-156">Enable diagnostics logging for apps in Azure App Service</span></span>](/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="bf7e8-157">[Azure 보안 로깅 및 감사](/azure/security/fundamentals/log-audit) 옵션 검토</span><span class="sxs-lookup"><span data-stu-id="bf7e8-157">Review [Azure security logging and auditing](/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="bf7e8-158">[Azure 플랫폼 로그](/azure/azure-monitor/platform/platform-logs-overview)를 사용하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="bf7e8-158">Learn how to work with [Azure platform logs](/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="bf7e8-159">[.NET Core 로깅 및 추적](../core/diagnostics/logging-tracing.md)에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="bf7e8-159">Read more about [.NET Core logging and tracing](../core/diagnostics/logging-tracing.md)</span></span>
