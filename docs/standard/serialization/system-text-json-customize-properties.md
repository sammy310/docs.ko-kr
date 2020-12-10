---
title: System.Text.Json으로 속성 이름 및 값을 사용자 지정하는 방법
description: .NET에서 System.Text.Json을 사용하여 직렬화할 때 속성 이름 및 값을 사용자 지정하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c754d41071e886bc1efcc3a30e249bf9e554ab5b
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599592"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a><span data-ttu-id="864a3-103">System.Text.Json으로 속성 이름 및 값을 사용자 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="864a3-103">How to customize property names and values with System.Text.Json</span></span>

<span data-ttu-id="864a3-104">기본적으로 대/소문자를 비롯한 속성 이름 및 사전 키는 JSON 출력에서 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-104">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="864a3-105">열거형 값은 숫자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-105">Enum values are represented as numbers.</span></span> <span data-ttu-id="864a3-106">이 문서에서는 다음을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-106">In this article, you'll learn how to:</span></span>

> [!NOTE]
> <span data-ttu-id="864a3-107">[웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)은 카멜식 대/소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-107">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is camel case.</span></span>

* [<span data-ttu-id="864a3-108">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="864a3-108">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="864a3-109">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="864a3-109">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="864a3-110">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="864a3-110">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="864a3-111">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="864a3-111">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="864a3-112">열거형을 문자열 및 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="864a3-112">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="864a3-113">JSON 속성 이름 및 값을 특수하게 처리해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-113">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

## <a name="customize-individual-property-names"></a><span data-ttu-id="864a3-114">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="864a3-114">Customize individual property names</span></span>

<span data-ttu-id="864a3-115">개별 속성 이름을 설정하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-115">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="864a3-116">다음은 직렬화 형식과 그 결과 JSON의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-116">Here's an example type to serialize and resulting JSON:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="864a3-117">이 특성을 통해 설정된 속성 이름은 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-117">The property name set by this attribute:</span></span>

* <span data-ttu-id="864a3-118">직렬화 및 역직렬화 양방향으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-118">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="864a3-119">속성 명명 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-119">Takes precedence over property naming policies.</span></span>

## <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="864a3-120">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="864a3-120">Use camel case for all JSON property names</span></span>

<span data-ttu-id="864a3-121">모든 JSON 속성 이름에 카멜식 대/소문자를 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>을 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-121">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

<span data-ttu-id="864a3-122">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-122">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="864a3-123">카멜식 대/소문자 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-123">The camel case property naming policy:</span></span>

* <span data-ttu-id="864a3-124">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-124">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="864a3-125">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-125">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="864a3-126">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-126">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

## <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="864a3-127">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="864a3-127">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="864a3-128">사용자 지정 JSON 속성 명명 정책을 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-128">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

<span data-ttu-id="864a3-129">그리고 다음과 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-129">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

<span data-ttu-id="864a3-130">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-130">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="864a3-131">JSON 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-131">The JSON property naming policy:</span></span>

* <span data-ttu-id="864a3-132">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-132">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="864a3-133">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-133">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="864a3-134">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 대문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-134">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

## <a name="camel-case-dictionary-keys"></a><span data-ttu-id="864a3-135">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="864a3-135">Camel case dictionary keys</span></span>

<span data-ttu-id="864a3-136">직렬화할 개체의 속성이 `Dictionary<string,TValue>` 형식이면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-136">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="864a3-137">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-137">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

<span data-ttu-id="864a3-138">키-값 쌍 `"ColdMinTemp", 20` 및 `"HotMinTemp", 40`가 있는 `TemperatureRanges`라는 사전이 포함된 개체를 직렬화하면 다음 예제와 같은 JSON 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-138">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="864a3-139">사전 키에 대한 카멜식 대/소문자 명명 정책은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-139">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="864a3-140">사전을 역직렬화하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase`를 지정하더라도 키가 JSON 파일과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-140">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

## <a name="enums-as-strings"></a><span data-ttu-id="864a3-141">문자열인 열거형</span><span class="sxs-lookup"><span data-stu-id="864a3-141">Enums as strings</span></span>

<span data-ttu-id="864a3-142">기본적으로 열거형은 숫자로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-142">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="864a3-143">열거형 이름을 문자열로 직렬화하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-143">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="864a3-144">예를 들어 열거형을 포함하는 다음 클래스를 직렬화해야 한다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="864a3-144">For example, suppose you need to serialize the following class that has an enum:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

<span data-ttu-id="864a3-145">Summary가 `Hot`이면 기본적으로 직렬화된 JSON은 다음과 같이 숫자 값 3을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-145">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="864a3-146">다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화하고, 이름을 카멜식 대/소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-146">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

<span data-ttu-id="864a3-147">그 결과로 얻는 JSON은 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-147">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="864a3-148">다음 예제와 같이 열거형 문자열 이름도 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="864a3-148">Enum string names can be deserialized as well, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a><span data-ttu-id="864a3-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="864a3-149">See also</span></span>

* [<span data-ttu-id="864a3-150">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="864a3-150">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="864a3-151">JsonSerializerOptions 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="864a3-151">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="864a3-152">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="864a3-152">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="864a3-153">속성 무시</span><span class="sxs-lookup"><span data-stu-id="864a3-153">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="864a3-154">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="864a3-154">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="864a3-155">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="864a3-155">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="864a3-156">순환 참조 보존</span><span class="sxs-lookup"><span data-stu-id="864a3-156">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="864a3-157">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="864a3-157">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="864a3-158">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="864a3-158">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="864a3-159">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="864a3-159">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
