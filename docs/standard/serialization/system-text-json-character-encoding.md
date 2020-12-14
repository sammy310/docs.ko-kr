---
title: System.Text.Json을 사용하여 문자 인코딩을 사용자 지정하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 문자 인코딩을 사용자 지정하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cfb83af0c58e0c9dfb73ecb8e2177d255e403fae
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009627"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a><span data-ttu-id="9fcc7-103">System.Text.Json을 사용하여 문자 인코딩을 사용자 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="9fcc7-103">How to customize character encoding with System.Text.Json</span></span>

<span data-ttu-id="9fcc7-104">기본적으로 직렬 변환기는 ASCII가 아닌 문자를 모두 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-104">By default, the serializer escapes all non-ASCII characters.</span></span> <span data-ttu-id="9fcc7-105">즉, ASCII가 아닌 문자를 `\uxxxx`로 바꾸며, 여기서 `xxxx`는 문자의 유니코드 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-105">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span> <span data-ttu-id="9fcc7-106">예를 들어 다음 JSON의 `Summary` 속성이 키릴 자모 `жарко`로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-106">For example, if the `Summary` property in the following JSON is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a><span data-ttu-id="9fcc7-107">언어 문자 세트 직렬화</span><span class="sxs-lookup"><span data-stu-id="9fcc7-107">Serialize language character sets</span></span>

<span data-ttu-id="9fcc7-108">하나 이상의 언어 문자 세트를 이스케이프하지 않고 직렬화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-108">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

<span data-ttu-id="9fcc7-109">이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-109">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="9fcc7-110">`Summary` 속성이 키릴 자모 `жарко`로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-110">If the `Summary` property is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="9fcc7-111">모든 언어 세트를 이스케이프하지 않고 직렬화하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-111">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

## <a name="serialize-specific-characters"></a><span data-ttu-id="9fcc7-112">특정 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="9fcc7-112">Serialize specific characters</span></span>

<span data-ttu-id="9fcc7-113">이스케이프하지 않고 허용하려는 개별 문자를 지정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-113">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="9fcc7-114">다음 예제는 `жарко`의 처음 두 문자만 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-114">The following example serializes only the first two characters of `жарко`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

<span data-ttu-id="9fcc7-115">다음은 이전 코드에서 생성된 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-115">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a><span data-ttu-id="9fcc7-116">모든 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="9fcc7-116">Serialize all characters</span></span>

<span data-ttu-id="9fcc7-117">이스케이프를 최소화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-117">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> <span data-ttu-id="9fcc7-118">기본 인코더와 비교할 때, `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프하지 않은 상태로 통과할 수 있도록 허용하는 기준이 더 관대합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-118">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="9fcc7-119">`<`, `>`, `&` 및 `'`처럼 HTML 구분 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-119">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="9fcc7-120">*문자 세트* 에 대한 클라이언트와 서버의 내용이 서로 다를 때 발생할 수 있는 XSS 또는 정보 노출 공격에 대한 심층 방어를 추가로 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-120">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="9fcc7-121">클라이언트가 결과 페이로드를 UTF-8로 인코딩된 JSON으로 해석한다는 사실을 알고 있는 경우에만 안전하지 않은 인코더를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-121">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="9fcc7-122">예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`을 보내는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-122">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="9fcc7-123">원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보내도록 허용하면 절대 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fcc7-123">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fcc7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fcc7-124">See also</span></span>

* [<span data-ttu-id="9fcc7-125">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="9fcc7-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9fcc7-126">JSON 직렬화 및 역직렬화 방법</span><span class="sxs-lookup"><span data-stu-id="9fcc7-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="9fcc7-127">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="9fcc7-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="9fcc7-128">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9fcc7-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="9fcc7-129">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9fcc7-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="9fcc7-130">속성 무시</span><span class="sxs-lookup"><span data-stu-id="9fcc7-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="9fcc7-131">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="9fcc7-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="9fcc7-132">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="9fcc7-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="9fcc7-133">참조 유지</span><span class="sxs-lookup"><span data-stu-id="9fcc7-133">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="9fcc7-134">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="9fcc7-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="9fcc7-135">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="9fcc7-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="9fcc7-136">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9fcc7-136">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="9fcc7-137">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="9fcc7-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="9fcc7-138">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="9fcc7-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="9fcc7-139">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="9fcc7-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="9fcc7-140">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="9fcc7-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="9fcc7-141">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="9fcc7-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
