---
title: System.Text.Json을 사용하여 일부 잘못된 종류의 JSON을 허용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 주석, 후행 쉼표, 따옴표 붙은 숫자를 허용하는 방법을 알아봅니다.
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
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439818"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a><span data-ttu-id="bc401-103">System.Text.Json을 사용하여 일부 잘못된 종류의 JSON을 허용하는 방법</span><span class="sxs-lookup"><span data-stu-id="bc401-103">How to allow some kinds of invalid JSON with System.Text.Json</span></span>

<span data-ttu-id="bc401-104">이 문서에서는 JSON에서 주석, 후행 쉼표, 따옴표 붙은 숫자를 허용하는 방법과 숫자를 문자열로 쓰는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-104">In this article, you will learn how to allow comments, trailing commas, and quoted numbers in JSON, and how to write numbers as strings.</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="bc401-105">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="bc401-105">Allow comments and trailing commas</span></span>

<span data-ttu-id="bc401-106">기본적으로 주석과 후행 쉼표는 JSON에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-106">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="bc401-107">JSON에서 주석을 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-107">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="bc401-108">그리고 후행 쉼표를 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-108">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="bc401-109">다음 예제에서는 주석과 후행 쉼표를 허용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-109">The following example shows how to allow both:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

<span data-ttu-id="bc401-110">다음은 주석과 후행 쉼표를 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-110">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="bc401-111">따옴표 안에 숫자를 허용하거나 씁니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-111">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="bc401-112">일부 직렬 변환기는 숫자를 JSON 문자열로 인코딩합니다(따옴표로 묶음).</span><span class="sxs-lookup"><span data-stu-id="bc401-112">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span>

<span data-ttu-id="bc401-113">예:</span><span class="sxs-lookup"><span data-stu-id="bc401-113">For example:</span></span>

```json
{
    "DegreesCelsius": "23"
}
```

<span data-ttu-id="bc401-114">다음 식을 사용하는 대신</span><span class="sxs-lookup"><span data-stu-id="bc401-114">Instead of:</span></span>

```json
{
    "DegreesCelsius": 23
}
```

<span data-ttu-id="bc401-115">전체 입력 개체 그래프에서 따옴표 안의 숫자를 직렬화하거나 따옴표 안의 숫자를 허용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-115">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

<span data-ttu-id="bc401-116">ASP.NET Core를 통해 간접적으로 `System.Text.Json`을 사용하는 경우 ASP.NET Core가 [웹 기본 옵션](xref:System.Text.Json.JsonSerializerDefaults.Web)을 지정하기 때문에 역직렬화할 때 따옴표 붙은 숫자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-116">When you use `System.Text.Json` indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="bc401-117">특정 속성, 필드 또는 형식에 따옴표 붙은 숫자를 허용하거나 쓰려면 [JsonNumberHandling](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-117">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="bc401-118">.NET Core 3.1에서 `System.Text.Json`은 따옴표로 묶은 숫자의 직렬화 또는 역직렬화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc401-118">`System.Text.Json` in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="bc401-119">자세한 내용은 [따옴표 안의 숫자 허용 또는 쓰기](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc401-119">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="bc401-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc401-120">See also</span></span>

* [<span data-ttu-id="bc401-121">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="bc401-121">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="bc401-122">JsonSerializerOptions 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="bc401-122">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="bc401-123">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="bc401-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="bc401-124">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bc401-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="bc401-125">속성 무시</span><span class="sxs-lookup"><span data-stu-id="bc401-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="bc401-126">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="bc401-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="bc401-127">순환 참조 보존</span><span class="sxs-lookup"><span data-stu-id="bc401-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="bc401-128">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="bc401-128">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="bc401-129">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="bc401-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="bc401-130">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="bc401-130">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
