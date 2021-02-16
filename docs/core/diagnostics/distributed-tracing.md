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
# <a name="net-distributed-tracing"></a>.NET 분산 추적

분산 추적은 분산 시스템에서 추적 데이터를 게시하고 관찰하는 방법입니다.
.NET Framework 및 .NET Core는 <xref:System.Diagnostics> API를 통해 추적을 지원해 왔습니다.

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType> 클래스 - 진단 컨텍스트를 저장 및 액세스하고 로깅 시스템에서 사용할 수 있습니다.
- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType> - 계측된 프로세스 내에서 사용하기 위한 다양한 데이터 페이로드의 프로덕션 시간 로깅에 대한 코드를 계측할 수 있습니다.

다음은 HTTP 수신 요청에서 추적 데이터를 게시하는 방법을 보여 주는 예제입니다.

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

다음은 활동 이벤트를 수신 대기하는 방법의 예제입니다.

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

.NET 5.0에서는 [OpenTelemetry](https://opentelemetry.io/) 추적 시나리오가 가능하도록 분산 추적의 기능이 확장되고, 샘플링 기능이 추가되고, 추적 코딩 패턴이 간소화되고, 활동 이벤트 수신 대기가 더 쉽고 유연해졌습니다.

> [!NOTE]
> 추가된 모든 .NET 5.0 기능에 액세스하려면 프로젝트가 [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/) NuGet 패키지 버전 5.0 이상을 참조해야 합니다. 이 패키지는 지원되는 버전의 .NET Framework, .NET Core 및 .NET Standard를 대상으로 하는 라이브러리 및 앱에서 사용할 수 있습니다. .NET 5.0 이상을 대상으로 하는 경우 .NET 런타임과 함께 설치된 공유 라이브러리에 패키지가 포함되어 있으므로 수동으로 패키지를 참조할 필요가 없습니다.

## <a name="getting-started-with-tracing"></a>추적 시작

애플리케이션 및 라이브러리는 단순히 <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Activity?displayProperty=nameWithType> 클래스를 사용하여 쉽게 추적 데이터를 게시할 수 있습니다.

### <a name="activitysource"></a>ActivitySource

추적 데이터를 게시하는 첫 번째 단계는 ActivitySource 클래스의 인스턴스를 만드는 것입니다. ActivitySource는 활동 개체를 만들고 시작하는 API와 활동 이벤트를 수신 대기하기 위해 ActivityListener 개체를 등록하는 API를 제공하는 클래스입니다.

```csharp
    private static ActivitySource source = new ActivitySource("MyCompany.MyComponent.SourceName", "v1");
```

#### <a name="best-practices"></a>모범 사례

- ActivitySource를 한 번 만들어 정적 변수에 저장하고 필요에 따라 해당 인스턴스를 사용합니다.

- 생성자에 전달된 소스 이름은 다른 소스와의 충돌을 방지하기 위해 고유해야 합니다. 회사 이름, 구성 요소 이름, 소스 이름이 포함된 계층 이름을 사용하는 것이 좋습니다. 예들 들어 `Microsoft.System.HttpClient.HttpInOutRequests`입니다.

- 버전 매개 변수는 선택 사항입니다. 여러 버전의 라이브러리 또는 애플리케이션을 릴리스하고 각 버전의 소스를 구분하려는 경우 버전을 제공하는 것이 좋습니다.

### <a name="activity-creation"></a>활동 만들기

이제 만든 ActivitySource 개체를 사용하여 코드의 원하는 위치에서 추적 데이터를 기록하는 데 사용되는 활동 개체를 만들고 시작할 수 있습니다.

```csharp
        using (Activity activity = source.StartActivity("OperationName"))
        {
            // Do something

            activity?.AddTag("key", "value"); // log the tracing
        }
```

다음 샘플 코드는 활동 개체를 만든 다음 추적 태그 `key` 및 `value`를 기록하려고 시도합니다.

#### <a name="notes"></a>참고

- `ActivitySource.StartActivity`는 활동을 만드는 동시에 시작하려고 시도합니다. 나열된 코드 패턴에서는 블록을 실행한 후 만든 활동 개체를 자동으로 삭제하는 `using` 블록을 사용합니다. 활동 개체를 삭제하면 이 시작된 활동이 중지되며 코드에서 명시적으로 활동을 중지할 필요가 없습니다. 그러면 코딩 패턴이 단순해집니다.

- `ActivitySource.StartActivity`는 내부적으로 해당 이벤트에 대한 수신기가 있는지 확인합니다. 등록된 수신기가 없거나 해당 이벤트에 관심이 없는 수신기가 있는 경우 `ActivitySource.StartActivity`는 단순히 `null`을 반환하고 활동 개체를 만들지 않도록 합니다. 이 때문에 코드에서 문 `activity?.AddTag`에 null 허용 연산자 `?`를 사용하는 것입니다. 일반적으로 `using` 블록 내에서 항상 활동 개체 이름 뒤에 null 허용 연산자 `?`를 사용합니다.

## <a name="listening-to-the-activity-events"></a>활동 이벤트 수신 대기

.NET에서는 하나 이상의 ActivitySource에서 트리거된 활동 이벤트를 수신 대기하는 데 사용할 수 있는 클래스 <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType>을 제공합니다.
이 수신기를 사용하여 추적 데이터를 수집하거나, 샘플을 만들거나, 활동 개체를 강제로 만들 수 있습니다.

`ActivityListener` 클래스는 서로 다른 이벤트를 처리하는 다양한 콜백을 제공합니다.

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

- `ShouldListenTo`를 사용하면 특정 `ActivitySource` 개체를 수신 대기할 수 있습니다. 이 예제에서는 이전에 만든 `ActivitySource` 개체를 수신 대기합니다. 추가로 입력 `ActivitySource`의 `Name` 및 `Version`을 확인하여 다른 `ActivitySource` 개체를 수신 대기할 수 있는 유연성이 있습니다.

- `ActivityStarted` 및 `ActivityStopped`를 사용하면 `ShouldListenTo` 콜백에서 활성화된 `ActivitySource` 개체가 생성한 모든 `Activity` 개체에 대해 `Activity` 시작 및 중지 이벤트를 가져올 수 있습니다.

- `Sample` 및 `SampleUsingParentId`는 샘플링을 위한 기본 콜백입니다. 이러한 두 콜백은 `ActivitySamplingResult` 열거형 값을 반환합니다. 이 값은 현재 `Activity` 만들기 요청을 샘플링 또는 제외하도록 지시할 수 있습니다. 콜백이 `ActivitySamplingResult.None`을 반환하고 다른 활성화된 수신기가 다른 값을 반환하지 않는 경우 활동이 생성되지 않으며 `ActivitySource.StartActivity`가 `null`을 반환합니다. 그렇지 않으면 `Activity` 개체가 생성됩니다.

## <a name="net-50-new-features"></a>.NET 5.0 새로운 기능

`Activity` 클래스는 추적 시나리오를 지원해 왔습니다. 이 클래스를 사용하여 추적 데이터의 키-값 쌍인 태그를 추가할 수 있었습니다. 또한 네트워크를 통해 전파하기 위한 키-값 쌍인 Baggage를 지원해 왔습니다.

.NET 5.0은 주로 OpenTelemetry 시나리오를 구현하기 위한 더 많은 기능을 지원합니다.

### <a name="activitycontext"></a>ActivityContext

<xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType>는 추적 작업의 컨텍스트를 전달하는 구조체입니다(예: 추적 ID, 범위 ID, 추적 플래그, 추적 상태). 이제 부모 추적 컨텍스트를 제공하는 새 `Activity`를 만들 수 있습니다. 또한 `Activity.Context` 속성을 호출하여 `Activity` 개체에서 추적 컨텍스트를 쉽게 추출할 수 있습니다.

### <a name="activitylink"></a>ActivityLink

<xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType>는 관련된 `Activity` 개체에 연결될 수 있는 추적 컨텍스트 인스턴스를 포함하는 구조체입니다. `Activity`를 만들 때 링크 목록을 `ActivitySource.StartActivity` 메서드로 전달하여 `Activity` 개체에 링크를 추가할 수 있습니다. `Activity.Links` 속성을 사용하여 개체 연결 링크 `Activity`를 검색할 수 있습니다.

### <a name="activityevent"></a>ActivityEvent

<xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType>는 이름 및 타임스탬프를 포함하는 이벤트와 선택적 태그 목록을 나타냅니다. `Activity.AddEvent` 메서드를 호출하여 `Activity` 개체에 이벤트를 추가할 수 있습니다. `Activity` 개체 이벤트의 전체 목록은 `Activity.Events` 속성을 사용하여 검색할 수 있습니다.

### <a name="activitykind"></a>ActivityKind

<xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType>는 추적의 활동, 부모 및 자식 간의 관계를 설명합니다. `Activity`를 만들 때 종류 값을 `ActivitySource.StartActivity` 메서드에 전달하여 `Activity` 개체에 종류를 설정할 수 있습니다. `Activity.Kind` 속성을 사용하여 `Activity` 개체 종류를 검색할 수 있습니다.

### <a name="isalldatarequested"></a>IsAllDataRequested

<xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType>는 이 활동을 모든 전파 정보뿐만 아니라 링크, 태그 및 이벤트와 같은 다른 모든 속성으로 채워야 하는지 여부를 나타냅니다. `IsAllDataRequested`의 값은 모든 수신기 `Sample` 및 `SampleUsingParentId` 콜백에서 반환된 결과로부터 결정됩니다. `Activity.IsAllDataRequested` 속성을 사용하여 값을 검색할 수 있습니다.

### <a name="activitysource"></a>Activity.Source

<xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType>는 이 활동과 연결된 활동 소스를 가져옵니다.

### <a name="activitydisplayname"></a>Activity.DisplayName

<xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType>를 사용하면 활동의 표시 이름을 가져오거나 설정할 수 있습니다.

### <a name="activitytagobjects"></a>Activity.TagObjects

`Activity` 클래스에는 키 및 값에 대한 문자열 형식 태그의 키-값 쌍 목록을 반환하는 `Activity.Tags` 속성이 있습니다. 이러한 태그는 `AddTag(string, string)` 메서드를 사용하여 `Activity`에 추가할 수 있습니다. `Activity`는 모든 형식의 값을 허용하는 오버로드된 메서드 `AddTag(string, object)`를 제공하여 태그 지원을 확장했습니다.  이러한 태그의 전체 목록은 <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>를 사용하여 검색할 수 있습니다.

## <a name="sampling"></a>샘플링

샘플링은 수집되고 백 엔드로 전송되는 추적 샘플 수를 줄임으로써 노이즈 및 오버헤드를 제어하는 메커니즘입니다. 샘플링은 중요한 OpenTelemetry 시나리오입니다. .NET 5.0에서는 샘플링을 쉽게 수행할 수 있습니다. 이 메서드를 호출하는 경우 `ActivitySource.StartActivity`를 사용하여 새 `Activity` 개체를 만들고 사용 가능한 모든 데이터(예: 태그, 종류, 링크 등)를 제공하는 것이 좋습니다. 데이터를 제공하면 `ActivityListener`를 사용하여 구현된 샘플러가 적절한 샘플링 결정을 수행할 수 있습니다. `Activity` 개체를 만들기 전에 데이터가 생성되는 것을 방지하기 위해 성능이 중요한 경우 `ActivitySource.HasListeners` 속성은 필요한 데이터를 만들기 전에 수신기가 있는지 확인하는 데 유용합니다.

## <a name="opentelemetry"></a>OpenTelemetry

OpenTelemetry SDK에는 엔드투엔드 분산 추적 시나리오를 지원하는 다양한 기능이 함께 제공됩니다. 선택할 수 있는 여러 샘플러 및 내보내기를 제공합니다. 사용자 지정 샘플러 및 내보내기를 만들 수도 있습니다.

OpenTelemetry는 수집된 추적 데이터를 다른 백 엔드(예: Jaeger, Zipkin, New Relic 등)로 내보낼 수 있습니다. 자세한 내용은 [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/)을 참조하고 내보내기 패키지 목록을 가져오려면 Nuget.org에서 `OpenTelemetry.Exporter.`로 시작하는 패키지를 검색하세요.

다음은 [OpenTelemetry-dotnet 시작](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started)에서 포팅된 샘플 코드로, 얼마나 쉽게 추적 데이터를 샘플링하여 콘솔로 내보낼 수 있는지 보여 줍니다.

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

이 샘플은 [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2) 패키지를 참조해야 합니다.
