---
title: .NET에 대한 Azure SDK로 로깅
description: .NET 클라이언트 라이브러리에 대해 Azure SDK로 로깅을 활성화하는 방법에 대해 알아봅니다.
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433225"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="8012c-103">.NET에 대한 Azure SDK로 로깅</span><span class="sxs-lookup"><span data-stu-id="8012c-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="8012c-104">.NET 클라이언트 라이브러리에 대한 [Azure SDK에는](https://azure.microsoft.com/downloads/) 클라이언트 라이브러리 작업을 기록하는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="8012c-105">이를 통해 클라이언트 라이브러리가 Azure 서비스에 대해 하는 I/O 요청 및 응답을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="8012c-106">일반적으로 로그는 통신 문제를 디버깅하거나 진단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="8012c-107">이 문서에서는 .NET에 대한 Azure SDK로 로깅을 사용하도록 설정하는 세 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="8012c-108">콘솔 창에 로그</span><span class="sxs-lookup"><span data-stu-id="8012c-108">Log to the console window</span></span>
- <span data-ttu-id="8012c-109">.NET 진단 추적에 로그</span><span class="sxs-lookup"><span data-stu-id="8012c-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="8012c-110">사용자 지정 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="8012c-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8012c-111">이 문서는 .NET에 대한 Azure SDK의 최신 버전을 사용하는 클라이언트 라이브러리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="8012c-112">라이브러리가 지원되는지 확인하려면 [Azure SDK 최신 릴리스](https://azure.github.io/azure-sdk/releases/latest/index.html)목록을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8012c-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="8012c-113">응용 프로그램이 이전 버전의 Azure SDK 클라이언트 라이브러리를 사용하는 경우 해당 서비스 설명서의 특정 지침을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8012c-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="8012c-114">로그 정보</span><span class="sxs-lookup"><span data-stu-id="8012c-114">Log information</span></span>

<span data-ttu-id="8012c-115">SDK는 다음 정보를 기록하여 매개 변수 쿼리 및 헤더 값을 삭제하여 개인 데이터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="8012c-116">HTTP 요청 로그 항목:</span><span class="sxs-lookup"><span data-stu-id="8012c-116">HTTP request log entry:</span></span>

- <span data-ttu-id="8012c-117">고유 ID</span><span class="sxs-lookup"><span data-stu-id="8012c-117">Unique ID</span></span>
- <span data-ttu-id="8012c-118">HTTP 메서드</span><span class="sxs-lookup"><span data-stu-id="8012c-118">HTTP method</span></span>
- <span data-ttu-id="8012c-119">URI</span><span class="sxs-lookup"><span data-stu-id="8012c-119">URI</span></span>
- <span data-ttu-id="8012c-120">나가는 요청 헤더</span><span class="sxs-lookup"><span data-stu-id="8012c-120">Outgoing request headers</span></span>

<span data-ttu-id="8012c-121">HTTP 응답 로그 항목:</span><span class="sxs-lookup"><span data-stu-id="8012c-121">HTTP response log entry:</span></span>

- <span data-ttu-id="8012c-122">I/O 작업 시간(경과 시간)</span><span class="sxs-lookup"><span data-stu-id="8012c-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="8012c-123">요청 ID</span><span class="sxs-lookup"><span data-stu-id="8012c-123">Request ID</span></span>
- <span data-ttu-id="8012c-124">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="8012c-124">HTTP status code</span></span>
- <span data-ttu-id="8012c-125">HTTP 이유 구</span><span class="sxs-lookup"><span data-stu-id="8012c-125">HTTP reason phrase</span></span>
- <span data-ttu-id="8012c-126">응답 헤더</span><span class="sxs-lookup"><span data-stu-id="8012c-126">Response headers</span></span>
- <span data-ttu-id="8012c-127">오류 정보(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8012c-127">Error information, when applicable</span></span>

<span data-ttu-id="8012c-128">요청 및 응답 콘텐츠의 경우:</span><span class="sxs-lookup"><span data-stu-id="8012c-128">For request and response content:</span></span>

- <span data-ttu-id="8012c-129">콘텐츠 유형 헤더에 따라 텍스트 또는 바이트로 콘텐츠 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="8012c-130">[! NOTE} 콘텐츠 로깅은 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="8012c-131">활성화하려면 에서 `Diagnostics.IsLoggingContentEnabled` `true` `ClientOptions`설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="8012c-132">이벤트 로그는 일반적으로 다음 세 가지 수준 중 하나에서 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="8012c-133">요청 및 응답 이벤트에 대한 정보 제공</span><span class="sxs-lookup"><span data-stu-id="8012c-133">Informational for request and response events</span></span>
- <span data-ttu-id="8012c-134">오류 경고</span><span class="sxs-lookup"><span data-stu-id="8012c-134">Warning for errors</span></span>
- <span data-ttu-id="8012c-135">자세한 메시지 및 콘텐츠 로깅에 대한 자세한 내용</span><span class="sxs-lookup"><span data-stu-id="8012c-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="8012c-136">기본 제공 메서드를 사용하여 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="8012c-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="8012c-137">.NET 클라이언트 라이브러리에 대한 Azure SDK는 .NET에 대한 일반적인 [ `EventSource` 클래스를](/dotnet/api/system.diagnostics.tracing.eventsource)통해 ETW(Windows용 이벤트 추적)에 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="8012c-138">이벤트 소스를 사용하면 최소한의 성능 오버헤드로 응용 프로그램 코드에 구조화 된 로깅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="8012c-139">이러한 이벤트 로그에 액세스하려면 이벤트 리스너를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="8012c-140">SDK에는 .NET 응용 프로그램에 대한 포괄적인 로깅을 단순화하는 두 가지 정적 메서드가 포함된 `Azure.Core.Diagnostics.AzureEventSourceListener` 클래스(Azure.Core NuGet 패키지에 `CreateConsoleLogger` 정의됨)가 포함됩니다. `CreateTraceLogger`</span><span class="sxs-lookup"><span data-stu-id="8012c-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="8012c-141">이러한 메서드는 로그 수준을 지정하는 선택적 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="8012c-142">콘솔 창에 로그</span><span class="sxs-lookup"><span data-stu-id="8012c-142">Log to the console window</span></span>

<span data-ttu-id="8012c-143">.NET 클라이언트 라이브러리에 대한 Azure SDK의 핵심 원칙은 포괄적인 로그를 실시간으로 보는 기능을 단순화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="8012c-144">이 `CreateConsoleLogger` 방법을 사용하면 한 줄의 코드로 콘솔 창으로 로그를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="8012c-145">진단 추적에 로그</span><span class="sxs-lookup"><span data-stu-id="8012c-145">Log to diagnostic traces</span></span>

<span data-ttu-id="8012c-146">추적 리스너를 구현하는 경우 이 `CreateTraceLogger` 메서드를 사용하여 표준 .NET 이벤트[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)추적 메커니즘()에 로그온할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="8012c-147">.NET에서 이벤트 추적에 대한 자세한 내용은 [추적 리스너를](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8012c-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="8012c-148">이 예제는 자세한 내용의 로그 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="8012c-149">사용자 지정 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="8012c-149">Configure custom logging</span></span>

<span data-ttu-id="8012c-150">위에서 언급했듯이 .NET에 대한 Azure SDK에서 로그 메시지를 수신하도록 이벤트 리스너를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="8012c-151">위의 단순화된 메서드 중 하나를 사용하여 포괄적인 로깅을 구현하지 않으려면 `AzureEventSourceListener` 클래스의 인스턴스를 생성하고 작성하는 콜백 함수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="8012c-152">이 메서드는 처리 할 수 있는 로그 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="8012c-153">또한 인스턴스를 생성할 때 포함할 로그 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="8012c-154">다음 예제에서는 사용자 지정 메시지와 함께 콘솔에 로그온 하 고 수준 자세한 의 Azure 코어 이벤트로 필터링 되는 이벤트 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8012c-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="8012c-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8012c-155">Next steps</span></span>

- [<span data-ttu-id="8012c-156">Azure 앱 서비스에서 앱에 대한 진단 로깅 사용</span><span class="sxs-lookup"><span data-stu-id="8012c-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="8012c-157">[Azure 보안 로깅 및 감사](https://docs.microsoft.com/azure/security/fundamentals/log-audit) 옵션 검토</span><span class="sxs-lookup"><span data-stu-id="8012c-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="8012c-158">[Azure 플랫폼 로그](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) 사용 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="8012c-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="8012c-159">[.NET 코어 로깅 및 추적에](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing) 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8012c-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
