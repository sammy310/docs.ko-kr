---
title: JSON serialization에 대 한 사용자 지정 변환기를 작성 하는 방법-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33d1cd7764e71d9e2fa382c9f3c5feb77e8defb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283341"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="c2b80-102">.NET에서 JSON serialization에 대 한 사용자 지정 변환기를 작성 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c2b80-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="c2b80-103">이 문서에서는 <xref:System.Text.Json> 네임 스페이스에 제공 된 JSON serialization 클래스에 대 한 사용자 지정 변환기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="c2b80-104">`System.Text.Json`에 대 한 소개는 [.net에서 JSON을 serialize 및 deserialize 하는 방법](system-text-json-how-to.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2b80-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="c2b80-105">*변환기* 는 개체 또는 값을 JSON으로 변환 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="c2b80-106">`System.Text.Json` 네임 스페이스에는 JavaScript 기본 형식에 매핑되는 대부분의 기본 형식에 대 한 기본 제공 변환기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="c2b80-107">사용자 지정 변환기를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-107">You can write custom converters:</span></span>

* <span data-ttu-id="c2b80-108">기본 제공 변환기의 기본 동작을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="c2b80-109">예를 들어 `DateTime` 값을 기본 ISO 8601-1:2019 형식 대신 mm/dd/yyyy 형식으로 표시 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="c2b80-110">사용자 지정 값 형식을 지원 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-110">To support a custom value type.</span></span> <span data-ttu-id="c2b80-111">예를 들어 `PhoneNumber` 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="c2b80-112">현재 릴리스에 포함 되지 않은 기능을 사용 하 여 `System.Text.Json`를 확장 하는 사용자 지정 변환기를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="c2b80-113">이 문서의 뒷부분에서 설명 하는 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="c2b80-114">[유추 된 형식을 개체 속성으로 Deserialize](#deserialize-inferred-types-to-object-properties)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="c2b80-115">[문자열이 아닌 키로 사전을 지원](#support-dictionary-with-non-string-key)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="c2b80-116">[다형 deserialization을 지원](#support-polymorphic-deserialization)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="c2b80-117">사용자 지정 변환기 패턴</span><span class="sxs-lookup"><span data-stu-id="c2b80-117">Custom converter patterns</span></span>

<span data-ttu-id="c2b80-118">사용자 지정 변환기를 만드는 데는 기본 패턴과 팩터리 패턴의 두 가지 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="c2b80-119">팩터리 패턴은 형식 `Enum` 또는 개방형 제네릭을 처리 하는 변환기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="c2b80-120">기본 패턴은 제네릭이 아닌 및 폐쇄형 제네릭 형식에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="c2b80-121">예를 들어 다음 형식의 변환기에는 팩터리 패턴이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="c2b80-122">기본 패턴으로 처리할 수 있는 형식의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="c2b80-123">기본 패턴은 하나의 형식을 처리할 수 있는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="c2b80-124">팩터리 패턴은 런타임에 특정 형식이 필요한 지 여부를 결정 하는 클래스를 만들고 적절 한 변환기를 동적으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="c2b80-125">샘플 기본 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-125">Sample basic converter</span></span>

<span data-ttu-id="c2b80-126">다음 샘플은 기존 데이터 형식에 대 한 기본 serialization을 재정의 하는 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="c2b80-127">변환기는 `DateTimeOffset` 속성에 mm/dd/yyyy 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="c2b80-128">샘플 팩터리 패턴 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-128">Sample factory pattern converter</span></span>

