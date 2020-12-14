---
title: System.Text.Json을 사용하여 JsonSerializerOptions를 인스턴스화하는 방법
description: 성능 문제를 방지하는 방법과 JsonSerializerOptions 인스턴스에 대해 사용 가능한 생성자를 사용하는 방법을 알아봅니다.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009835"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="0c07a-103">System.Text.Json을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법</span><span class="sxs-lookup"><span data-stu-id="0c07a-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="0c07a-104">이 문서에서는 <xref:System.Text.Json.JsonSerializerOptions>를 사용하는 경우 성능 문제를 방지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-104">This article explains how to avoid performance problems when you use <xref:System.Text.Json.JsonSerializerOptions>.</span></span> <span data-ttu-id="0c07a-105">또한 사용할 수 있는 매개 변수가 있는 생성자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-105">It also shows how to use the parameterized constructors that are available.</span></span>

## <a name="reuse-jsonserializeroptions-instances"></a><span data-ttu-id="0c07a-106">JsonSerializerOptions 인스턴스 다시 사용</span><span class="sxs-lookup"><span data-stu-id="0c07a-106">Reuse JsonSerializerOptions instances</span></span>

<span data-ttu-id="0c07a-107">동일한 옵션으로 `JsonSerializerOptions`를 반복적으로 사용하는 경우 사용할 때마다 새 `JsonSerializerOptions` 인스턴스를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0c07a-107">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="0c07a-108">모든 호출에 대해 동일한 인스턴스를 다시 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0c07a-108">Reuse the same instance for every call.</span></span> <span data-ttu-id="0c07a-109">이 지침은 사용자 지정 변환기에 대해 작성하는 코드와 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 또는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>을 호출할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-109">This guidance applies to code you write for custom converters and when you call <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0c07a-110">다음 코드에서는 새 옵션 인스턴스를 사용하는 경우의 성능 저하를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-110">The following code demonstrates the performance penalty for using new options instances.</span></span>

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

<span data-ttu-id="0c07a-111">위의 코드는 동일한 옵션 인스턴스를 사용하여 작은 개체를 100,000번 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-111">The preceding code serializes a small object 100,000 times using the same options instance.</span></span> <span data-ttu-id="0c07a-112">그런 다음, 동일한 개체를 동일한 횟수만큼 직렬화하고 매번 새 옵션 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-112">Then it serializes the same object the same number of times and creates a new options instance each time.</span></span> <span data-ttu-id="0c07a-113">일반적인 런타임 차이는 40,140밀리초와 비교할 때 190입니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-113">A typical run time difference is 190 compared to 40,140 milliseconds.</span></span> <span data-ttu-id="0c07a-114">반복 횟수를 늘리면 차이가 훨씬 커집니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-114">The difference is even greater if you increase the number of iterations.</span></span>

<span data-ttu-id="0c07a-115">직렬 변환기는 새 옵션 인스턴스가 전달될 때 개체 그래프의 각 형식의 첫 번째 serialization 동안 준비 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-115">The serializer undergoes a warm-up phase during the first serialization of each type in the object graph when a new options instance is passed to it.</span></span> <span data-ttu-id="0c07a-116">이 준비에는 serialization에 필요한 메타데이터의 캐시를 만드는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-116">This warm-up includes creating a cache of metadata that is needed for serialization.</span></span> <span data-ttu-id="0c07a-117">메타데이터에는 getter 및 setter 속성, 생성자 인수, 지정된 특성 등에 대한 대리자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-117">The metadata includes delegates to property getters, setters, constructor arguments, specified attributes, and so forth.</span></span> <span data-ttu-id="0c07a-118">이 메타데이터 캐시는 옵션 인스턴스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-118">This metadata cache is stored in the options instance.</span></span> <span data-ttu-id="0c07a-119">동일한 준비 프로세스 및 캐시가 deserialization에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-119">The same warm-up process and cache applies to deserialization.</span></span>

<span data-ttu-id="0c07a-120">`JsonSerializerOptions` 인스턴스의 메타데이터 캐시 크기는 직렬화되는 형식 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-120">The size of the metadata cache in a `JsonSerializerOptions` instance depends on the number of types to be serialized.</span></span> <span data-ttu-id="0c07a-121">여러 형식(예: 동적으로 생성된 형식)을 직렬 변환기에 전달하는 경우 캐시 크기가 계속 커지고 결국 `OutOfMemoryException`이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-121">If you pass numerous types—for example, dynamically generated types—to the serializer, the cache size will continue to grow and can end up causing an `OutOfMemoryException`.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="0c07a-122">JsonSerializerOptions 복사</span><span class="sxs-lookup"><span data-stu-id="0c07a-122">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0c07a-123">다음 예제와 같이 기존 인스턴스와 동일한 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions))이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-123">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0c07a-124">기존 인스턴스를 사용하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-124">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="0c07a-125">JsonSerializerOptions의 웹 기본값</span><span class="sxs-lookup"><span data-stu-id="0c07a-125">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0c07a-126">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-126">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="0c07a-127">다음 예제와 같이 ASP.NET Core가 웹앱에 사용하는 기본 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-127">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0c07a-128">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-128">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="0c07a-129">기본값 집합을 지정하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c07a-129">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="0c07a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c07a-130">See also</span></span>

* [<span data-ttu-id="0c07a-131">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="0c07a-131">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0c07a-132">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="0c07a-132">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="0c07a-133">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="0c07a-133">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="0c07a-134">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0c07a-134">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0c07a-135">속성 무시</span><span class="sxs-lookup"><span data-stu-id="0c07a-135">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0c07a-136">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="0c07a-136">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0c07a-137">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="0c07a-137">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0c07a-138">참조 유지</span><span class="sxs-lookup"><span data-stu-id="0c07a-138">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0c07a-139">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="0c07a-139">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="0c07a-140">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="0c07a-140">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="0c07a-141">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0c07a-141">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="0c07a-142">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0c07a-142">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="0c07a-143">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="0c07a-143">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="0c07a-144">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="0c07a-144">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="0c07a-145">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="0c07a-145">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="0c07a-146">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0c07a-146">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="0c07a-147">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="0c07a-147">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
