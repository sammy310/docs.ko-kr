---
title: 분산 추적 - .NET
description: .NET 분산 추적에 대해 소개합니다.
ms.date: 02/02/2021
ms.openlocfilehash: d29c803dfec00474562abdc61ce65ea3f3faa133
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431440"
---
# <a name="net-distributed-tracing"></a><span data-ttu-id="f9bf4-103">.NET 분산 추적</span><span class="sxs-lookup"><span data-stu-id="f9bf4-103">.NET Distributed Tracing</span></span>

<span data-ttu-id="f9bf4-104">분산 추적은 분산 시스템에서 추적 데이터를 게시하고 관찰하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-104">Distributed tracing is the way to publish and observe tracing data in a distributed system.</span></span>
<span data-ttu-id="f9bf4-105">.NET Framework 및 .NET Core는 <xref:System.Diagnostics> API를 통해 추적을 지원해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-105">.NET Framework and .NET Core has been supporting tracing through the <xref:System.Diagnostics> APIs.</span></span>

- <span data-ttu-id="f9bf4-106"><xref:System.Diagnostics.Activity?displayProperty=nameWithType> 클래스 - 진단 컨텍스트를 저장 및 액세스하고 로깅 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-106"><xref:System.Diagnostics.Activity?displayProperty=nameWithType> class which allows storing and accessing diagnostics context and consuming it with logging system.</span></span>
- <span data-ttu-id="f9bf4-107"><xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType> - 계측된 프로세스 내에서 사용하기 위한 다양한 데이터 페이로드의 프로덕션 시간 로깅에 대한 코드를 계측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-107"><xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType> that allows code to be instrumented for production-time logging of rich data payloads for consumption within the process that was instrumented.</span></span>

<span data-ttu-id="f9bf4-108">다음은 HTTP 수신 요청에서 추적 데이터를 게시하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-108">Here is an example that shows how to publish tracing data from the HTTP incoming requests:</span></span>

```csharp
   public void OnIncomingRequest(DiagnosticListener httpListener, HttpContext context)
   {
       if (httpListener.IsEnabled("Http_In"))
       {
           var activity = new Activity("Http_In");

           //add tags, baggage, etc.
           activity.SetParentId(context.Request.headers["Request-id"])
           foreach (var pair in context.Request.Headers["Correlation-Context"])
           {
               var baggageItem = NameValueHeaderValue.Parse(pair);
               activity.AddBaggage(baggageItem.Key, baggageItem.Value);
           }
           httpListener.StartActivity(activity, new { context });
           try
           {
               //process request ...
           }
           finally
           {
               //stop activity
               httpListener.StopActivity(activity, new {context} );
           }
       }
   }
```

<span data-ttu-id="f9bf4-109">다음은 활동 이벤트를 수신 대기하는 방법의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-109">Here is example for how to listen to the Activity events:</span></span>

```csharp
    DiagnosticListener.AllListeners.Subscribe(delegate (DiagnosticListener listener)
    {
        if (listener.Name == "MyActivitySource")
        {
            listener.Subscribe(delegate (KeyValuePair<string, object> value)
            {
                if (value.Key.EndsWith("Start", StringComparison.Ordinal))
                    LogActivityStart();
                else if (value.Key.EndsWith("Stop", StringComparison.Ordinal))
                    LogActivityStop();
            });
        }
    }
```

