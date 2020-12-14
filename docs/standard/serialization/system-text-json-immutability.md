---
title: System.Text.Json에서 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법을 알아봅니다.
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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008827"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="4b824-103">System.Text.Json에서 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="4b824-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="4b824-104">이 문서에서는 `System.Text.Json` 네임스페이스를 사용하여 레코드와 같이 변경 불가능한 형식을 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="4b824-105">변경 불가능한 형식 및 레코드</span><span class="sxs-lookup"><span data-stu-id="4b824-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="4b824-106">`System.Text.Json`은 매개 변수가 있는 생성자를 사용할 수 있습니다. 이 생성자를 사용하면 변경 불가능한 클래스 또는 구조체를 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="4b824-107">클래스의 경우 유일한 생성자가 매개 변수가 있는 생성자이면 해당 생성자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="4b824-108">구조체 또는 여러 생성자가 포함된 클래스의 경우 [JsonConstructor](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) 특성을 적용하여 사용할 생성자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="4b824-109">특성을 사용하지 않는 경우 매개 변수가 없는 public 생성자가 있으면 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="4b824-110">특성은 public 생성자에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="4b824-111">다음 예제는 `[JsonConstructor]` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="4b824-112">다음 예제와 같이 C# 9의 레코드도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="4b824-113">모든 속성 setter가 public이 아니기 때문에 변경 불가능한 형식의 경우 [public이 아닌 속성 접근자](#non-public-property-accessors)에 대한 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b824-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="4b824-114">`JsonConstructorAttribute` 및 C# 9 레코드 지원은 .Net Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="4b824-115">public이 아닌 속성 접근자</span><span class="sxs-lookup"><span data-stu-id="4b824-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="4b824-116">public이 아닌 속성 접근자를 사용하도록 설정하려면 다음 예제와 같이 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="4b824-117">public이 아닌 속성 접근자는 .NET Core 3.1에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b824-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="4b824-118">자세한 내용은 [Newtonsoft.Json에서 마이그레이션 문서](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b824-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="4b824-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b824-119">See also</span></span>

* [<span data-ttu-id="4b824-120">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="4b824-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="4b824-121">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="4b824-121">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="4b824-122">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="4b824-122">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="4b824-123">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4b824-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="4b824-124">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4b824-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="4b824-125">속성 무시</span><span class="sxs-lookup"><span data-stu-id="4b824-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="4b824-126">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="4b824-126">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="4b824-127">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="4b824-127">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="4b824-128">참조 유지</span><span class="sxs-lookup"><span data-stu-id="4b824-128">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="4b824-129">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="4b824-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="4b824-130">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4b824-130">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="4b824-131">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4b824-131">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="4b824-132">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="4b824-132">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="4b824-133">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="4b824-133">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="4b824-134">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="4b824-134">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="4b824-135">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4b824-135">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="4b824-136">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="4b824-136">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
