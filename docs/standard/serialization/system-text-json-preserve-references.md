---
title: System.Text.Json을 사용하여 참조를 보존하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 참조를 보존하고 순환 참조를 처리하는 방법을 알아봅니다.
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
ms.openlocfilehash: 9254ca261c7d748c04c311fa56359014f752ff31
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439836"
---
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="1dd83-103">System.Text.Json을 사용하여 순환 참조를 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="1dd83-103">How to handle circular references with System.Text.Json</span></span>

<span data-ttu-id="1dd83-104">이 문서에서는 `System.Text.Json` 네임스페이스를 사용하여 순환 참조를 처리하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-104">In this article, you will learn how to handle circular references with the `System.Text.Json` namespace.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="1dd83-105">참조를 보존하고 순환 참조를 처리</span><span class="sxs-lookup"><span data-stu-id="1dd83-105">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1dd83-106">참조를 보존하고 순환 참조를 처리하려면 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A>를 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-106">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="1dd83-107">이렇게 설정하면 다음과 같은 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-107">This setting causes the following behavior:</span></span>

* <span data-ttu-id="1dd83-108">직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="1dd83-108">On serialize:</span></span>

  <span data-ttu-id="1dd83-109">복합 형식을 쓸 때 직렬 변환기는 메타데이터 속성(`$id`, `$values`, `$ref`)도 씁니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-109">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="1dd83-110">역직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="1dd83-110">On deserialize:</span></span>

  <span data-ttu-id="1dd83-111">메타데이터가 필요하며(필수는 아님), 역직렬 변환기는 이해를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-111">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="1dd83-112">다음 코드는 `Preserve` 설정을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-112">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="1dd83-113">이 기능은 값 형식 또는 변경 불가능한 형식을 유지하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-113">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="1dd83-114">역직렬화 시 변경 불가능한 형식의 인스턴스는 전체 페이로드를 읽은 후에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-114">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="1dd83-115">따라서 JSON 페이로드 내에 해당 참조가 표시되는 경우 동일한 인스턴스를 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-115">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="1dd83-116">값 형식, 변경 불가능한 형식, 배열의 경우 참조 메타데이터가 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-116">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="1dd83-117">역직렬화 시 `$ref` 또는 `$id`가 발견되면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-117">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="1dd83-118">하지만 Newtonsoft.Json을 사용하여 직렬화된 페이로드를 역직렬화할 수 있도록 값 형식은 `$id`(및 컬렉션의 경우에는 `$values`)를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-118">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="1dd83-119">Newtonsoft.Json은 이러한 형식의 메타데이터를 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-119">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="1dd83-120">개체가 같은지 확인하기 위해 System.Text.Json은 두 개체 인스턴스를 비교할 때 값 같음(<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) 대신 참조 같음(<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>)을 사용하는 <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-120">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="1dd83-121">참조가 직렬화 및 역직렬화되는 방법에 대한 자세한 내용은 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd83-121">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1dd83-122"><xref:System.Text.Json.Serialization.ReferenceResolver> 클래스는 직렬화 및 역직렬화 시 참조를 보존하는 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-122">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="1dd83-123">파생 클래스를 만들어 사용자 지정 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-123">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="1dd83-124">예제는 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd83-124">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1dd83-125">.NET Core 3.1의 System.Text.Json은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd83-125">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="1dd83-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dd83-126">See also</span></span>

* [<span data-ttu-id="1dd83-127">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="1dd83-127">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1dd83-128">JsonSerializerOptions 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1dd83-128">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="1dd83-129">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1dd83-129">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="1dd83-130">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1dd83-130">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="1dd83-131">속성 무시</span><span class="sxs-lookup"><span data-stu-id="1dd83-131">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="1dd83-132">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="1dd83-132">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="1dd83-133">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="1dd83-133">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="1dd83-134">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="1dd83-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="1dd83-135">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="1dd83-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="1dd83-136">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1dd83-136">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