<span data-ttu-id="f9bf4-110">.NET 5.0에서는 [OpenTelemetry](https://opentelemetry.io/) 추적 시나리오가 가능하도록 분산 추적의 기능이 확장되고, 샘플링 기능이 추가되고, 추적 코딩 패턴이 간소화되고, 활동 이벤트 수신 대기가 더 쉽고 유연해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-110">.NET 5.0 has extended the capability of the distributed tracing to allow the [OpenTelemetry](https://opentelemetry.io/) tracing scenarios, added Sampling capabilities, simplified the tracing coding pattern, and made listening to the Activity events easier and flexible.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bf4-111">추가된 모든 .NET 5.0 기능에 액세스하려면 프로젝트가 [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/) NuGet 패키지 버전 5.0 이상을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-111">To access all added .NET 5.0 capabilities, ensure your project references the [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/) NuGet package version 5.0 or later.</span></span> <span data-ttu-id="f9bf4-112">이 패키지는 지원되는 버전의 .NET Framework, .NET Core 및 .NET Standard를 대상으로 하는 라이브러리 및 앱에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-112">This package can be used in libraries and apps targeting any supported version of the .NET Framework, .NET Core, and .NET Standard.</span></span> <span data-ttu-id="f9bf4-113">.NET 5.0 이상을 대상으로 하는 경우 .NET 런타임과 함께 설치된 공유 라이브러리에 패키지가 포함되어 있으므로 수동으로 패키지를 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-113">If targeting .NET 5.0 or later, there is no need to manually reference the package as it is included in the shared library installed with the .NET Runtime.</span></span>

## <a name="getting-started-with-tracing"></a><span data-ttu-id="f9bf4-114">추적 시작</span><span class="sxs-lookup"><span data-stu-id="f9bf4-114">Getting Started With Tracing</span></span>

<span data-ttu-id="f9bf4-115">애플리케이션 및 라이브러리는 단순히 <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Activity?displayProperty=nameWithType> 클래스를 사용하여 쉽게 추적 데이터를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-115">Applications and libraries can easily publish tracing data by simply using the <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> and the <xref:System.Diagnostics.Activity?displayProperty=nameWithType> classes.</span></span>

### <a name="activitysource"></a><span data-ttu-id="f9bf4-116">ActivitySource</span><span class="sxs-lookup"><span data-stu-id="f9bf4-116">ActivitySource</span></span>

<span data-ttu-id="f9bf4-117">추적 데이터를 게시하는 첫 번째 단계는 ActivitySource 클래스의 인스턴스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-117">The first step to publish tracing data is to create an instance of the ActivitySource class.</span></span> <span data-ttu-id="f9bf4-118">ActivitySource는 활동 개체를 만들고 시작하는 API와 활동 이벤트를 수신 대기하기 위해 ActivityListener 개체를 등록하는 API를 제공하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-118">The ActivitySource is the class that provides APIs to create and start Activity objects and to register ActivityListener objects to listen to the Activity events.</span></span>

```csharp
    private static ActivitySource source = new ActivitySource("MyCompany.MyComponent.SourceName", "v1");
```

#### <a name="best-practices"></a><span data-ttu-id="f9bf4-119">모범 사례</span><span class="sxs-lookup"><span data-stu-id="f9bf4-119">Best Practices</span></span>

- <span data-ttu-id="f9bf4-120">ActivitySource를 한 번 만들어 정적 변수에 저장하고 필요에 따라 해당 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-120">Create the ActivitySource once and store it in a static variable and use that instance as long as needed.</span></span>

- <span data-ttu-id="f9bf4-121">생성자에 전달된 소스 이름은 다른 소스와의 충돌을 방지하기 위해 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-121">The source name passed to the constructor has to be unique to avoid the conflicts with any other sources.</span></span> <span data-ttu-id="f9bf4-122">회사 이름, 구성 요소 이름, 소스 이름이 포함된 계층 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-122">It is recommended to use a hierarchical name contains the company name, the component name, and the source name.</span></span> <span data-ttu-id="f9bf4-123">예들 들어 `Microsoft.System.HttpClient.HttpInOutRequests`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-123">For example, `Microsoft.System.HttpClient.HttpInOutRequests`.</span></span>

- <span data-ttu-id="f9bf4-124">버전 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-124">The version parameter is optional.</span></span> <span data-ttu-id="f9bf4-125">여러 버전의 라이브러리 또는 애플리케이션을 릴리스하고 각 버전의 소스를 구분하려는 경우 버전을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-125">It is recommended to provide the version in case you plan to release multiple versions of the library or the application and want to distinguish between the sources of different versions.</span></span>

### <a name="activity-creation"></a><span data-ttu-id="f9bf4-126">활동 만들기</span><span class="sxs-lookup"><span data-stu-id="f9bf4-126">Activity Creation</span></span>

<span data-ttu-id="f9bf4-127">이제 만든 ActivitySource 개체를 사용하여 코드의 원하는 위치에서 추적 데이터를 기록하는 데 사용되는 활동 개체를 만들고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-127">Now the created ActivitySource object can be used to create and start Activity objects which are used to log any tracing data in any desired places in the code.</span></span>

```csharp
        using (Activity activity = source.StartActivity("OperationName"))
        {
            // Do something

            activity?.AddTag("key", "value"); // log the tracing
        }
```

<span data-ttu-id="f9bf4-128">다음 샘플 코드는 활동 개체를 만든 다음 추적 태그 `key` 및 `value`를 기록하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-128">This sample code tries to create the Activity object and then logs some tracing tag `key` and `value`.</span></span>

#### <a name="notes"></a><span data-ttu-id="f9bf4-129">참고</span><span class="sxs-lookup"><span data-stu-id="f9bf4-129">Notes</span></span>

- <span data-ttu-id="f9bf4-130">`ActivitySource.StartActivity`는 활동을 만드는 동시에 시작하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-130">`ActivitySource.StartActivity` tries to create and start the activity at the same time.</span></span> <span data-ttu-id="f9bf4-131">나열된 코드 패턴에서는 블록을 실행한 후 만든 활동 개체를 자동으로 삭제하는 `using` 블록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-131">The listed code pattern is using the `using` block which automatically disposes the created Activity object after executing the block.</span></span> <span data-ttu-id="f9bf4-132">활동 개체를 삭제하면 이 시작된 활동이 중지되며 코드에서 명시적으로 활동을 중지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-132">Disposing the Activity object will stop this started activity and the code doesn't have to explicitly stop the activity.</span></span> <span data-ttu-id="f9bf4-133">그러면 코딩 패턴이 단순해집니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-133">That simplifies the coding pattern.</span></span>

- <span data-ttu-id="f9bf4-134">`ActivitySource.StartActivity`는 내부적으로 해당 이벤트에 대한 수신기가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-134">`ActivitySource.StartActivity` internally figures out if there are any listeners to such events.</span></span> <span data-ttu-id="f9bf4-135">등록된 수신기가 없거나 해당 이벤트에 관심이 없는 수신기가 있는 경우 `ActivitySource.StartActivity`는 단순히 `null`을 반환하고 활동 개체를 만들지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-135">If there are no registered listeners or there are listeners which are not interested in such an event, `ActivitySource.StartActivity` simply will return `null` and avoid creating the Activity object.</span></span> <span data-ttu-id="f9bf4-136">이 때문에 코드에서 문 `activity?.AddTag`에 null 허용 연산자 `?`를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-136">That is why the code used the nullable operator `?`  in the statement `activity?.AddTag`.</span></span> <span data-ttu-id="f9bf4-137">일반적으로 `using` 블록 내에서 항상 활동 개체 이름 뒤에 null 허용 연산자 `?`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-137">In general, inside the `using` block, always use the nullable operator `?` after the activity object name.</span></span>

## <a name="listening-to-the-activity-events"></a><span data-ttu-id="f9bf4-138">활동 이벤트 수신 대기</span><span class="sxs-lookup"><span data-stu-id="f9bf4-138">Listening to the Activity Events</span></span>

<span data-ttu-id="f9bf4-139">.NET에서는 하나 이상의 ActivitySource에서 트리거된 활동 이벤트를 수신 대기하는 데 사용할 수 있는 클래스 <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-139">.NET provides the class <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType> which can be used to listen to the Activity events triggered from one or more ActivitySources.</span></span>
<span data-ttu-id="f9bf4-140">이 수신기를 사용하여 추적 데이터를 수집하거나, 샘플을 만들거나, 활동 개체를 강제로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-140">The listener can be used to collect tracing data, sample, or force creating the Activity object.</span></span>

<span data-ttu-id="f9bf4-141">`ActivityListener` 클래스는 서로 다른 이벤트를 처리하는 다양한 콜백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-141">The `ActivityListener` class provides a different callbacks to handle different events.</span></span>

```csharp

ActivityListener listener = new ActivityListener()

ShouldListenTo = (activitySource) => object.ReferenceEquals(source, activitySource),
ActivityStarted = activity => /* Handle the Activity start event here */ DoSomething(),
ActivityStopped = activity => /* Handle the Activity stop event here */ DoSomething(),
SampleUsingParentId = (ref ActivityCreationOptions<string> activityOptions) => ActivitySamplingResult.AllData,
Sample = (ref ActivityCreationOptions<ActivityContext> activityOptions) => ActivitySamplingResult.AllData

// Enable the listener
ActivitySource.AddActivityListener(listener);
```

- <span data-ttu-id="f9bf4-142">`ShouldListenTo`를 사용하면 특정 `ActivitySource` 개체를 수신 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-142">`ShouldListenTo` enables listening to specific `ActivitySource` objects.</span></span> <span data-ttu-id="f9bf4-143">이 예제에서는 이전에 만든 `ActivitySource` 개체를 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-143">In the example, it enables listening to the `ActivitySource` object we have previously created.</span></span> <span data-ttu-id="f9bf4-144">추가로 입력 `ActivitySource`의 `Name` 및 `Version`을 확인하여 다른 `ActivitySource` 개체를 수신 대기할 수 있는 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-144">There is more flexibility to listen to any other `ActivitySource` objects by checking the `Name` and `Version` of the input `ActivitySource`.</span></span>

- <span data-ttu-id="f9bf4-145">`ActivityStarted` 및 `ActivityStopped`를 사용하면 `ShouldListenTo` 콜백에서 활성화된 `ActivitySource` 개체가 생성한 모든 `Activity` 개체에 대해 `Activity` 시작 및 중지 이벤트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-145">`ActivityStarted` and `ActivityStopped` enable getting the `Activity` Start and Stop events for all `Activity` objects created by the `ActivitySource` objects which were enabled by the `ShouldListenTo` callback.</span></span>

- <span data-ttu-id="f9bf4-146">`Sample` 및 `SampleUsingParentId`는 샘플링을 위한 기본 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-146">`Sample` and `SampleUsingParentId` are the main callbacks which intended for sampling.</span></span> <span data-ttu-id="f9bf4-147">이러한 두 콜백은 `ActivitySamplingResult` 열거형 값을 반환합니다. 이 값은 현재 `Activity` 만들기 요청을 샘플링 또는 제외하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-147">These two callbacks return the `ActivitySamplingResult` enum value which can tell either to sample in or out the current `Activity` creation request.</span></span> <span data-ttu-id="f9bf4-148">콜백이 `ActivitySamplingResult.None`을 반환하고 다른 활성화된 수신기가 다른 값을 반환하지 않는 경우 활동이 생성되지 않으며 `ActivitySource.StartActivity`가 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-148">If the callback returns `ActivitySamplingResult.None` and no other enabled listeners return different value, then the Activity will not get created and `ActivitySource.StartActivity` will return `null`.</span></span> <span data-ttu-id="f9bf4-149">그렇지 않으면 `Activity` 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-149">Otherwise, the `Activity` object will get created.</span></span>

## <a name="net-50-new-features"></a><span data-ttu-id="f9bf4-150">.NET 5.0 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f9bf4-150">.NET 5.0 New Features</span></span>

<span data-ttu-id="f9bf4-151">`Activity` 클래스는 추적 시나리오를 지원해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-151">For awhile the `Activity` class has been supporting tracing scenarios.</span></span> <span data-ttu-id="f9bf4-152">이 클래스를 사용하여 추적 데이터의 키-값 쌍인 태그를 추가할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-152">It allowed adding tags which are key-value pairs of tracing data.</span></span> <span data-ttu-id="f9bf4-153">또한 네트워크를 통해 전파하기 위한 키-값 쌍인 Baggage를 지원해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-153">It has been supporting Baggage which is are key-value pairs intended to be propagated across the wire.</span></span>

<span data-ttu-id="f9bf4-154">.NET 5.0은 주로 OpenTelemetry 시나리오를 구현하기 위한 더 많은 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-154">.NET 5.0 supports more features mainly to enable OpenTelemetry scenarios.</span></span>

### <a name="activitycontext"></a><span data-ttu-id="f9bf4-155">ActivityContext</span><span class="sxs-lookup"><span data-stu-id="f9bf4-155">ActivityContext</span></span>

<span data-ttu-id="f9bf4-156"><xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType>는 추적 작업의 컨텍스트를 전달하는 구조체입니다(예: 추적 ID, 범위 ID, 추적 플래그, 추적 상태).</span><span class="sxs-lookup"><span data-stu-id="f9bf4-156"><xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType> is the struct carrying the context of the tracing operations (e.g. the trace Id, Span Id, trace flags, and trace state).</span></span> <span data-ttu-id="f9bf4-157">이제 부모 추적 컨텍스트를 제공하는 새 `Activity`를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-157">Now it is possible to create a new `Activity` providing the parent tracing context.</span></span> <span data-ttu-id="f9bf4-158">또한 `Activity.Context` 속성을 호출하여 `Activity` 개체에서 추적 컨텍스트를 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-158">Also, it is easy to extract the tracing context from any `Activity` object by calling `Activity.Context` property.</span></span>

### <a name="activitylink"></a><span data-ttu-id="f9bf4-159">ActivityLink</span><span class="sxs-lookup"><span data-stu-id="f9bf4-159">ActivityLink</span></span>

<span data-ttu-id="f9bf4-160"><xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType>는 관련된 `Activity` 개체에 연결될 수 있는 추적 컨텍스트 인스턴스를 포함하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-160"><xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType> is the struct containing the tracing context instance which can be linked to casually related `Activity` objects.</span></span> <span data-ttu-id="f9bf4-161">`Activity`를 만들 때 링크 목록을 `ActivitySource.StartActivity` 메서드로 전달하여 `Activity` 개체에 링크를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-161">Links can be added to the `Activity` object by passing the links list to `ActivitySource.StartActivity` method when creating the `Activity`.</span></span> <span data-ttu-id="f9bf4-162">`Activity.Links` 속성을 사용하여 개체 연결 링크 `Activity`를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-162">The `Activity` object attached links can be retrieved using the property `Activity.Links`.</span></span>

### <a name="activityevent"></a><span data-ttu-id="f9bf4-163">ActivityEvent</span><span class="sxs-lookup"><span data-stu-id="f9bf4-163">ActivityEvent</span></span>

<span data-ttu-id="f9bf4-164"><xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType>는 이름 및 타임스탬프를 포함하는 이벤트와 선택적 태그 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-164"><xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType> represents an event containing a name and a timestamp, as well as an optional list of tags.</span></span> <span data-ttu-id="f9bf4-165">`Activity.AddEvent` 메서드를 호출하여 `Activity` 개체에 이벤트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-165">Events can be added to the `Activity` object by calling `Activity.AddEvent` method.</span></span> <span data-ttu-id="f9bf4-166">`Activity` 개체 이벤트의 전체 목록은 `Activity.Events` 속성을 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-166">The whole list of the `Activity` object Events can be retrieved using the property `Activity.Events`.</span></span>

### <a name="activitykind"></a><span data-ttu-id="f9bf4-167">ActivityKind</span><span class="sxs-lookup"><span data-stu-id="f9bf4-167">ActivityKind</span></span>

<span data-ttu-id="f9bf4-168"><xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType>는 추적의 활동, 부모 및 자식 간의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-168"><xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType> describes the relationship between the activity, its parents and its children in a trace.</span></span> <span data-ttu-id="f9bf4-169">`Activity`를 만들 때 종류 값을 `ActivitySource.StartActivity` 메서드에 전달하여 `Activity` 개체에 종류를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-169">Kind can be set to the `Activity` object by passing the kind value to `ActivitySource.StartActivity` method when creating the `Activity`.</span></span> <span data-ttu-id="f9bf4-170">`Activity.Kind` 속성을 사용하여 `Activity` 개체 종류를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-170">The `Activity` object kind can be retrieved using the property `Activity.Kind`.</span></span>

### <a name="isalldatarequested"></a><span data-ttu-id="f9bf4-171">IsAllDataRequested</span><span class="sxs-lookup"><span data-stu-id="f9bf4-171">IsAllDataRequested</span></span>

<span data-ttu-id="f9bf4-172"><xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType>는 이 활동을 모든 전파 정보뿐만 아니라 링크, 태그 및 이벤트와 같은 다른 모든 속성으로 채워야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-172"><xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType> indicates whether this activity should be populated with all the propagation information, as well as all the other properties, such as links, tags, and events.</span></span> <span data-ttu-id="f9bf4-173">`IsAllDataRequested`의 값은 모든 수신기 `Sample` 및 `SampleUsingParentId` 콜백에서 반환된 결과로부터 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-173">The value of `IsAllDataRequested` is determined from the result returned from all listeners `Sample` and `SampleUsingParentId` callbacks.</span></span> <span data-ttu-id="f9bf4-174">`Activity.IsAllDataRequested` 속성을 사용하여 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-174">The value can be retrieved using `Activity.IsAllDataRequested` property.</span></span>

### <a name="activitysource"></a><span data-ttu-id="f9bf4-175">Activity.Source</span><span class="sxs-lookup"><span data-stu-id="f9bf4-175">Activity.Source</span></span>

<span data-ttu-id="f9bf4-176"><xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType>는 이 활동과 연결된 활동 소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-176"><xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType> gets the activity source associated with this activity.</span></span>

### <a name="activitydisplayname"></a><span data-ttu-id="f9bf4-177">Activity.DisplayName</span><span class="sxs-lookup"><span data-stu-id="f9bf4-177">Activity.DisplayName</span></span>

<span data-ttu-id="f9bf4-178"><xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType>를 사용하면 활동의 표시 이름을 가져오거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-178"><xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType> allows getting or setting a display name for the activity.</span></span>

### <a name="activitytagobjects"></a><span data-ttu-id="f9bf4-179">Activity.TagObjects</span><span class="sxs-lookup"><span data-stu-id="f9bf4-179">Activity.TagObjects</span></span>

<span data-ttu-id="f9bf4-180">`Activity` 클래스에는 키 및 값에 대한 문자열 형식 태그의 키-값 쌍 목록을 반환하는 `Activity.Tags` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-180">`Activity` class has the property `Activity.Tags` which return the a key-value pair list of the tags of type string for the key and value.</span></span> <span data-ttu-id="f9bf4-181">이러한 태그는 `AddTag(string, string)` 메서드를 사용하여 `Activity`에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-181">Such Tags can be added to the `Activity` using the method `AddTag(string, string)`.</span></span> <span data-ttu-id="f9bf4-182">`Activity`는 모든 형식의 값을 허용하는 오버로드된 메서드 `AddTag(string, object)`를 제공하여 태그 지원을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-182">`Activity` has extended the support of tags by providing the overloaded method `AddTag(string, object)` allowing values of any type.</span></span>  <span data-ttu-id="f9bf4-183">이러한 태그의 전체 목록은 <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>를 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-183">The complete list of such tags can be retrieved using <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>.</span></span>

## <a name="sampling"></a><span data-ttu-id="f9bf4-184">샘플링</span><span class="sxs-lookup"><span data-stu-id="f9bf4-184">Sampling</span></span>

<span data-ttu-id="f9bf4-185">샘플링은 수집되고 백 엔드로 전송되는 추적 샘플 수를 줄임으로써 노이즈 및 오버헤드를 제어하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-185">Sampling is a mechanism to control the noise and overhead by reducing the number of samples of traces collected and sent to the backend.</span></span> <span data-ttu-id="f9bf4-186">샘플링은 중요한 OpenTelemetry 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-186">Sampling is an important OpenTelemetry scenario.</span></span> <span data-ttu-id="f9bf4-187">.NET 5.0에서는 샘플링을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-187">In .NET 5.0 it is easy to allow sampling.</span></span> <span data-ttu-id="f9bf4-188">이 메서드를 호출하는 경우 `ActivitySource.StartActivity`를 사용하여 새 `Activity` 개체를 만들고 사용 가능한 모든 데이터(예: 태그, 종류, 링크 등)를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-188">A good practice is to create the new `Activity` objects using `ActivitySource.StartActivity` and try to provide all possible available data (e.g. tags, kind, links, ...etc.) when calling this method.</span></span> <span data-ttu-id="f9bf4-189">데이터를 제공하면 `ActivityListener`를 사용하여 구현된 샘플러가 적절한 샘플링 결정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-189">Providing the data will allow the samplers implemented using the `ActivityListener` to have a proper sampling decision.</span></span> <span data-ttu-id="f9bf4-190">`Activity` 개체를 만들기 전에 데이터가 생성되는 것을 방지하기 위해 성능이 중요한 경우 `ActivitySource.HasListeners` 속성은 필요한 데이터를 만들기 전에 수신기가 있는지 확인하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-190">If the performance is critical to avoid creating the data before creating the `Activity` object, the property `ActivitySource.HasListeners` comes in handy to check if there are any listeners before creating the needed data.</span></span>

## <a name="opentelemetry"></a><span data-ttu-id="f9bf4-191">OpenTelemetry</span><span class="sxs-lookup"><span data-stu-id="f9bf4-191">OpenTelemetry</span></span>

<span data-ttu-id="f9bf4-192">OpenTelemetry SDK에는 엔드투엔드 분산 추적 시나리오를 지원하는 다양한 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-192">OpenTelemetry SDK comes with many features that support end-to-end distributed tracing scenarios.</span></span> <span data-ttu-id="f9bf4-193">선택할 수 있는 여러 샘플러 및 내보내기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-193">It provides multiple samplers and exporters which you can choose from.</span></span> <span data-ttu-id="f9bf4-194">사용자 지정 샘플러 및 내보내기를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-194">It allows creating a custom samplers and exporters too.</span></span>

<span data-ttu-id="f9bf4-195">OpenTelemetry는 수집된 추적 데이터를 다른 백 엔드(예: Jaeger, Zipkin, New Relic 등)로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-195">OpenTelemetry supports exporting the collected tracing data to different backends (e.g. Jaeger, Zipkin, New Relic,...etc.).</span></span> <span data-ttu-id="f9bf4-196">자세한 내용은 [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/)을 참조하고 내보내기 패키지 목록을 가져오려면 Nuget.org에서 `OpenTelemetry.Exporter.`로 시작하는 패키지를 검색하세요.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-196">Refer to [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/) for more details and search Nuget.org for packages starting with `OpenTelemetry.Exporter.` to get the exporter packages list.</span></span>

<span data-ttu-id="f9bf4-197">다음은 [OpenTelemetry-dotnet 시작](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started)에서 포팅된 샘플 코드로, 얼마나 쉽게 추적 데이터를 샘플링하여 콘솔로 내보낼 수 있는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-197">Here is sample code ported from [OpenTelemetry-dotnet getting started](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started) showing how easy it is to sample and export tracing data to the console.</span></span>

```csharp
// <copyright file="Program.cs" company="OpenTelemetry Authors">
// Copyright The OpenTelemetry Authors
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//     http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.
// </copyright>

using System.Diagnostics;
using OpenTelemetry;
using OpenTelemetry.Trace;

public class Program
{
    private static readonly ActivitySource MyActivitySource = new ActivitySource(
        "MyCompany.MyProduct.MyLibrary");

    public static void Main()
    {
        using var tracerProvider = Sdk.CreateTracerProviderBuilder()
            .SetSampler(new AlwaysOnSampler())
            .AddSource("MyCompany.MyProduct.MyLibrary")
            .AddConsoleExporter()
            .Build();

        using (var activity = MyActivitySource.StartActivity("SayHello"))
        {
            activity?.SetTag("foo", 1);
            activity?.SetTag("bar", "Hello, World!");
            activity?.SetTag("baz", new int[] { 1, 2, 3 });
        }
    }
}
```

<span data-ttu-id="f9bf4-198">이 샘플은 [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2) 패키지를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-198">The sample needs to reference the package [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2).</span></span>