<span data-ttu-id="c2b80-129">다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동 하는 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="c2b80-130">첫 번째 제네릭 형식 매개 변수가 `Enum` 고 두 번째는 열려 있기 때문에 코드는 팩터리 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="c2b80-131">`CanConvert` 메서드는 두 개의 제네릭 매개 변수를 사용 하는 `Dictionary`에 대 한 `true` 반환 합니다 .이 중 첫 번째 매개 변수는 `Enum` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="c2b80-132">내부 변환기는 `TValue`위해 런타임에 제공 되는 형식을 처리 하기 위해 기존 변환기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="c2b80-133">위의 코드는이 문서의 뒷부분에 나오는 [문자열이 아닌 키를 사용 하 여 지원 사전](#support-dictionary-with-non-string-key) 에 표시 되는 코드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="c2b80-134">기본 패턴을 따르는 단계</span><span class="sxs-lookup"><span data-stu-id="c2b80-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="c2b80-135">다음 단계에서는 기본 패턴을 따라 변환기를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="c2b80-136"><xref:System.Text.Json.Serialization.JsonConverter%601>에서 파생 되는 클래스를 만듭니다. 여기서 `T`는 serialize 및 deserialize 할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="c2b80-137">`Read` 메서드를 재정의 하 여 들어오는 JSON을 deserialize 하 고 `T`형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="c2b80-138">메서드에 전달 된 <xref:System.Text.Json.Utf8JsonReader>를 사용 하 여 JSON을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="c2b80-139">`Write` 메서드를 재정의 하 여 `T`형식의 들어오는 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="c2b80-140">메서드에 전달 된 <xref:System.Text.Json.Utf8JsonWriter>를 사용 하 여 JSON을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="c2b80-141">필요한 경우에만 `CanConvert` 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="c2b80-142">변환할 형식이 `T`형식일 때 기본 구현에서는 `true`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="c2b80-143">따라서 형식 `T` 지 원하는 변환기는이 메서드를 재정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="c2b80-144">이 메서드를 재정의 해야 하는 변환기에 대 한 예제는이 문서의 뒷부분에 있는 [다형 deserialization](#support-polymorphic-deserialization) 단원을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2b80-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="c2b80-145">[기본 제공 변환기 소스 코드](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) 를 참조 구현으로 참조 하 여 사용자 지정 변환기를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="c2b80-146">팩터리 패턴을 따르는 단계</span><span class="sxs-lookup"><span data-stu-id="c2b80-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="c2b80-147">다음 단계는 팩터리 패턴을 따라 변환기를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="c2b80-148"><xref:System.Text.Json.Serialization.JsonConverterFactory>에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="c2b80-149">변환할 형식이 변환기에서 처리할 수 있는 형식인 경우 true를 반환 하도록 `CanConvert` 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="c2b80-150">예를 들어 `List<T>`에 대 한 변환기 인 경우 `List<int>`, `List<string>`및 `List<DateTime>`만 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="c2b80-151">런타임에 제공 되는 변환 형식을 처리할 변환기 클래스의 인스턴스를 반환 하도록 `CreateConverter` 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="c2b80-152">`CreateConverter` 메서드가 인스턴스화하는 변환기 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="c2b80-153">개체를 문자열로 변환 하는 코드는 모든 형식에 대해 동일 하지 않기 때문에 개방형 제네릭에 팩터리 패턴이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="c2b80-154">개방형 제네릭 형식 (예:`List<T>`)에 대 한 변환기는 폐쇄형 제네릭 형식 (예:`List<DateTime>`)에 대 한 변환기를 백그라운드에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="c2b80-155">변환기가 처리할 수 있는 각 폐쇄형 제네릭 형식을 처리 하기 위해 코드를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="c2b80-156">`Enum` 형식은 개방형 제네릭 형식과 유사 합니다. `Enum`에 대 한 변환기는 내부적으로 특정 `Enum` (예:`WeekdaysEnum`)의 변환기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="c2b80-157">오류 처리</span><span class="sxs-lookup"><span data-stu-id="c2b80-157">Error handling</span></span>

<span data-ttu-id="c2b80-158">오류 처리 코드에서 예외를 throw 해야 하는 경우에는 메시지 없이 <xref:System.Text.Json.JsonException>를 throw 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="c2b80-159">이 예외 형식은 오류를 발생 시킨 JSON 부분의 경로를 포함 하는 메시지를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="c2b80-160">예를 들어 `throw new JsonException();` 문은 다음 예제와 같이 오류 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="c2b80-161">`throw new JsonException("Error occurred")`와 같이 메시지를 제공 하는 경우 예외는 여전히 <xref:System.Text.Json.JsonException.Path> 속성의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="c2b80-162">사용자 지정 변환기 등록</span><span class="sxs-lookup"><span data-stu-id="c2b80-162">Register a custom converter</span></span>

<span data-ttu-id="c2b80-163">사용자 지정 변환기를 *등록* 하 여 `Serialize` 및 `Deserialize` 메서드가 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="c2b80-164">다음 방법 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="c2b80-165"><xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> 컬렉션에 변환기 클래스의 인스턴스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="c2b80-166">[[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) 특성을 사용자 지정 변환기가 필요한 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="c2b80-167">사용자 지정 값 형식을 나타내는 구조체 또는 클래스에 [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) 특성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="c2b80-168">등록 샘플-변환기 컬렉션</span><span class="sxs-lookup"><span data-stu-id="c2b80-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="c2b80-169">다음은 형식 <xref:System.DateTimeOffset>의 속성에 대 한 기본값을 <xref:System.ComponentModel.DateTimeOffsetConverter> 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="c2b80-170">다음 형식의 인스턴스를 serialize 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="c2b80-171">다음은 사용자 지정 변환기가 사용 되었음을 보여 주는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="c2b80-172">다음 코드에서는 사용자 지정 `DateTimeOffset` 변환기를 사용 하 여 deserialize 하는 동일한 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="c2b80-173">등록 샘플-속성의 [JsonConverter]</span><span class="sxs-lookup"><span data-stu-id="c2b80-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="c2b80-174">다음 코드는 `Date` 속성에 대 한 사용자 지정 변환기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="c2b80-175">`WeatherForecastWithConverterAttribute`를 serialize 하는 코드는 `JsonSerializeOptions.Converters`를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="c2b80-176">Deserialize 할 코드는 `Converters`를 사용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="c2b80-177">등록 샘플-형식에서 [JsonConverter]</span><span class="sxs-lookup"><span data-stu-id="c2b80-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="c2b80-178">구조체를 만들고 `[JsonConverter]` 특성을 적용 하는 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="c2b80-179">앞의 구조체에 대 한 사용자 지정 변환기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="c2b80-180">구조체의 `[JsonConvert]` 특성은 `Temperature`형식의 속성에 대 한 기본값으로 사용자 지정 변환기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="c2b80-181">변환기는 직렬화 하거나 deserialize 할 때 다음 형식의 `TemperatureCelsius` 속성에서 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="c2b80-182">변환기 등록 우선 순위</span><span class="sxs-lookup"><span data-stu-id="c2b80-182">Converter registration precedence</span></span>

<span data-ttu-id="c2b80-183">Serialization 또는 deserialization 중에는 각 JSON 요소에 대해 가장 높은 우선 순위에서 가장 낮은 순서로 변환기가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="c2b80-184">`[JsonConverter]` 속성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="c2b80-185">`Converters` 컬렉션에 추가 된 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="c2b80-186">`[JsonConverter]` 사용자 지정 값 형식 또는 POCO에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="c2b80-187">형식에 대 한 여러 사용자 지정 변환기가 `Converters` 컬렉션에 등록 된 경우 `CanConvert`에 대해 true를 반환 하는 첫 번째 변환기가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="c2b80-188">기본 제공 변환기는 해당 하는 사용자 지정 변환기가 등록 되지 않은 경우에만 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="c2b80-189">일반적인 시나리오에 대 한 변환기 샘플</span><span class="sxs-lookup"><span data-stu-id="c2b80-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="c2b80-190">다음 섹션에서는 기본 제공 기능이 처리 하지 않는 몇 가지 일반적인 시나리오를 해결 하는 변환기 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="c2b80-191">유추 된 형식을 개체 속성으로 Deserialize</span><span class="sxs-lookup"><span data-stu-id="c2b80-191">Deserialize inferred types to Object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="c2b80-192">문자열이 아닌 키가 포함 된 지원 사전</span><span class="sxs-lookup"><span data-stu-id="c2b80-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="c2b80-193">다형 deserialization 지원</span><span class="sxs-lookup"><span data-stu-id="c2b80-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="c2b80-194">유추 된 형식을 개체 속성으로 Deserialize</span><span class="sxs-lookup"><span data-stu-id="c2b80-194">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="c2b80-195">`Object`형식의 속성으로 deserialize 할 때 `JsonElement` 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-195">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="c2b80-196">그 이유는 역직렬 변환기가 만들 CLR 유형을 알지 못하고 추측 하려고 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="c2b80-197">예를 들어 JSON 속성에 "true"가 있는 경우 역직렬 변환기는 값이 `Boolean`임을 유추 하지 않으며 요소에 "01/01/2019"가 있는 경우 역직렬 변환기가 `DateTime`를 유추 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="c2b80-198">형식 유추는 정확 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="c2b80-199">역직렬 변환기가 `long`로 소수점이 없는 JSON 번호를 구문 분석 하는 경우 값이 원래 `ulong` 또는 `BigInteger`으로 serialize 되 면 범위를 벗어난 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="c2b80-200">소수점이 `double` 된 숫자를 구문 분석 하면 해당 숫자가 원래 `decimal`로 serialize 된 경우에는 전체 자릿수가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="c2b80-201">형식 유추가 필요한 시나리오의 경우 다음 코드는 `Object` 속성에 대 한 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-201">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="c2b80-202">코드는 다음을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-202">The code converts:</span></span>

* <span data-ttu-id="c2b80-203">`true` 및 `false` `Boolean`</span><span class="sxs-lookup"><span data-stu-id="c2b80-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="c2b80-204">`long` 또는 `double` 숫자</span><span class="sxs-lookup"><span data-stu-id="c2b80-204">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="c2b80-205">`DateTime` 날짜</span><span class="sxs-lookup"><span data-stu-id="c2b80-205">Dates to `DateTime`</span></span>
* <span data-ttu-id="c2b80-206">`string` 문자열</span><span class="sxs-lookup"><span data-stu-id="c2b80-206">Strings to `string`</span></span>
* <span data-ttu-id="c2b80-207">다른 모든 항목 `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="c2b80-207">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="c2b80-208">다음 코드는 변환기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-208">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="c2b80-209">다음은 `Object` 속성을 사용 하는 예제 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-209">Here's an example type with `Object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="c2b80-210">Deserialize 할 JSON의 다음 예제에는 `DateTime`, `long`및 `string`deserialize 될 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-210">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="c2b80-211">사용자 지정 변환기가 없으면 deserialization은 각 속성에 `JsonElement`을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-211">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="c2b80-212">`System.Text.Json.Serialization` 네임 스페이스의 [단위 테스트 폴더](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) 에는 개체 속성에 대 한 deserialization을 처리 하는 사용자 지정 변환기의 추가 예가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-212">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="c2b80-213">문자열이 아닌 키가 포함 된 지원 사전</span><span class="sxs-lookup"><span data-stu-id="c2b80-213">Support Dictionary with non-string key</span></span>

<span data-ttu-id="c2b80-214">사전 컬렉션에 대 한 기본 제공 지원은 `Dictionary<string, TValue>`입니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-214">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="c2b80-215">즉, 키는 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-215">That is, the key must be a string.</span></span> <span data-ttu-id="c2b80-216">정수 또는 다른 형식을 키로 사용 하는 사전을 지원 하려면 사용자 지정 변환기가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-216">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="c2b80-217">다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동 하는 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-217">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="c2b80-218">다음 코드는 변환기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-218">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="c2b80-219">변환기는 다음 `Enum`를 사용 하는 다음 클래스의 `TemperatureRanges` 속성을 serialize 및 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-219">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="c2b80-220">Serialization에서 JSON 출력은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-220">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="c2b80-221">`System.Text.Json.Serialization` 네임 스페이스의 [단위 테스트 폴더](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) 에는 문자열 키가 아닌 사전을 처리 하는 사용자 지정 변환기의 추가 예가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-221">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="c2b80-222">다형 deserialization 지원</span><span class="sxs-lookup"><span data-stu-id="c2b80-222">Support polymorphic deserialization</span></span>

<span data-ttu-id="c2b80-223">[다형 serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) 에는 사용자 지정 변환기가 필요 하지 않지만 deserialization을 수행 하려면 사용자 지정 변환기가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-223">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="c2b80-224">예를 들어 `Employee` 및 `Customer` 파생 클래스를 사용 하는 `Person` 추상 기본 클래스가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-224">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="c2b80-225">다형 deserialization은 디자인 타임에 `Person`를 deserialization 대상으로 지정할 수 있으며, JSON의 `Customer` 및 `Employee` 개체가 런타임에 올바르게 deserialize 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-225">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="c2b80-226">Deserialization을 수행 하는 동안 JSON에서 필요한 형식을 식별 하는 단서를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-226">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="c2b80-227">사용 가능한 단서의 종류는 각 시나리오 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-227">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="c2b80-228">예를 들어 판별자 속성을 사용할 수 있거나 특정 속성이 있는지 여부를 사용 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-228">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="c2b80-229">현재 `System.Text.Json` 릴리스에서는 다형성 deserialization 시나리오를 처리 하는 방법을 지정 하는 특성을 제공 하지 않으므로 사용자 지정 변환기가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-229">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="c2b80-230">다음 코드에서는 기본 클래스, 두 개의 파생 클래스 및 해당 클래스에 대 한 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-230">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="c2b80-231">변환기는 판별자 속성을 사용 하 여 다형 deserialization을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-231">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="c2b80-232">형식 판별자는 클래스 정의에 없지만 직렬화 하는 동안 만들어지고 deserialization 중에 읽혀집니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-232">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="c2b80-233">다음 코드는 변환기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-233">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="c2b80-234">변환기는 동일한 변환기를 사용 하 여 만든 JSON을 deserialize 할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-234">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="c2b80-235">기타 사용자 지정 변환기 샘플</span><span class="sxs-lookup"><span data-stu-id="c2b80-235">Other custom converter samples</span></span>

<span data-ttu-id="c2b80-236">`System.Text.Json.Serialization` 소스 코드의 [단위 테스트 폴더](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) 에는 다음과 같은 다른 사용자 지정 변환기 샘플이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2b80-236">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="c2b80-237">deserialize 할 때 null을 0으로 변환 하는 `Int32` 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-237">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="c2b80-238">deserialize 할 때 문자열 및 숫자 값을 모두 허용 하는 `Int32` 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-238">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="c2b80-239">`Enum` 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-239">`Enum` converter</span></span>
* <span data-ttu-id="c2b80-240">외부 데이터를 허용 하는 `List<T>` 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-240">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="c2b80-241">쉼표로 구분 된 숫자 목록과 함께 작동 하는 `Long[]` 변환기</span><span class="sxs-lookup"><span data-stu-id="c2b80-241">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="c2b80-242">추가 자료</span><span class="sxs-lookup"><span data-stu-id="c2b80-242">Additional resources</span></span>

* [<span data-ttu-id="c2b80-243">System.object 개요</span><span class="sxs-lookup"><span data-stu-id="c2b80-243">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="c2b80-244">System.object API 참조</span><span class="sxs-lookup"><span data-stu-id="c2b80-244">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="c2b80-245">System.object를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c2b80-245">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="c2b80-246">기본 제공 변환기에 대 한 소스 코드</span><span class="sxs-lookup"><span data-stu-id="c2b80-246">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="c2b80-247">`System.Text.Json`에 대 한 사용자 지정 변환기와 관련 된 GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="c2b80-247">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="c2b80-248">36639 사용자 지정 변환기 소개</span><span class="sxs-lookup"><span data-stu-id="c2b80-248">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="c2b80-249">38713 개체를 역직렬화 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c2b80-249">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="c2b80-250">40120 문자열 키 사전이 아닌 사전 정보</span><span class="sxs-lookup"><span data-stu-id="c2b80-250">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="c2b80-251">37787 다형성 deserialization 정보</span><span class="sxs-lookup"><span data-stu-id="c2b80-251">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
