---
title: C#을 사용하여 JSON 직렬화 및 역직렬화 - .NET
description: 이 개요에서는 .NET에서 JSON으로 직렬화 및 역직렬화하는 System.Text.Json 네임스페이스 기능에 대해 설명합니다.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009887"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="15667-103">.NET의 JSON 직렬화 및 역직렬화(마샬링 및 역 마샬링) - 개요</span><span class="sxs-lookup"><span data-stu-id="15667-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="15667-104">`System.Text.Json` 네임스페이스는 JSON(JavaScript Object Notation)에서 직렬화 및 역직렬화하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15667-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="15667-105">라이브러리 디자인은 광범위한 기능 집합에 비해 높은 성능과 낮은 메모리 할당을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="15667-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="15667-106">기본 제공 UTF-8 지원은 UTF-8로 인코딩된 JSON 텍스트를 읽고 쓰는 프로세스를 최적화합니다. 이는 웹의 데이터와 디스크의 파일에 가장 널리 사용되는 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="15667-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="15667-107">라이브러리는 메모리 내 DOM(문서 개체 모델)을 사용하기 위한 클래스도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15667-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="15667-108">이 기능을 사용하면 JSON 파일 또는 문자열의 요소에 대한 임의 읽기 전용 액세스가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="15667-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="15667-109">라이브러리를 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="15667-109">How to get the library</span></span>

* <span data-ttu-id="15667-110">라이브러리는 .NET Core 3.0 이상 버전에서 공유 프레임워크의 일부로 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="15667-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="15667-111">이전 프레임워크 버전의 경우 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="15667-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="15667-112">패키지는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="15667-112">The package supports:</span></span>

  * <span data-ttu-id="15667-113">.NET Standard 2.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="15667-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="15667-114">.NET Framework 4.7.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="15667-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="15667-115">.NET Core 2.0, 2.1 및 2.2</span><span class="sxs-lookup"><span data-stu-id="15667-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15667-116">추가 자료</span><span class="sxs-lookup"><span data-stu-id="15667-116">Additional resources</span></span>

* [<span data-ttu-id="15667-117">라이브러리를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="15667-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="15667-118">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="15667-118">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="15667-119">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="15667-119">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="15667-120">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="15667-120">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="15667-121">속성 무시</span><span class="sxs-lookup"><span data-stu-id="15667-121">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="15667-122">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="15667-122">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="15667-123">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="15667-123">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="15667-124">참조 유지</span><span class="sxs-lookup"><span data-stu-id="15667-124">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="15667-125">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="15667-125">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="15667-126">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="15667-126">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="15667-127">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="15667-127">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="15667-128">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="15667-128">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="15667-129">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="15667-129">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="15667-130">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="15667-130">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="15667-131">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="15667-131">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="15667-132">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="15667-132">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="15667-133">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="15667-133">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
