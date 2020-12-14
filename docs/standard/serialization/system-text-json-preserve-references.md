---
title: System.Text.Json을 사용하여 참조를 보존하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 참조를 보존하고 순환 참조를 처리하는 방법을 알아봅니다.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008736"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="22642-103">System.Text.Json을 사용하여 참조를 보존하고 순환 참조를 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="22642-103">How to preserve references and handle circular references with System.Text.Json</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="22642-104">참조를 보존하고 순환 참조를 처리하려면 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A>를 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-104">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="22642-105">이렇게 설정하면 다음과 같은 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-105">This setting causes the following behavior:</span></span>

* <span data-ttu-id="22642-106">직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="22642-106">On serialize:</span></span>

  <span data-ttu-id="22642-107">복합 형식을 쓸 때 직렬 변환기는 메타데이터 속성(`$id`, `$values`, `$ref`)도 씁니다.</span><span class="sxs-lookup"><span data-stu-id="22642-107">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="22642-108">역직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="22642-108">On deserialize:</span></span>

  <span data-ttu-id="22642-109">메타데이터가 필요하며(필수는 아님), 역직렬 변환기는 이해를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-109">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="22642-110">다음 코드는 `Preserve` 설정을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22642-110">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="22642-111">이 기능은 값 형식 또는 변경 불가능한 형식을 유지하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22642-111">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="22642-112">역직렬화 시 변경 불가능한 형식의 인스턴스는 전체 페이로드를 읽은 후에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="22642-112">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="22642-113">따라서 JSON 페이로드 내에 해당 참조가 표시되는 경우 동일한 인스턴스를 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22642-113">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="22642-114">값 형식, 변경 불가능한 형식, 배열의 경우 참조 메타데이터가 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22642-114">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="22642-115">역직렬화 시 `$ref` 또는 `$id`가 발견되면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="22642-115">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="22642-116">하지만 Newtonsoft.Json을 사용하여 직렬화된 페이로드를 역직렬화할 수 있도록 값 형식은 `$id`(및 컬렉션의 경우에는 `$values`)를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-116">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="22642-117">Newtonsoft.Json은 이러한 형식의 메타데이터를 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-117">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="22642-118">개체가 같은지 확인하기 위해 System.Text.Json은 두 개체 인스턴스를 비교할 때 값 같음(<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) 대신 참조 같음(<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>)을 사용하는 <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-118">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="22642-119">참조가 직렬화 및 역직렬화되는 방법에 대한 자세한 내용은 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22642-119">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="22642-120"><xref:System.Text.Json.Serialization.ReferenceResolver> 클래스는 직렬화 및 역직렬화 시 참조를 보존하는 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-120">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="22642-121">파생 클래스를 만들어 사용자 지정 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-121">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="22642-122">예제는 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22642-122">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="22642-123">.NET Core 3.1의 System.Text.Json은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="22642-123">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="22642-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22642-124">See also</span></span>

* [<span data-ttu-id="22642-125">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="22642-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="22642-126">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="22642-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="22642-127">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="22642-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="22642-128">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="22642-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="22642-129">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="22642-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="22642-130">속성 무시</span><span class="sxs-lookup"><span data-stu-id="22642-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="22642-131">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="22642-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="22642-132">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="22642-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="22642-133">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="22642-133">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="22642-134">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="22642-134">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="22642-135">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="22642-135">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="22642-136">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="22642-136">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="22642-137">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="22642-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="22642-138">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="22642-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="22642-139">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="22642-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="22642-140">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="22642-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="22642-141">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="22642-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
