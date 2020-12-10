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
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599078"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="1e63c-103">System.Text.Json으로 대/소문자를 구분하지 않는 이름 일치를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="1e63c-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="1e63c-104">이 문서에서는 `System.Text.Json` 네임스페이스로 대/소문자를 구분하지 않는 속성 이름 일치를 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="1e63c-105">대/소문자를 구분하지 않는 속성 매칭</span><span class="sxs-lookup"><span data-stu-id="1e63c-105">Case-insensitive property matching</span></span>

<span data-ttu-id="1e63c-106">기본적으로 역직렬화는 JSON과 대상 개체 속성 간에 일치하는 대/소문자 구분 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="1e63c-107">이 동작을 변경하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="1e63c-108">[웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)은 대/소문자 구분 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="1e63c-109">다음은 카멜식 대/소문자 속성 이름을 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="1e63c-110">파스칼식 대/소문자 속성 이름을 사용하는 다음 형식으로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e63c-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="1e63c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e63c-111">See also</span></span>

* [<span data-ttu-id="1e63c-112">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="1e63c-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1e63c-113">JsonSerializerOptions 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1e63c-113">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="1e63c-114">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1e63c-114">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="1e63c-115">속성 무시</span><span class="sxs-lookup"><span data-stu-id="1e63c-115">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="1e63c-116">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="1e63c-116">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="1e63c-117">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="1e63c-117">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="1e63c-118">순환 참조 보존</span><span class="sxs-lookup"><span data-stu-id="1e63c-118">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="1e63c-119">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="1e63c-119">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="1e63c-120">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="1e63c-120">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="1e63c-121">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1e63c-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
