---
title: '호환성이 손상되는 변경: ASP.NET Core 앱은 따옴표 붙은 숫자를 역직렬화할 수 있음'
description: ASP.NET Core 앱이 예외를 throw하는 대신 JSON 문자열로 표현되는 숫자를 역직렬화하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/21/2020
ms.openlocfilehash: f541af5bf5f0a519fd5205f44d68a9b401569909
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256311"
---
# <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="3436e-103">ASP.NET Core 앱은 따옴표 붙은 숫자를 역직렬화할 수 있음</span><span class="sxs-lookup"><span data-stu-id="3436e-103">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="3436e-104">.NET 5부터 ASP.NET Core 앱은 <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>에 지정된 대로 기본 deserialization 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-104">Starting in .NET 5, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3436e-105">옵션의 <xref:System.Text.Json.JsonSerializerDefaults.Web> 집합에는 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling>을 <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>으로 설정하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-105">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3436e-106">이 변경 내용은 ASP.NET Core 앱이 예외를 throw하는 대신 JSON 문자열로 표현되는 숫자를 역직렬화함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-106">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings instead of throwing an exception.</span></span>

## <a name="change-description"></a><span data-ttu-id="3436e-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3436e-107">Change description</span></span>

<span data-ttu-id="3436e-108">.NET Core 3.0 - 3.1에서는 JSON 페이로드에 따옴표 붙은 숫자가 있는 경우 <xref:System.Text.Json.JsonSerializer>에서 deserialization 중에 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-108">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="3436e-109">따옴표 붙은 숫자는 개체 그래프의 숫자 속성으로 매핑하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-109">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="3436e-110">.NET Core 3.0 - 3.1에서 숫자는 <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> 토큰에서만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-110">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="3436e-111">.NET 5부터 JSON 페이로드의 따옴표 붙은 숫자는 기본적으로 ASP.NET Core 앱에 유효한 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-111">Starting in .NET 5, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="3436e-112">따옴표 붙은 숫자 deserialization 중에는 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-112">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="3436e-113">기본, 독립 실행형 <xref:System.Text.Json.JsonSerializer> 또는 <xref:System.Text.Json.JsonSerializerOptions>에 대한 동작은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-113">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="3436e-114">기술적으로는 더욱 제한적이기보다는 더욱 허용하는 시나리오를 만들기 때문에 호환성이 손상되는 변경이 아닙니다. 즉, 예외를 throw하는 대신 JSON 문자열에서 숫자를 강제 변환하는 데 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-114">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="3436e-115">그러나 ASP.NET Core 앱에 영향을 주는 중요한 동작 변경 사항이기 때문에 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-115">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="3436e-116"><xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> 확장 메서드도 serialization 옵션의 <xref:System.Text.Json.JsonSerializerDefaults.Web> 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-116">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="3436e-117">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3436e-117">Version introduced</span></span>

<span data-ttu-id="3436e-118">5.0</span><span class="sxs-lookup"><span data-stu-id="3436e-118">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="3436e-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3436e-119">Reason for change</span></span>

<span data-ttu-id="3436e-120">여러 사용자가 <xref:System.Text.Json.JsonSerializer>에서 더욱 허용적인 숫자 처리에 대한 옵션을 요청했습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-120">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="3436e-121">이 피드백은 많은 JSON 생산자(예: 웹의 서비스)가 따옴표 붙은 숫자를 내보냄을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-121">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="3436e-122">따옴표 붙은 숫자를 읽을 수 있도록 역직렬화하면 .NET 앱은 기본적으로 웹 컨텐스트에서 이러한 페이로드를 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-122">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="3436e-123">클라이언트, 서버 및 공유와 같이 여러 애플리케이션 계층에서 동일한 옵션을 지정할 수 있도록 <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>을 통해 구성이 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-123">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3436e-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3436e-124">Recommended action</span></span>

<span data-ttu-id="3436e-125">예를 들어 유효성 검사를 위해 엄격한 숫자 처리를 사용하는 경우처럼 이러한 변경이 중단되면 이전 동작을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-125">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="3436e-126"><xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> 옵션을 <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="3436e-126">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3436e-127">ASP.NET Core MVC 및 웹 API 앱의 경우 다음 코드를 사용하여 `Startup`에서 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3436e-127">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

## <a name="affected-apis"></a><span data-ttu-id="3436e-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3436e-128">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

- ASP.NET Core
- Serialization

-->
