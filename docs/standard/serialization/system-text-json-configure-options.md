---
title: System.Text.Json을 사용하여 JsonSerializerOptions를 인스턴스화하는 방법
description: 기존 인스턴스를 복사하거나 웹 기본값을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법을 알아봅니다.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439870"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="fca41-103">System.Text.Json을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법</span><span class="sxs-lookup"><span data-stu-id="fca41-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="fca41-104">이 문서에서는 기존 인스턴스를 복사하거나 웹 기본값을 사용하여 <xref:System.Text.Json.JsonSerializerOptions> 인스턴스를 인스턴스화하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-104">In this article, you'll learn how to instantiate <xref:System.Text.Json.JsonSerializerOptions> instances by copying existing instances or with web defaults.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="fca41-105">JsonSerializerOptions 복사</span><span class="sxs-lookup"><span data-stu-id="fca41-105">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="fca41-106">다음 예제와 같이 기존 인스턴스와 동일한 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions))이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-106">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="fca41-107">기존 인스턴스를 사용하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-107">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="fca41-108">JsonSerializerOptions의 웹 기본값</span><span class="sxs-lookup"><span data-stu-id="fca41-108">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="fca41-109">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-109">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="fca41-110">다음 예제와 같이 ASP.NET Core가 웹앱에 사용하는 기본 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-110">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="fca41-111">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-111">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="fca41-112">기본값 집합을 지정하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fca41-112">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="fca41-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fca41-113">See also</span></span>

* [<span data-ttu-id="fca41-114">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="fca41-114">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="fca41-115">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="fca41-115">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="fca41-116">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fca41-116">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="fca41-117">속성 무시</span><span class="sxs-lookup"><span data-stu-id="fca41-117">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="fca41-118">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="fca41-118">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="fca41-119">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="fca41-119">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="fca41-120">순환 참조 보존</span><span class="sxs-lookup"><span data-stu-id="fca41-120">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="fca41-121">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="fca41-121">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="fca41-122">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="fca41-122">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="fca41-123">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="fca41-123">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
