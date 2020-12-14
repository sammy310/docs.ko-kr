---
title: System.Text.Json으로 대/소문자를 구분하지 않는 이름 일치를 사용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 대/소문자를 구분하지 않는 속성 이름 일치를 사용하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3e2fb8cbdd35e772b5e97c731199f69aa834bd0a
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009744"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="07b13-103">System.Text.Json으로 대/소문자를 구분하지 않는 이름 일치를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="07b13-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="07b13-104">이 문서에서는 `System.Text.Json` 네임스페이스로 대/소문자를 구분하지 않는 속성 이름 일치를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="07b13-105">대/소문자를 구분하지 않는 속성 매칭</span><span class="sxs-lookup"><span data-stu-id="07b13-105">Case-insensitive property matching</span></span>

<span data-ttu-id="07b13-106">기본적으로 역직렬화는 JSON과 대상 개체 속성 간에 일치하는 대/소문자 구분 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="07b13-107">이 동작을 변경하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="07b13-108">[웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)은 대/소문자 구분 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="07b13-109">다음은 카멜식 대/소문자 속성 이름을 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="07b13-110">파스칼식 대/소문자 속성 이름을 사용하는 다음 형식으로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07b13-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="07b13-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07b13-111">See also</span></span>

* [<span data-ttu-id="07b13-112">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="07b13-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="07b13-113">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="07b13-113">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="07b13-114">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="07b13-114">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="07b13-115">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="07b13-115">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="07b13-116">속성 무시</span><span class="sxs-lookup"><span data-stu-id="07b13-116">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="07b13-117">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="07b13-117">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="07b13-118">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="07b13-118">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="07b13-119">참조 유지</span><span class="sxs-lookup"><span data-stu-id="07b13-119">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="07b13-120">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="07b13-120">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="07b13-121">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="07b13-121">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="07b13-122">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="07b13-122">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="07b13-123">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="07b13-123">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="07b13-124">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="07b13-124">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="07b13-125">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="07b13-125">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="07b13-126">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="07b13-126">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="07b13-127">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="07b13-127">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="07b13-128">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="07b13-128">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
