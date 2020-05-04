---
title: JSON serialization용 사용자 지정 변환기를 작성하는 방법 - .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159574"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="f9ce5-102">.NET에서 JSON serialization(마샬링)용 사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="f9ce5-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="f9ce5-103">이 문서에서는 <xref:[!OP.NO-LOC(System.Text.Json)]> 네임스페이스에 제공된 JSON serialization 클래스에 대한 사용자 지정 변환기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="f9ce5-104">`[!OP.NO-LOC(System.Text.Json)]`에 대한 소개는 [.NET에서 JSON을 직렬화 및 역직렬화하는 방법](system-text-json-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="f9ce5-105">*변환기*는 개체 또는 값을 JSON으로 변환하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="f9ce5-106">`[!OP.NO-LOC(System.Text.Json)]` 네임스페이스에는 JavaScript 기본 형식에 매핑되는 기본 형식 대부분에 대한 기본 제공 변환기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="f9ce5-107">다음과 같은 용도로 사용자 지정 변환기를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-107">You can write custom converters:</span></span>

* <span data-ttu-id="f9ce5-108">기본 제공 변환기의 기본 동작을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="f9ce5-109">예를 들어 `DateTime` 값을 기본 ISO 8601-1:2019 형식 대신 mm/dd/yyyy 형식으로 표시하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="f9ce5-110">사용자 지정 값 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-110">To support a custom value type.</span></span> <span data-ttu-id="f9ce5-111">예를 들어 `PhoneNumber` 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="f9ce5-112">현재 릴리스에 포함되지 않은 기능을 사용하여 `[!OP.NO-LOC(System.Text.Json)]`를 사용자 지정하거나 확장하는 사용자 지정 변환기를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="f9ce5-113">이 문서의 뒷부분에서 다음과 같은 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="f9ce5-114">[유추된 형식을 개체 속성으로 역직렬화](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="f9ce5-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="f9ce5-115">[문자열이 아닌 키를 사용하는 사전 지원](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="f9ce5-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="f9ce5-116">[다형 deserialization 지원](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="f9ce5-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="f9ce5-117">사용자 지정 변환기 패턴</span><span class="sxs-lookup"><span data-stu-id="f9ce5-117">Custom converter patterns</span></span>

<span data-ttu-id="f9ce5-118">사용자 지정 변환기를 만드는 데는 기본 패턴과 팩터리 패턴의 두 가지 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="f9ce5-119">팩터리 패턴은 `Enum` 형식 또는 개방형 제네릭을 처리하는 변환기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="f9ce5-120">기본 패턴은 제네릭이 아닌 형식과 폐쇄형 제네릭 형식을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="f9ce5-121">예를 들어 다음 형식의 변환기에는 팩터리 패턴이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="f9ce5-122">기본 패턴으로 처리할 수 있는 형식의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="f9ce5-123">기본 패턴은 한 형식을 처리할 수 있는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="f9ce5-124">팩터리 패턴은 런타임에 특정 형식이 필요한지 여부를 결정하는 클래스를 만들고 적절한 변환기를 동적으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="f9ce5-125">샘플 기본 변환기</span><span class="sxs-lookup"><span data-stu-id="f9ce5-125">Sample basic converter</span></span>

<span data-ttu-id="f9ce5-126">다음 샘플은 기존 데이터 형식에 대한 기본 serialization을 재정의하는 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="f9ce5-127">변환기는 `DateTimeOffset` 속성에 mm/dd/yyyy 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="f9ce5-128">샘플 팩터리 패턴 변환기</span><span class="sxs-lookup"><span data-stu-id="f9ce5-128">Sample factory pattern converter</span></span>

<span data-ttu-id="f9ce5-129">다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동하는 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="f9ce5-130">첫 번째 제네릭 형식 매개 변수가 `Enum`이고 두 번째는 개방형이기 때문에 이 코드는 팩터리 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="f9ce5-131">`CanConvert` 메서드는 두 개의 제네릭 매개 변수(이 중 첫 번째는 `Enum` 형식)가 있는 `Dictionary`에 대해서만 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="f9ce5-132">내부 변환기는 런타임에 `TValue`에 제공되는 형식을 처리하기 위해 기존 변환기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="f9ce5-133">위의 코드는 이 문서의 뒷부분에 나오는 [문자열이 아닌 키를 사용하는 사전 지원](#support-dictionary-with-non-string-key)에서 보여 주는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="f9ce5-134">기본 패턴을 따르기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="f9ce5-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="f9ce5-135">다음 단계에서는 기본 패턴을 따라 변환기를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="f9ce5-136"><xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601>에서 파생되는 클래스를 만듭니다. 여기서 `T`는 직렬화 및 역직렬화할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="f9ce5-137">들어오는 JSON을 역직렬화하고 `T` 형식으로 변환하도록 `Read` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="f9ce5-138">메서드에 전달된 <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader>를 사용하여 JSON을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="f9ce5-139">들어오는 `T` 형식의 개체를 직렬화하도록 `Write` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="f9ce5-140">메서드에 전달된 <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter>를 사용하여 JSON을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="f9ce5-141">필요한 경우에만 `CanConvert` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="f9ce5-142">기본 구현은 변환할 형식이 `T` 형식일 때 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="f9ce5-143">따라서 `T` 형식만 지원하는 변환기는 이 메서드를 재정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="f9ce5-144">이 메서드를 재정의해야 하는 변환기의 예제는 이 문서의 뒷부분에 나오는 [다형 deserialization](#support-polymorphic-deserialization) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="f9ce5-145">사용자 지정 변환기 작성을 위한 참조 구현으로 [기본 제공 변환기 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="f9ce5-146">팩터리 패턴을 따르기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="f9ce5-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="f9ce5-147">다음 단계에서는 팩터리 패턴을 따라 변환기를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="f9ce5-148"><xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="f9ce5-149">변환할 형식이 변환기에서 처리할 수 있는 형식인 경우 true를 반환하도록 `CanConvert` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="f9ce5-150">예를 들어 `List<T>`에 대한 변환기인 경우 `List<int>`, `List<string>` 및 `List<DateTime>`만 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="f9ce5-151">런타임에 제공되는 변환할 형식을 처리할 변환기 클래스 인스턴스를 반환하도록 `CreateConverter` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="f9ce5-152">`CreateConverter` 메서드가 인스턴스화하는 변환기 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="f9ce5-153">개체와 문자열 간에 변환하는 코드가 모든 형식에 대해 동일하지 않기 때문에 개방형 제네릭에는 팩터리 패턴이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="f9ce5-154">개방형 제네릭 형식(예: `List<T>`)에 대한 변환기는 백그라운드에서 폐쇄형 제네릭 형식(예: `List<DateTime>`)에 대한 변환기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="f9ce5-155">변환기가 처리할 수 있는 각 폐쇄형 제네릭 형식을 처리하기 위해 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="f9ce5-156">`Enum` 형식은 개방형 제네릭 형식과 유사합니다. `Enum`에 대한 변환기는 내부적으로 특정 `Enum`(예: `WeekdaysEnum`)에 대한 변환기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="f9ce5-157">오류 처리</span><span class="sxs-lookup"><span data-stu-id="f9ce5-157">Error handling</span></span>

<span data-ttu-id="f9ce5-158">오류 처리 코드에서 예외를 throw해야 하는 경우에는 메시지 없이 <xref:[!OP.NO-LOC(System.Text.Json)].JsonException>을 throw하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="f9ce5-159">이 예외 형식은 JSON에서 오류를 발생시킨 부분의 경로를 포함하는 메시지를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="f9ce5-160">예를 들어 `throw new JsonException();` 문은 다음 예제와 같은 오류 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="f9ce5-161">메시지(예: `throw new JsonException("Error occurred")`)를 제공하는 경우에도 예외는 <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> 속성에서 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="f9ce5-162">사용자 지정 변환기 등록</span><span class="sxs-lookup"><span data-stu-id="f9ce5-162">Register a custom converter</span></span>

<span data-ttu-id="f9ce5-163">`Serialize` 및 `Deserialize` 메서드가 사용할 수 있도록 사용자 지정 변환기를 *등록*합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="f9ce5-164">다음 방법 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="f9ce5-165"><xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> 컬렉션에 변환기 클래스의 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="f9ce5-166">[[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) 특성을 사용자 지정 변환기가 필요한 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="f9ce5-167">[[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) 특성을 사용자 지정 값 형식을 나타내는 클래스 또는 구조체에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="f9ce5-168">등록 샘플 - 변환기 컬렉션</span><span class="sxs-lookup"><span data-stu-id="f9ce5-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="f9ce5-169">다음은 <xref:System.ComponentModel.DateTimeOffsetConverter>를 <xref:System.DateTimeOffset> 형식의 속성에 대한 기본값으로 지정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="f9ce5-170">다음 형식의 인스턴스를 직렬화한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="f9ce5-171">다음은 사용자 지정 변환기가 사용되었음을 보여 주는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="f9ce5-172">다음 코드에서는 사용자 지정 `DateTimeOffset` 변환기를 사용하여 역직렬화하기 위해 동일한 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="f9ce5-173">등록 샘플 - 속성에 적용되는 [JsonConverter]</span><span class="sxs-lookup"><span data-stu-id="f9ce5-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="f9ce5-174">다음 코드에서는 `Date` 속성에 대한 사용자 지정 변환기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="f9ce5-175">`WeatherForecastWithConverterAttribute`를 직렬화하는 코드는 `JsonSerializeOptions.Converters`를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="f9ce5-176">역직렬화하는 코드도 `Converters`를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="f9ce5-177">등록 샘플 - 형식에 적용되는 [JsonConverter]</span><span class="sxs-lookup"><span data-stu-id="f9ce5-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="f9ce5-178">다음은 구조체를 만들고 `[JsonConverter]` 특성을 적용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="f9ce5-179">앞의 구조체에 대한 사용자 지정 변환기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="f9ce5-180">구조체의 `[JsonConvert]` 특성은 사용자 지정 변환기를 `Temperature` 형식의 속성에 대한 기본값으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="f9ce5-181">이 변환기는 다음 형식의 `TemperatureCelsius` 속성을 직렬화 또는 역직렬화할 때 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="f9ce5-182">변환기 등록 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f9ce5-182">Converter registration precedence</span></span>

<span data-ttu-id="f9ce5-183">serialization 또는 deserialization 동안 각 JSON 요소에 대해 가장 높은 우선 순위에서 가장 낮은 순서로 변환기가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="f9ce5-184">속성에 적용된 `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="f9ce5-185">`Converters` 컬렉션에 추가된 변환기.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="f9ce5-186">사용자 지정 값 형식 또는 POCO에 적용된 `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="f9ce5-187">`Converters` 컬렉션에 특정 형식에 대한 여러 사용자 지정 변환기가 등록된 경우 `CanConvert`에 true를 반환하는 첫 번째 변환기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="f9ce5-188">기본 제공 변환기는 해당하는 사용자 지정 변환기가 등록되지 않은 경우에만 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="f9ce5-189">일반 시나리오용 변환기 샘플</span><span class="sxs-lookup"><span data-stu-id="f9ce5-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="f9ce5-190">다음 섹션에서는 기본 제공 기능이 처리하지 않는 몇 가지 일반적인 시나리오를 해결하는 변환기 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="f9ce5-191">유추된 형식을 개체 속성으로 역직렬화</span><span class="sxs-lookup"><span data-stu-id="f9ce5-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="f9ce5-192">문자열이 아닌 키를 사용하는 사전 지원</span><span class="sxs-lookup"><span data-stu-id="f9ce5-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="f9ce5-193">다형 deserialization 지원</span><span class="sxs-lookup"><span data-stu-id="f9ce5-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="f9ce5-194">유추된 형식을 개체 속성으로 역직렬화</span><span class="sxs-lookup"><span data-stu-id="f9ce5-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="f9ce5-195">`object` 형식의 속성으로 역직렬화할 때 `JsonElement` 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="f9ce5-196">그 이유는 역직렬 변환기가 만들 CLR 형식을 알지 못하고 추측하려고 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="f9ce5-197">예를 들어 JSON 속성에 "true"가 있는 경우 역직렬 변환기는 값이 `Boolean`임을 유추하지 않으며 요소에 "01/01/2019"가 있는 경우 역직렬 변환기가 `DateTime`를 유추하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="f9ce5-198">형식 유추는 정확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="f9ce5-199">역직렬 변환기가 소수점이 없는 JSON 번호를 `long`으로 구문 분석하는 경우 값이 원래 `ulong` 또는 `BigInteger`로 직렬화되었다면 범위를 벗어남 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="f9ce5-200">소수점이 있는 숫자를 `double`로 구문 분석하면 해당 숫자가 원래 `decimal`로 직렬화된 경우에는 전체 자릿수가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="f9ce5-201">형식 유추가 필요한 시나리오의 경우 다음 코드는 `object` 속성에 대한 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="f9ce5-202">이 코드는 다음과 같이 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-202">The code converts:</span></span>

* <span data-ttu-id="f9ce5-203">`true` 및 `false`를 `Boolean`으로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="f9ce5-204">소수점이 없는 숫자를 `long`으로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="f9ce5-205">소수점이 있는 숫자를 `double`로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="f9ce5-206">날짜를 `DateTime`으로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="f9ce5-207">문자열을 `string`으로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-207">Strings to `string`</span></span>
* <span data-ttu-id="f9ce5-208">그 밖의 모든 항목으로 `JsonElement`로</span><span class="sxs-lookup"><span data-stu-id="f9ce5-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="f9ce5-209">다음 코드는 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="f9ce5-210">다음은 `object` 속성을 사용하는 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="f9ce5-211">다음의 역직렬화 JSON 예제에는 `DateTime`, `long` 및 `string`으로 역직렬화될 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="f9ce5-212">사용자 지정 변환기가 없으면 deserialization은 각 속성에 `JsonElement`를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="f9ce5-213">`System.Text.Json.Serialization` 네임스페이스의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 `object` 속성에 대한 deserialization을 처리하는 사용자 지정 변환기의 더 많은 예제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="f9ce5-214">문자열이 아닌 키를 사용하는 사전 지원</span><span class="sxs-lookup"><span data-stu-id="f9ce5-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="f9ce5-215">사전 컬렉션에 대한 기본 제공 지원은 `Dictionary<string, TValue>`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="f9ce5-216">즉, 키가 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-216">That is, the key must be a string.</span></span> <span data-ttu-id="f9ce5-217">정수 또는 다른 형식을 키로 사용하는 사전을 지원하려면 사용자 지정 변환기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="f9ce5-218">다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동하는 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="f9ce5-219">다음 코드는 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="f9ce5-220">이 변환기는 다음 `Enum`을 사용하는 다음 클래스의 `TemperatureRanges` 속성을 직렬화 및 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="f9ce5-221">Serialization의 JSON 출력은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-221">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="f9ce5-222">`System.Text.Json.Serialization` 네임스페이스의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 비 문자열 키 사전을 처리하는 사용자 지정 변환기의 더 많은 예제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="f9ce5-223">다형 deserialization 지원</span><span class="sxs-lookup"><span data-stu-id="f9ce5-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="f9ce5-224">기본 제공 기능을 통해 제한적으로 [다형 serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes)을 제공할 수 있지만 deserialization은 전혀 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="f9ce5-225">deserialization을 수행하려면 사용자 지정 변환기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="f9ce5-226">예를 들어 `Employee` 및 `Customer` 파생 클래스를 사용하는 `Person` 추상 기본 클래스가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="f9ce5-227">다형 deserialization은 디자인 타임에 `Person`을 deserialization 대상으로 지정할 수 있고 런타임에 JSON의 `Customer` 및 `Employee` 개체가 올바르게 역직렬화됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="f9ce5-228">deserialization 동안 JSON에서 필요한 형식을 식별하는 단서를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="f9ce5-229">사용 가능한 단서의 종류는 각 시나리오마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="f9ce5-230">예를 들어 판별자 속성을 사용할 수 있거나 특정 속성이 존재하는지 여부에 의존해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="f9ce5-231">현재 릴리스의 `System.Text.Json`에서는 다형 deserialization 시나리오를 처리하는 방법을 지정하는 특성을 제공하지 않으므로 사용자 지정 변환기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="f9ce5-232">다음 코드에서는 기본 클래스, 두 개의 파생 클래스 및 해당 클래스에 대한 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="f9ce5-233">이 변환기는 판별자 속성을 사용하여 다형 deserialization을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="f9ce5-234">형식 판별자는 클래스 정의에 없지만 serialization 동안 만들어지고 deserialization 동안 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="f9ce5-235">다음 코드는 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="f9ce5-236">변환기는 동일한 직렬화 변환기를 사용하여 만든 JSON을 역직렬화할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="f9ce5-237">이전 예제의 변환기 코드는 각 속성을 수동으로 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="f9ce5-238">대신 `Deserialize` 또는 `Serialize`를 호출하여 일부 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="f9ce5-239">예제는 [이 StackOverflow 게시물](https://stackoverflow.com/a/59744873/12509023)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="f9ce5-240">기타 사용자 지정 변환기 샘플</span><span class="sxs-lookup"><span data-stu-id="f9ce5-240">Other custom converter samples</span></span>

<span data-ttu-id="f9ce5-241">[Newtonsoft.Json에서 System.Text.Json로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md) 문서에는 사용자 지정 변환기의 추가 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="f9ce5-242">`System.Text.Json.Serialization` 소스 코드의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 다음과 같은 다른 사용자 지정 변환기 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="f9ce5-243">[역직렬화할 때 null을 0으로 변환하는 Int32 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="f9ce5-244">[역직렬화할 때 문자열 및 숫자 값을 모두 허용하는 Int32 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="f9ce5-245">[Enum 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="f9ce5-246">외부 데이터를 허용하는 [List\<T> 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="f9ce5-247">[쉼표로 구분된 숫자 목록과 함께 작동하는 Long[] 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="f9ce5-248">기존 기본 제공 변환기의 동작을 수정하는 변환기를 만들어야 하는 경우 [기존 변환기의 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)를 가져와 사용자 지정을 위한 시작 지점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce5-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9ce5-249">추가 자료</span><span class="sxs-lookup"><span data-stu-id="f9ce5-249">Additional resources</span></span>

* <span data-ttu-id="f9ce5-250">[기본 제공 변환기 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="f9ce5-251">[System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="f9ce5-252">[System.Text.Json 개요](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="f9ce5-253">[System.Text.Json 사용 방법](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="f9ce5-254">[Newtonsoft.Json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="f9ce5-255">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="f9ce5-256">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="f9ce5-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
