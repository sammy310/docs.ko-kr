---
title: System.Text.Json을 사용하여 파생 클래스의 속성을 직렬화하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬할 때 다형 개체를 직렬화하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c0bc16c60d3bf96a380bc29bbf7f4765f752b320
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008749"
---
# <a name="how-to-serialize-properties-of-derived-classes-with-no-locsystemtextjson"></a><span data-ttu-id="d8909-103">System.Text.Json을 사용하여 파생 클래스의 속성을 직렬화하는 방법</span><span class="sxs-lookup"><span data-stu-id="d8909-103">How to serialize properties of derived classes with System.Text.Json</span></span>

<span data-ttu-id="d8909-104">이 문서에서는 `System.Text.Json` 네임스페이스를 사용하여 파생 클래스의 속성을 직렬화하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-104">In this article, you will learn how to serialize properties of derived classes with the `System.Text.Json` namespace.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="d8909-105">파생 클래스의 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="d8909-105">Serialize properties of derived classes</span></span>

<span data-ttu-id="d8909-106">다형 형식 계층 구조의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-106">Serialization of a polymorphic type hierarchy is _not_ supported.</span></span> <span data-ttu-id="d8909-107">예를 들어 속성이 인터페이스 또는 추상 클래스로 정의된 경우에는 런타임 형식에 추가 속성이 있더라도 인터페이스 또는 추상 클래스에 정의된 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-107">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="d8909-108">이 동작의 예외는 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-108">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="d8909-109">예를 들어 `WeatherForecast` 클래스와 `WeatherForecastDerived` 파생 클래스가 있다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="d8909-109">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFDerived":::

<span data-ttu-id="d8909-110">그리고 컴파일 시간에 `Serialize` 메서드의 형식 인수가 `WeatherForecast`라고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-110">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeDefault":::

<span data-ttu-id="d8909-111">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastDerived` 개체인 경우에도 `WindSpeed` 속성이 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-111">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="d8909-112">기본 클래스 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-112">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="d8909-113">이 동작의 목적은 파생된 런타임 생성 형식에서 실수로 데이터가 노출되는 것을 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-113">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="d8909-114">이전 예제의 파생 형식 속성을 직렬화하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-114">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="d8909-115">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-115">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeGetType":::

* <span data-ttu-id="d8909-116">`object`로 직렬화할 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-116">Declare the object to be serialized as `object`.</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeObject":::

<span data-ttu-id="d8909-117">위의 예제 시나리오에서 두 방법 모두 다음과 같이 `WindSpeed` 속성이 JSON 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-117">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="d8909-118">이러한 접근 방식은 루트 개체의 속성이 아니라 직렬화할 루트 개체에 대해서만 다형 직렬화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-118">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="d8909-119">`object` 형식으로 정의하면 하위 수준 개체에 대한 다형 직렬화를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-119">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="d8909-120">예를 들어 `WeatherForecast` 클래스에 `WeatherForecast` 또는 `object` 형식으로 정의할 수 있는 `PreviousForecast`라는 속성이 있다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-120">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPrevious":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPreviousAsObject":::

<span data-ttu-id="d8909-121">이 `PreviousForecast` 속성은 다음과 같이 `WeatherForecastDerived` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-121">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="d8909-122">`WeatherForecastWithPrevious` 직렬화의 JSON 출력에는 `WindSpeed`가 포함되지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="d8909-122">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="d8909-123">`WeatherForecastWithPreviousAsObject` 직렬화의 JSON 출력에는 `WindSpeed`가 포함 **됩니다**.</span><span class="sxs-lookup"><span data-stu-id="d8909-123">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="d8909-124">루트 개체가 파생 형식이 아닐 수도 있으므로 `WeatherForecastWithPreviousAsObject`를 직렬화하기 위해 `Serialize<object>` 또는 `GetType`을 반드시 호출해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-124">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="d8909-125">예를 들어 다음 코드 예제는 `Serialize<object>` 또는 `GetType`을 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-125">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeSecondLevel":::

<span data-ttu-id="d8909-126">이전 코드는 다음과 같이 `WeatherForecastWithPreviousAsObject`를 올바르게 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-126">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="d8909-127">속성을 `object`로 정의하는 동일한 방법이 인터페이스에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-127">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="d8909-128">다음과 같은 인터페이스 및 구현이 있고, 구현 인스턴스가 포함된 속성을 사용하여 클래스를 직렬화하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-128">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/IForecast.cs":::

<span data-ttu-id="d8909-129">`Forecasts`의 인스턴스를 직렬화할 경우 `Tuesday`가 `object`로 정의되어 있으므로 `Tuesday`만 `WindSpeed` 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-129">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeInterface":::

<span data-ttu-id="d8909-130">다음 예제에서는 이전 코드의 결과로 생성되는 JSON을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8909-130">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="d8909-131">다형 **serialization** 및 **deserialization** 에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8909-131">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8909-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8909-132">See also</span></span>

* [<span data-ttu-id="d8909-133">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="d8909-133">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="d8909-134">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="d8909-134">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="d8909-135">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="d8909-135">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="d8909-136">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d8909-136">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="d8909-137">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d8909-137">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="d8909-138">속성 무시</span><span class="sxs-lookup"><span data-stu-id="d8909-138">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="d8909-139">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="d8909-139">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="d8909-140">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="d8909-140">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="d8909-141">참조 유지</span><span class="sxs-lookup"><span data-stu-id="d8909-141">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="d8909-142">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="d8909-142">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="d8909-143">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d8909-143">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="d8909-144">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d8909-144">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="d8909-145">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="d8909-145">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="d8909-146">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="d8909-146">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="d8909-147">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="d8909-147">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="d8909-148">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d8909-148">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="d8909-149">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="d8909-149">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
