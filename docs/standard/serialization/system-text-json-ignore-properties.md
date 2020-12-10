---
title: System.Text.Json을 사용하여 속성을 무시하는 방법
description: .NET에서 System.Text.Json을 사용하여 직렬화할 때 속성을 무시하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439823"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a><span data-ttu-id="7e414-103">System.Text.Json을 사용하여 속성을 무시하는 방법</span><span class="sxs-lookup"><span data-stu-id="7e414-103">How to ignore properties with System.Text.Json</span></span>

<span data-ttu-id="7e414-104">C# 개체를 JavaScript Object Notation(JSON)으로 직렬화하면 기본적으로 모든 public 속성이 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-104">When serializing C# objects to JavaScript Object Notation (JSON), by default, all public properties are serialized.</span></span> <span data-ttu-id="7e414-105">그중 일부 속성을 결과 JSON에 표시하지 않으려는 경우 사용할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-105">If you don't want some of them to appear in the resulting JSON, you have several options.</span></span> <span data-ttu-id="7e414-106">이 문서에서는 다양한 조건을 기준으로 속성을 무시하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-106">In this article you learn how to ignore properties based on various criteria:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="7e414-107">개별 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-107">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="7e414-108">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-108">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="7e414-109">모든 Null 값 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-109">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="7e414-110">모든 기본값 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-110">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="7e414-111">개별 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-111">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="7e414-112">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-112">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="7e414-113">모든 Null 값 속성</span><span class="sxs-lookup"><span data-stu-id="7e414-113">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a><span data-ttu-id="7e414-114">개별 속성 무시</span><span class="sxs-lookup"><span data-stu-id="7e414-114">Ignore individual properties</span></span>

<span data-ttu-id="7e414-115">개별 속성을 무시하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-115">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="7e414-116">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-116">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="7e414-117">[JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 설정하여 조건부 제외를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-117">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="7e414-118"><xref:System.Text.Json.Serialization.JsonIgnoreCondition> 열거형은 다음 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-118">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="7e414-119">`Always` - 속성이 항상 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-119">`Always` - The property is always ignored.</span></span> <span data-ttu-id="7e414-120">`Condition`을 지정하지 않으면 이 옵션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-120">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="7e414-121">`Never` - `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` 및 `IgnoreReadOnlyFields` 전역 설정에 관계 없이 속성은 항상 직렬화 및 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-121">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="7e414-122">`WhenWritingDefault` - 속성이 참조 형식 `null`, null 허용 값 형식 `null` 또는 값 형식 `default`인 경우 직렬화 시 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-122">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null`, a nullable value type `null`, or a value type `default`.</span></span>
* <span data-ttu-id="7e414-123">`WhenWritingNull` - 속성이 참조 형식 `null` 또는 null 허용 값 형식 `null`인 경우 직렬화 시 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-123">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`, or a nullable value type `null`.</span></span>

<span data-ttu-id="7e414-124">다음 예는 [JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-124">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a><span data-ttu-id="7e414-125">모든 읽기 전용 속성 무시</span><span class="sxs-lookup"><span data-stu-id="7e414-125">Ignore all read-only properties</span></span>

<span data-ttu-id="7e414-126">public setter가 아닌 public getter를 포함하는 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-126">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="7e414-127">직렬화할 때 모든 읽기 전용 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-127">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

<span data-ttu-id="7e414-128">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-128">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="7e414-129">이 옵션은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-129">This option applies only to serialization.</span></span> <span data-ttu-id="7e414-130">역직렬화를 수행할 때 읽기 전용 속성은 기본적으로 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-130">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="7e414-131">이 옵션은 속성에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-131">This option applies only to properties.</span></span> <span data-ttu-id="7e414-132">[필드를 직렬화](system-text-json-how-to.md#include-fields)할 때 읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-132">To ignore read-only fields when [serializing fields](system-text-json-how-to.md#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

## <a name="ignore-all-null-value-properties"></a><span data-ttu-id="7e414-133">모든 Null 값 속성 무시</span><span class="sxs-lookup"><span data-stu-id="7e414-133">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="7e414-134">모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-134">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="7e414-135">직렬화할 때 모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-135">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

<span data-ttu-id="7e414-136">다음은 직렬화 개체 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-136">Here's an example object to serialize and JSON output:</span></span>

| <span data-ttu-id="7e414-137">속성</span><span class="sxs-lookup"><span data-stu-id="7e414-137">Property</span></span>             | <span data-ttu-id="7e414-138">값</span><span class="sxs-lookup"><span data-stu-id="7e414-138">Value</span></span>                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a><span data-ttu-id="7e414-139">모든 기본값 속성 무시</span><span class="sxs-lookup"><span data-stu-id="7e414-139">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="7e414-140">값 형식 속성에서 기본값의 직렬화를 방지하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-140">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="7e414-141"><xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> 설정은 null 값 참조 형식 및 null 허용 값 형식 속성의 직렬화도 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-141">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> setting also prevents serialization of null-value reference type and nullable value type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="7e414-142">.NET Core 3.1에서 `System.Text.Json`의 값 형식 기본값으로 속성의 직렬화를 방지하는 기본 제공 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e414-142">There is no built-in way to prevent serialization of properties with value type defaults in `System.Text.Json` in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="7e414-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e414-143">See also</span></span>

* [<span data-ttu-id="7e414-144">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="7e414-144">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="7e414-145">JsonSerializerOptions 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="7e414-145">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="7e414-146">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="7e414-146">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="7e414-147">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7e414-147">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="7e414-148">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="7e414-148">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="7e414-149">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="7e414-149">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="7e414-150">순환 참조 보존</span><span class="sxs-lookup"><span data-stu-id="7e414-150">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="7e414-151">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="7e414-151">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="7e414-152">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="7e414-152">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="7e414-153">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="7e414-153">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
