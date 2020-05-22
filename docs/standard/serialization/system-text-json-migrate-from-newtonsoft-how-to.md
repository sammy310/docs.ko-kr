---
title: Newtonsoft.Json에서 System.Text.Json으로 마이그레이션 - .NET
author: ''
ms.author: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: ''
helpviewer_keywords: []
ms.openlocfilehash: fe370b34d311816a815f3b2d419751ac7871f013
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703587"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="0f1ff-102">Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="0f1ff-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="0f1ff-103">이 문서에서는 [Newtonsoft.Json](https://www.newtonsoft.com/json)에서 <xref:System.Text.Json>로 마이그레이션하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

<span data-ttu-id="0f1ff-104">`System.Text.Json` 네임스페이스는 JSON(JavaScript Object Notation)에서 직렬화 및 역직렬화하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="0f1ff-105">`System.Text.Json` 라이브러리는 [.NET Core 3.0](https://aka.ms/netcore3download) 공유 프레임워크에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-105">The `System.Text.Json` library is included in the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span> <span data-ttu-id="0f1ff-106">다른 대상 프레임워크의 경우 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-106">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="0f1ff-107">패키지는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-107">The package supports:</span></span>

* <span data-ttu-id="0f1ff-108">.NET Standard 2.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0f1ff-108">.NET Standard 2.0 and later versions</span></span>
* <span data-ttu-id="0f1ff-109">.NET Framework 4.7.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0f1ff-109">.NET Framework 4.7.2 and later versions</span></span>
* <span data-ttu-id="0f1ff-110">.NET Core 2.0, 2.1, 2.2</span><span class="sxs-lookup"><span data-stu-id="0f1ff-110">.NET Core 2.0, 2.1, and 2.2</span></span>

<span data-ttu-id="0f1ff-111">`System.Text.Json`은 성능, 보안 및 표준 규정 준수에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-111">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="0f1ff-112">기본 동작에서 몇 가지 큰 차이가 있으며 `Newtonsoft.Json`과의 기능 패리티를 목표로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-112">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="0f1ff-113">일부 시나리오에서는 `System.Text.Json`에 기본 기능이 없지만, 권장 해결 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-113">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="0f1ff-114">그 외의 시나리오에서는 해결 방법이 실용적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-114">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="0f1ff-115">애플리케이션에서 사용하는 기능이 없는 경우 [이슈를 제출](https://github.com/dotnet/runtime/issues/new)하여 해당 시나리오에 대한 지원을 추가할 수 있는지 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-115">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="0f1ff-116">이 문서의 대부분은 <xref:System.Text.Json.JsonSerializer> API 사용 방법에 대한 내용이지만, <xref:System.Text.Json.JsonDocument>(DOM(문서 개체 모델)을 나타냄), <xref:System.Text.Json.Utf8JsonReader> 및 <xref:System.Text.Json.Utf8JsonWriter> 형식을 사용하는 방법에 대한 지침도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-116">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span>

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a><span data-ttu-id="0f1ff-117">Newtonsoft.Json와 System.Text.Json 간의 차이점 표</span><span class="sxs-lookup"><span data-stu-id="0f1ff-117">Table of differences between Newtonsoft.Json and System.Text.Json</span></span>

<span data-ttu-id="0f1ff-118">다음 표에는 `Newtonsoft.Json` 기능과 그에 상응하는 `System.Text.Json` 기능이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-118">The following table lists `Newtonsoft.Json` features and `System.Text.Json` equivalents.</span></span> <span data-ttu-id="0f1ff-119">상응하는 기능은 다음 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-119">The equivalents fall into the following categories:</span></span>

* <span data-ttu-id="0f1ff-120">기본 제공 기능에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-120">Supported by built-in functionality.</span></span> <span data-ttu-id="0f1ff-121">`System.Text.Json`에서 유사한 동작을 가져오려면 특성 또는 글로벌 옵션을 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-121">Getting similar behavior from `System.Text.Json` may require the use of an attribute or global option.</span></span>
* <span data-ttu-id="0f1ff-122">지원되지 않으며, 해결이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-122">Not supported, workaround is possible.</span></span> <span data-ttu-id="0f1ff-123">해결 방법은 [사용자 지정 변환기](system-text-json-converters-how-to.md)이며, 사용자 지정 변환기는 `Newtonsoft.Json` 기능과의 완전한 패리티를 제공하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-123">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="0f1ff-124">그 중 일부는 샘플 코드가 예제로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-124">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="0f1ff-125">이러한 `Newtonsoft.Json` 기능을 사용하는 경우 마이그레이션을 수행하려면 .NET 개체 모델 또는 기타 코드 변경 내용을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-125">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>
* <span data-ttu-id="0f1ff-126">지원되지 않으며, 해결 방법이 실용적이지 않거나 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-126">Not supported, workaround is not practical or possible.</span></span> <span data-ttu-id="0f1ff-127">이러한 `Newtonsoft.Json` 기능을 사용하는 경우 중요한 변경 없이는 마이그레이션을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-127">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

| Newtonsoft.Json<span data-ttu-id="0f1ff-128"> 기능</span><span class="sxs-lookup"><span data-stu-id="0f1ff-128"> feature</span></span>                               | System.Text.Json<span data-ttu-id="0f1ff-129"> 해당 항목</span><span class="sxs-lookup"><span data-stu-id="0f1ff-129"> equivalent</span></span> |
|---
<span data-ttu-id="0f1ff-130">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-130">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-131">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-131">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-133">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-133">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-134">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-134">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-136">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-136">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-137">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-137">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-139">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-139">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-140">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-140">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-142">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-142">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-143">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-143">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-145">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-145">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-146">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-146">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-148">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-148">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-149">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-149">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-151">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-151">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-152">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-152">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-154">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-154">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-155">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-155">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-157">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-157">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-158">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-158">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-160">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-160">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-161">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-161">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-163">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-163">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-164">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-164">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-166">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-166">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-167">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-167">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-169">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-169">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-170">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-170">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-172">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-172">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-173">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-173">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-175">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-175">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-176">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-176">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-178">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-178">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-179">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-179">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-181">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-181">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-182">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-182">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-184">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-184">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-185">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-185">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-187">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-187">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-188">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-188">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-190">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-190">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-191">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-191">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-193">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-193">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-194">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-194">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-196">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-196">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-197">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-197">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-199">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-199">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-200">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-200">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-202">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-202">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-203">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-203">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="0f1ff-205">----------------------------|--- title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-205">----------------------------|--- title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-206">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-206">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-208">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-208">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-209">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-209">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-211">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-211">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-212">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-212">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-214">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-214">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-215">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-215">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-217">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-217">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-218">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-218">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-220">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-220">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-221">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-221">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-223">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-223">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-224">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-224">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-226">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-226">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-227">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-227">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-229">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-229">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-230">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-230">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-232">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-232">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-233">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-233">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-235">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-235">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-236">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-236">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="0f1ff-238">title: 'Newtonsoft.Json에서 System.Text.Json로 마이그레이션 - .NET' 작성자: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-238">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="0f1ff-239">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="0f1ff-239">'System.Text.Json'</span></span>
- <span data-ttu-id="0f1ff-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="0f1ff-241">---------------| | 기본적으로 대/소문자를 구분하지 않는 deserialization           | ✔️ [PropertyNameCaseInsensitive 전역 설정](#case-insensitive-deserialization) | | 카멜식 대/소문자 속성 이름                             | ✔️ [PropertyNamingPolicy 전역 설정](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | 최소 문자 이스케이프                            | ✔️ [엄격 문자 이스케이프, 구성 가능](#minimal-character-escaping) | | `NullValueHandling.Ignore` 전역 설정             | ✔️ [IgnoreNullValues 전역 설정](system-text-json-how-to.md#exclude-all-null-value-properties) | | 주석 허용                                        | ✔️ [ReadCommentHandling 전역 설정](#comments) | | 후행 쉼표 허용                                 | ✔️ [AllowTrailingCommas 전역 설정](#trailing-commas) | | 사용자 지정 변환기 등록                         | ✔️ [우선 순위 다름](#converter-registration-precedence) | | 기본적으로 최대 깊이 없음                           | ✔️ [기본 최대 깊이 64, 구성 가능](#maximum-depth) | | 광범위한 형식 지원                    | ⚠ [일부 형식은 사용자 지정 변환기 필요](#types-without-built-in-support) | | 문자열을 숫자로 역직렬화                        | ⚠ [지원되지 않음, 해결 방법, 샘플](#quoted-numbers) | | 문자열이 아닌 키로 `Dictionary` 역직렬화          | ⚠ [지원되지 않음, 해결 방법, 샘플](#dictionary-with-non-string-key) | | 다형 serialization                             | ⚠ [지원되지 않음, 해결 방법, 샘플](#polymorphic-serialization) | | 다형 deserialization                           | ⚠ [지원되지 않음, 해결 방법, 샘플](#polymorphic-deserialization) | | 유추 형식을 `object` 속성으로 역직렬화      | ⚠ [지원되지 않음, 해결 방법, 샘플](#deserialization-of-object-properties) | | JSON `null` 리터럴을 null을 허용하지 않는 값 형식으로 역직렬화 | ⚠ [지원되지 않음, 해결 방법, 샘플](#deserialize-null-to-non-nullable-type) | | 변경할 수 없는 클래스 및 구조체로 역직렬화          | ⚠ [지원되지 않음, 해결 방법, 샘플](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` 특성                         | ⚠ [지원되지 않음, 해결 방법, 샘플](#specify-constructor-to-use) | | `[JsonProperty]` 특성에 대한 `Required` 설정        | ⚠ [지원되지 않음, 해결 방법, 샘플](#required-properties) | | `[JsonProperty]` 특성에 대한 `NullValueHandling` 설정 | ⚠ [지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property)  | | `[JsonProperty]` 특성에 대한 `DefaultValueHandling` 설정 | ⚠ [지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property)  | | `DefaultValueHandling` 전역 설정                 | ⚠ [지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property) | | 속성을 제외하는 `DefaultContractResolver`       | ⚠ [지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`, `DateFormatString` 설정   | ⚠ [지원되지 않음, 해결 방법, 샘플](#specify-date-format) | | 콜백                                             | ⚠ [지원되지 않음, 해결 방법, 샘플](#callbacks) | | public 및 비-public 필드 지원              | ⚠ [지원되지 않음, 해결 방법](#public-and-non-public-fields) | | internal/private 속성 setter 및 getter 지원 | ⚠ [지원되지 않음, 해결 방법](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` 메서드                   | ⚠ [지원되지 않음, 해결 방법](#populate-existing-objects) | | `ObjectCreationHandling` 전역 설정               | ⚠ [지원되지 않음, 해결 방법](#reuse-rather-than-replace-properties) | | setter 없이 컬렉션에 추가                    | ⚠ [지원되지 않음, 해결 방법](#add-to-collections-without-setters) | | `PreserveReferencesHandling` 전역 설정           | ❌ [지원되지 않음](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` 전역 설정                | ❌ [지원되지 않음](#preserve-object-references-and-handle-loops) | | `System.Runtime.Serialization` 특성 지원 | ❌ [지원되지 않음](#systemruntimeserialization-attributes) | | `MissingMemberHandling` 전역 설정                | ❌ [지원되지 않음](#missingmemberhandling) | | 따옴표 없는 속성 이름 허용                   | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) | | 문자열 값 주변에 작은따옴표 허용              | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) | | 문자열 속성에 문자열이 아닌 JSON 값 허용    | ❌ [지원되지 않음](#non-string-values-for-string-properties) |</span><span class="sxs-lookup"><span data-stu-id="0f1ff-241">---------------| | Case-insensitive deserialization by default           | ✔️ [PropertyNameCaseInsensitive global setting](#case-insensitive-deserialization) | | Camel-case property names                             | ✔️ [PropertyNamingPolicy global setting](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Minimal character escaping                            | ✔️ [Strict character escaping, configurable](#minimal-character-escaping) | | `NullValueHandling.Ignore` global setting             | ✔️ [IgnoreNullValues global option](system-text-json-how-to.md#exclude-all-null-value-properties) | | Allow comments                                        | ✔️ [ReadCommentHandling global setting](#comments) | | Allow trailing commas                                 | ✔️ [AllowTrailingCommas global setting](#trailing-commas) | | Custom converter registration                         | ✔️ [Order of precedence differs](#converter-registration-precedence) | | No maximum depth by default                           | ✔️ [Default maximum depth 64, configurable](#maximum-depth) | | Support for a broad range of types                    | ⚠️ [Some types require custom converters](#types-without-built-in-support) | | Deserialize strings as numbers                        | ⚠️ [Not supported, workaround, sample](#quoted-numbers) | | Deserialize `Dictionary` with non-string key          | ⚠️ [Not supported, workaround, sample](#dictionary-with-non-string-key) | | Polymorphic serialization                             | ⚠️ [Not supported, workaround, sample](#polymorphic-serialization) | | Polymorphic deserialization                           | ⚠️ [Not supported, workaround, sample](#polymorphic-deserialization) | | Deserialize inferred type to `object` properties      | ⚠️ [Not supported, workaround, sample](#deserialization-of-object-properties) | | Deserialize JSON `null` literal to non-nullable value types | ⚠️ [Not supported, workaround, sample](#deserialize-null-to-non-nullable-type) | | Deserialize to immutable classes and structs          | ⚠️ [Not supported, workaround, sample](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` attribute                         | ⚠️ [Not supported, workaround, sample](#specify-constructor-to-use) | | `Required` setting on `[JsonProperty]` attribute        | ⚠️ [Not supported, workaround, sample](#required-properties) | | `NullValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` global setting                 | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DefaultContractResolver` to exclude properties       | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`, `DateFormatString` settings   | ⚠️ [Not supported, workaround, sample](#specify-date-format) | | Callbacks                                             | ⚠️ [Not supported, workaround, sample](#callbacks) | | Support for public and non-public fields              | ⚠️ [Not supported, workaround](#public-and-non-public-fields) | | Support for internal and private property setters and getters | ⚠️ [Not supported, workaround](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` method                   | ⚠️ [Not supported, workaround](#populate-existing-objects) | | `ObjectCreationHandling` global setting               | ⚠️ [Not supported, workaround](#reuse-rather-than-replace-properties) | | Add to collections without setters                    | ⚠️ [Not supported, workaround](#add-to-collections-without-setters) | | `PreserveReferencesHandling` global setting           | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` global setting                | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | Support for `System.Runtime.Serialization` attributes | ❌ [Not supported](#systemruntimeserialization-attributes) | | `MissingMemberHandling` global setting                | ❌ [Not supported](#missingmemberhandling) | | Allow property names without quotes                   | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow single quotes around string values              | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow non-string JSON values for string properties    | ❌ [Not supported](#non-string-values-for-string-properties) |</span></span>

<span data-ttu-id="0f1ff-242">이 목록은 `Newtonsoft.Json` 기능의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-242">This is not an exhaustive list of `Newtonsoft.Json` features.</span></span> <span data-ttu-id="0f1ff-243">이 목록에는 [GitHub 이슈](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 또는 [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) 게시물에 요청된 여러 시나리오가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-243">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span> <span data-ttu-id="0f1ff-244">여기에 나열된 시나리오 중에서 현재 샘플 코드가 없는 시나리오에 대한 해결 방법을 구현하셨으며 그 방법을 공유하려는 분들은 이 페이지 하단의 **피드백** 섹션에서 **이 페이지**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-244">If you implement a workaround for one of the scenarios listed here that doesn't currently have sample code, and if you want to share your solution, select **This page** in the **Feedback** section at the bottom of this page.</span></span> <span data-ttu-id="0f1ff-245">그러면 이 설명서의 GitHub 리포지토리에 이슈가 작성되고 이 페이지의 **피드백** 섹션에도 이슈가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-245">That creates an issue in this documentation's GitHub repo and lists it in the **Feedback** section on this page too.</span></span>

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="0f1ff-246">기본 JsonSerializer와 Newtonsoft.Json의 동작 차이</span><span class="sxs-lookup"><span data-stu-id="0f1ff-246">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="0f1ff-247"><xref:System.Text.Json>은 기본적으로 엄격하며, 호출자를 대신하여 추측하거나 해석하는 것을 금지하고 결정적 동작을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-247"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="0f1ff-248">이 라이브러리는 성능과 보안을 위해 의도적으로 이렇게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-248">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="0f1ff-249">`Newtonsoft.Json`은 기본적으로 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-249">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="0f1ff-250">이러한 기본적인 디자인의 차이로 인해 기본 동작에서 다음과 같은 여러 가지 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-250">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="0f1ff-251">대/소문자를 구분하지 않는 역직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-251">Case-insensitive deserialization</span></span>

<span data-ttu-id="0f1ff-252">역직렬화를 수행하는 동안 `Newtonsoft.Json`은 기본적으로 대/소문자를 구분하지 않는 속성 이름을 매칭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-252">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="0f1ff-253"><xref:System.Text.Json>은 기본적으로 대/소문자를 구분하며, 이 방법은 매칭을 정확히 수행하기 때문에 보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-253">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="0f1ff-254">대/소문자를 구분하지 않는 매칭 방법에 대한 자세한 내용은 [대/소문자를 구분하지 않는 속성 매칭](system-text-json-how-to.md#case-insensitive-property-matching)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-254">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="0f1ff-255">ASP.NET Core를 사용하여 간접적으로 `System.Text.Json`을 사용하는 경우 `Newtonsoft.Json`과 같은 동작을 얻기 위해 아무것도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-255">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="0f1ff-256">ASP.NET Core는 `System.Text.Json`을 사용할 때 [카멜식 대/소문자 구분 속성 이름](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) 및 대/소문자를 구분하지 않는 매칭에 대한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-256">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="minimal-character-escaping"></a><span data-ttu-id="0f1ff-257">최소 문자 이스케이프</span><span class="sxs-lookup"><span data-stu-id="0f1ff-257">Minimal character escaping</span></span>

<span data-ttu-id="0f1ff-258">직렬화할 때 `Newtonsoft.Json`은 문자를 이스케이프하지 않고 허용하는 것에 대해 비교적 관대합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-258">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="0f1ff-259">즉, 문자를 `\uxxxx`로 바꾸지 않으며, 여기서 `xxxx`는 문자의 코드 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-259">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="0f1ff-260">문자를 이스케이프할 때는 문자 앞에 `\`를 내보냅니다. 예를 들어 `"`는 `\"`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-260">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="0f1ff-261"><xref:System.Text.Json>은 XSS(교차 사이트 스크립팅) 또는 정보 공개 공격에 대한 심층 방어를 제공하기 위해 기본적으로 더 많은 문자를 이스케이프하며, 그러기 위해 6문자 시퀀스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-261"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="0f1ff-262">`System.Text.Json`은 기본적으로 ASCII가 아닌 모든 문자를 이스케이프하므로, `Newtonsoft.Json`에서 `StringEscapeHandling.EscapeNonAscii`를 사용 중이라면 아무것도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-262">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="0f1ff-263">또한 `System.Text.Json`은 기본적으로 HTML 구분 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-263">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="0f1ff-264">기본 `System.Text.Json` 동작을 재정의하는 방법에 대한 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-264">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="comments"></a><span data-ttu-id="0f1ff-265">주석</span><span class="sxs-lookup"><span data-stu-id="0f1ff-265">Comments</span></span>

<span data-ttu-id="0f1ff-266">역직렬화할 때 `Newtonsoft.Json`은 기본적으로 JSON의 주석을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-266">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="0f1ff-267">[RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에 주석이 포함되지 않기 때문에 <xref:System.Text.Json>은 기본적으로 주석에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-267">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="0f1ff-268">주석을 허용하는 방법에 대한 자세한 내용은 [주석과 후행 쉼표 허용](system-text-json-how-to.md#allow-comments-and-trailing-commas)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-268">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="0f1ff-269">후행 쉼표</span><span class="sxs-lookup"><span data-stu-id="0f1ff-269">Trailing commas</span></span>

<span data-ttu-id="0f1ff-270">역직렬화할 때 `Newtonsoft.Json`은 기본적으로 후행 쉼표를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-270">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="0f1ff-271">또한 여러 개의 후행 쉼표를 무시합니다(예: `[{"Color":"Red"},{"Color":"Green"},,]`).</span><span class="sxs-lookup"><span data-stu-id="0f1ff-271">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="0f1ff-272">[RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 후행 쉼표를 허용하지 않기 때문에 <xref:System.Text.Json>은 기본적으로 후행 쉼표에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-272">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="0f1ff-273">`System.Text.Json`에서 후행 쉼표를 허용하게 만드는 방법은 [주석과 후행 쉼표 허용](system-text-json-how-to.md#allow-comments-and-trailing-commas)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-273">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="0f1ff-274">후행 쉼표를 여러 개 허용하는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-274">There's no way to allow multiple trailing commas.</span></span>

### <a name="converter-registration-precedence"></a><span data-ttu-id="0f1ff-275">변환기 등록 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0f1ff-275">Converter registration precedence</span></span>

<span data-ttu-id="0f1ff-276">사용자 지정 변환기에 대한 `Newtonsoft.Json` 등록 우선 순위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-276">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="0f1ff-277">속성의 특성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-277">Attribute on property</span></span>
* <span data-ttu-id="0f1ff-278">형식의 특성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-278">Attribute on type</span></span>
* <span data-ttu-id="0f1ff-279">[변환기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="0f1ff-279">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="0f1ff-280">이 순서는 형식 수준에서 특성을 적용하여 등록된 변환기가 `Converters` 컬렉션의 사용자 지정 변환기를 재정의한다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-280">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="0f1ff-281">두 등록 모두 속성 수준에서 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-281">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="0f1ff-282">사용자 지정 변환기에 대한 <xref:System.Text.Json> 등록 우선 순위는 다음과 같이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-282">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="0f1ff-283">속성의 특성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-283">Attribute on property</span></span>
* <span data-ttu-id="0f1ff-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션</span><span class="sxs-lookup"><span data-stu-id="0f1ff-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="0f1ff-285">형식의 특성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-285">Attribute on type</span></span>

<span data-ttu-id="0f1ff-286">여기서 `Converters` 컬렉션의 사용자 지정 변환기가 형식 수준에서 특성을 재정의한다는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-286">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="0f1ff-287">이 우선 순위 순서의 숨은 의도는 런타임 변경이 디자인 타임 선택 항목을 재정의하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-287">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="0f1ff-288">우선 순위를 변경할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-288">There's no way to change the precedence.</span></span>

<span data-ttu-id="0f1ff-289">사용자 지정 변환기 등록에 대한 자세한 내용은 [사용자 지정 변환기 등록](system-text-json-converters-how-to.md#register-a-custom-converter)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-289">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="0f1ff-290">최대 깊이</span><span class="sxs-lookup"><span data-stu-id="0f1ff-290">Maximum depth</span></span>

<span data-ttu-id="0f1ff-291">`Newtonsoft.Json`은 기본적으로 최대 깊이 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-291">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="0f1ff-292"><xref:System.Text.Json>의 경우 기본 제한은 64이며, <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>을 설정하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-292">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="0f1ff-293">JSON 문자열(속성 이름 및 문자열 값)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-293">JSON strings (property names and string values)</span></span>

<span data-ttu-id="0f1ff-294">역직렬화할 때 `Newtonsoft.Json`은 큰따옴표/작은따옴표로 묶은 속성 이름 또는 따옴표 없는 속성 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-294">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="0f1ff-295">큰따옴표 또는 작은따옴표로 묶은 문자열 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-295">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="0f1ff-296">예를 들어 `Newtonsoft.Json`은 다음 JSON을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-296">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="0f1ff-297">`System.Text.Json`은 큰따옴표로 묶은 속성 이름과 문자열 값만 허용합니다. [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 이 형식을 요구하며 유일하게 유효한 JSON으로 간주되는 형식이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-297">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="0f1ff-298">작은따옴표로 묶은 값은 다음 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-298">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="0f1ff-299">문자열 속성에 문자열이 아닌 값 허용</span><span class="sxs-lookup"><span data-stu-id="0f1ff-299">Non-string values for string properties</span></span>

<span data-ttu-id="0f1ff-300">`Newtonsoft.Json`은 형식 문자열의 속성으로 역직렬화할 때 숫자 또는 리터럴 `true` 및 `false`처럼 문자열이 아닌 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-300">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="0f1ff-301">아래는 `Newtonsoft.Json`이 성공적으로 다음 클래스로 역직렬화하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-301">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

<span data-ttu-id="0f1ff-302">`System.Text.Json`은 문자열이 아닌 값을 문자열 속성으로 역직렬화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-302">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="0f1ff-303">문자열 필드에 대해 문자열이 아닌 값을 받으면 다음 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-303">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="0f1ff-304">해결 방법이 필요한 JsonSerializer를 사용하는 시나리오</span><span class="sxs-lookup"><span data-stu-id="0f1ff-304">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="0f1ff-305">다음 시나리오는 기본 제공 기능에서 지원되지 않지만, 해결이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-305">The following scenarios aren't supported by built-in functionality, but workarounds are possible.</span></span> <span data-ttu-id="0f1ff-306">해결 방법은 [사용자 지정 변환기](system-text-json-converters-how-to.md)이며, 사용자 지정 변환기는 `Newtonsoft.Json` 기능과의 완전한 패리티를 제공하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-306">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="0f1ff-307">그 중 일부는 샘플 코드가 예제로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-307">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="0f1ff-308">이러한 `Newtonsoft.Json` 기능을 사용하는 경우 마이그레이션을 수행하려면 .NET 개체 모델 또는 기타 코드 변경 내용을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-308">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="0f1ff-309">기본적으로 지원되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="0f1ff-309">Types without built-in support</span></span>

<span data-ttu-id="0f1ff-310"><xref:System.Text.Json>은 기본적으로 다음 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-310"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="0f1ff-311"><xref:System.Data.DataTable> 및 관련 형식</span><span class="sxs-lookup"><span data-stu-id="0f1ff-311"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="0f1ff-312">[구분된 공용 구조체](../../fsharp/language-reference/discriminated-unions.md), [레코드 형식](../../fsharp/language-reference/records.md), [익명 레코드 형식](../../fsharp/language-reference/anonymous-records.md) 등의 F# 형식</span><span class="sxs-lookup"><span data-stu-id="0f1ff-312">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="0f1ff-313"><xref:System.ValueTuple> 및 관련 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="0f1ff-313"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="0f1ff-314">기본적으로 지원되지 않는 형식에 대한 사용자 지정 변환기를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-314">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="0f1ff-315">따옴표 붙은 숫자</span><span class="sxs-lookup"><span data-stu-id="0f1ff-315">Quoted numbers</span></span>

<span data-ttu-id="0f1ff-316">`Newtonsoft.Json`은 JSON 문자열로 표시되는(따옴표로 묶은) 숫자를 직렬화 또는 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-316">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="0f1ff-317">예를 들어 `{"DegreesCelsius":23}` 대신 `{"DegreesCelsius":"23"}`을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-317">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="0f1ff-318"><xref:System.Text.Json>에서 해당 동작을 사용하도록 설정하려면 다음 예제와 같이 사용자 지정 변환기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-318">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="0f1ff-319">이 변환기는 다음과 같이 `long`으로 정의된 속성을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-319">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="0f1ff-320">속성을 JSON 문자열로 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-320">It serializes them as JSON strings.</span></span>
* <span data-ttu-id="0f1ff-321">역직렬화할 때 JSON 숫자 및 따옴표 안의 숫자를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-321">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

<span data-ttu-id="0f1ff-322">개별 `long` 속성에 대한 [특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-322">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="0f1ff-323">키가 문자열이 아닌 사전</span><span class="sxs-lookup"><span data-stu-id="0f1ff-323">Dictionary with non-string key</span></span>

<span data-ttu-id="0f1ff-324">`Newtonsoft.Json`은 `Dictionary<TKey, TValue>` 형식의 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-324">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="0f1ff-325"><xref:System.Text.Json>의 사전 컬렉션에 대한 기본 지원은 `Dictionary<string, TValue>`로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-325">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="0f1ff-326">즉, 키는 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-326">That is, the key must be a string.</span></span>

<span data-ttu-id="0f1ff-327">정수 또는 다른 형식의 키를 사용하는 사전을 지원하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)의 예제와 같은 변환기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-327">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="0f1ff-328">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-328">Polymorphic serialization</span></span>

<span data-ttu-id="0f1ff-329">`Newtonsoft.Json`은 다형 직렬화를 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-329">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="0f1ff-330"><xref:System.Text.Json>의 제한 다형 직렬화 기능에 대한 자세한 내용은 [파생 클래스의 속성 직렬화](system-text-json-how-to.md#serialize-properties-of-derived-classes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-330">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="0f1ff-331">해당 문서에 설명된 해결 방법은 `object` 형식으로 파생 클래스를 포함할 수 있는 속성을 정의하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-331">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="0f1ff-332">이 방법을 사용할 수 없는 경우 다른 옵션은 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같이 전체 상속 형식 계층 구조에 대한 `Write` 메서드를 사용하여 변환기를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-332">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="0f1ff-333">다형 역직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-333">Polymorphic deserialization</span></span>

<span data-ttu-id="0f1ff-334">`Newtonsoft.Json`에는 직렬화하는 동안 JSON에 형식 이름 메타데이터를 추가하는 `TypeNameHandling` 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-334">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="0f1ff-335">이 설정은 역직렬화하는 동안 메타데이터를 사용하여 다형 역직렬화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-335">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="0f1ff-336"><xref:System.Text.Json>은 제한된 범위의 [다형 직렬화](system-text-json-how-to.md#serialize-properties-of-derived-classes)를 수행할 수 있지만 다형 역직렬화는 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-336"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="0f1ff-337">다형 역직렬화를 지원하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같은 변환기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-337">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="0f1ff-338">개체 속성 역직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-338">Deserialization of object properties</span></span>

<span data-ttu-id="0f1ff-339">`Newtonsoft.Json`은 <xref:System.Object>로 역직렬화할 때 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-339">When `Newtonsoft.Json` deserializes to <xref:System.Object>, it:</span></span>

* <span data-ttu-id="0f1ff-340">JSON 페이로드의 기본 값 형식(`null` 제외)을 유추하고 저장된 `string`, `long`, `double`, `boolean` 또는 `DateTime`을 boxed 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-340">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="0f1ff-341">*기본 값*은 JSON 숫자, 문자열, `true`, `false`, `null` 등의 단일 JSON 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-341">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="0f1ff-342">JSON 페이로드의 복합 값에 대한 `JObject` 또는 `JArray`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-342">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="0f1ff-343">*복합 값*은 중괄호(`{}`) 안에 있는 JSON 키-값 쌍 컬렉션 또는 대괄호(`[]`) 안에 있는 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-343">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="0f1ff-344">중괄호 또는 대괄호 안에 있는 속성과 값이 추가 속성 또는 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-344">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="0f1ff-345">페이로드에 `null` JSON 리터럴이 있으면 null 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-345">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="0f1ff-346"><xref:System.Text.Json>은 <xref:System.Object>로 역직렬화할 때마다 기본 값과 복합 값 모두에 대한 boxed `JsonElement`를 저장하며, 다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-346"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values whenever deserializing to <xref:System.Object>, for example:</span></span>

* <span data-ttu-id="0f1ff-347">`object` 속성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-347">An `object` property.</span></span>
* <span data-ttu-id="0f1ff-348">`object` 사전 값</span><span class="sxs-lookup"><span data-stu-id="0f1ff-348">An `object` dictionary value.</span></span>
* <span data-ttu-id="0f1ff-349">`object` 배열 값</span><span class="sxs-lookup"><span data-stu-id="0f1ff-349">An `object` array value.</span></span>
* <span data-ttu-id="0f1ff-350">루트 `object`</span><span class="sxs-lookup"><span data-stu-id="0f1ff-350">A root `object`.</span></span>

<span data-ttu-id="0f1ff-351">그러나 페이로드에 `null` JSON 리터럴이 있으면 `System.Text.Json`은 `null`을 `Newtonsoft.Json`과 같은 방법으로 처리하고 null 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-351">However, `System.Text.Json` treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="0f1ff-352">`object` 속성에 대한 형식 유추를 구현하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)의 예제와 같은 변환기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-352">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="0f1ff-353">null을 허용하지 않는 형식으로 Null 역직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-353">Deserialize null to non-nullable type</span></span>

<span data-ttu-id="0f1ff-354">`Newtonsoft.Json`은 는 다음과 같은 시나리오에서 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-354">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="0f1ff-355">`NullValueHandling`이 `Ignore`로 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="0f1ff-355">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="0f1ff-356">역직렬화를 수행하는 동안 JSON은 null을 허용하지 않는 값 형식에 대해 Null 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-356">During deserialization, the JSON contains a null value for a non-nullable value type.</span></span>

<span data-ttu-id="0f1ff-357">동일한 시나리오에서 <xref:System.Text.Json>은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-357">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="0f1ff-358">(해당하는 null 처리 설정은 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>입니다.)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-358">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="0f1ff-359">대상 형식을 소유하고 있는 경우 가장 좋은 해결 방법은 문제가 되는 속성을 null 허용으로 만드는 것입니다(예를 들어 `int`를 `int?`로 변경).</span><span class="sxs-lookup"><span data-stu-id="0f1ff-359">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="0f1ff-360">또 다른 해결 방법은 `DateTimeOffset` 형식의 Null 값을 처리하는 다음 예제처럼 형식에 대한 변환기를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-360">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="0f1ff-361">[속성에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-361">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="0f1ff-362">**참고:** 위의 변환기는 기본값을 지정하는 POCO를 `Newtonsoft.Json`이 처리하는 방법과는 **다르게 Null 값을 처리**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-362">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="0f1ff-363">예를 들어 다음 코드가 대상 개체를 보여준다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-363">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="0f1ff-364">그리고 앞의 변환기를 사용하여 다음 JSON을 역직렬화한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-364">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="0f1ff-365">역직렬화 후 `Date` 속성에 1/1/0001(`default(DateTimeOffset)`)이 있습니다. 즉, 생성자에서 설정한 값이 덮어쓰기 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-365">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="0f1ff-366">POCO 및 JSON이 동일할 때 `Newtonsoft.Json` 역직렬화 시 `Date` 속성에 1/1/2001이 남습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-366">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="0f1ff-367">변경할 수 없는 클래스 및 구조체로 역직렬화</span><span class="sxs-lookup"><span data-stu-id="0f1ff-367">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="0f1ff-368">`Newtonsoft.Json`은 매개 변수가 있는 생성자를 사용할 수 있기 때문에 변경 불가능한 클래스 및 구조체로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-368">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="0f1ff-369"><xref:System.Text.Json>은 매개 변수 없는 public 생성자만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-369"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="0f1ff-370">사용자 지정 변환기에서 매개 변수가 있는 생성자를 호출하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-370">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="0f1ff-371">다음은 여러 생성자 매개 변수가 있는 변경할 수 없는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-371">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="0f1ff-372">다음은 이 구조체를 직렬화 및 역직렬화하는 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-372">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="0f1ff-373"><xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-373">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="0f1ff-374">개방형 제네릭 속성을 처리하는 비슷한 변환기의 예제는 [키-값 쌍에 사용되는 기본 제공 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-374">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="0f1ff-375">사용할 변환기 지정</span><span class="sxs-lookup"><span data-stu-id="0f1ff-375">Specify constructor to use</span></span>

<span data-ttu-id="0f1ff-376">`Newtonsoft.Json` `[JsonConstructor]` 특성을 사용하면 POCO로 역직렬화할 때 호출할 생성자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-376">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="0f1ff-377"><xref:System.Text.Json>은 매개 변수 없는 생성자만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-377"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="0f1ff-378">사용자 지정 변환기에서 필요한 생성자를 호출하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-378">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="0f1ff-379">예제는 [변경할 수 없는 클래스 및 구조체로 역직렬화](#deserialize-to-immutable-classes-and-structs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-379">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="required-properties"></a><span data-ttu-id="0f1ff-380">필수 속성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-380">Required properties</span></span>

<span data-ttu-id="0f1ff-381">`Newtonsoft.Json`에서 `[JsonProperty]` 특성에 대한 `Required`를 설정하여 속성을 필수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-381">In `Newtonsoft.Json`, you specify that a property is required by setting `Required` on the `[JsonProperty]` attribute.</span></span> <span data-ttu-id="0f1ff-382">필수로 지정된 속성에 대해 JSON에서 값을 받지 못하면 `Newtonsoft.Json`이 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-382">`Newtonsoft.Json` throws an exception if no value is received in the JSON for a property marked as required.</span></span>

<span data-ttu-id="0f1ff-383">대상 형식의 속성 중 하나에 대한 값을 받지 못해도 <xref:System.Text.Json>은 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-383"><xref:System.Text.Json> doesn't throw an exception if no value is received for one of the properties of the target type.</span></span> <span data-ttu-id="0f1ff-384">예를 들어 `WeatherForecast` 클래스가 있는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-384">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="0f1ff-385">다음 JSON은 오류 없이 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-385">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="0f1ff-386">JSON에 `Date` 속성이 없으면 역직렬화가 실패하도록 구성하려면 사용자 지정 변환기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-386">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="0f1ff-387">다음 샘플 변환기 코드는 역직렬화 완료 후 `Date` 속성이 설정되지 않으면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-387">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="0f1ff-388">[POCO 클래스에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-388">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="0f1ff-389">이 패턴을 따르는 경우 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 또는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A>를 재귀적으로 호출할 때 options 개체를 전달하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-389">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="0f1ff-390">options 개체는 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 컬렉션을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-390">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="0f1ff-391">이 개체를 `Serialize` 또는 `Deserialize`에 전달하면 사용자 지정 변환기가 자신을 호출하여 스택 오버플로 예외로 이어지는 무한 루프가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-391">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="0f1ff-392">기본 옵션이 실현 불가능한 경우 필요한 설정을 사용하여 새로운 옵션 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-392">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="0f1ff-393">이 방법은 각각의 새 인스턴스가 독립적으로 캐시하므로 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-393">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="0f1ff-394">위의 변환기 코드는 단순화된 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-394">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="0f1ff-395">특성(예: [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 또는 다른 옵션(예: 사용자 지정 인코더)을 처리해야 하는 경우에는 추가 논리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-395">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="0f1ff-396">또한 예제 코드는 생성자에서 기본값이 설정된 속성을 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-396">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="0f1ff-397">이 방법은 다음과 같은 시나리오를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-397">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="0f1ff-398">JSON에서 속성이 누락되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-398">A property is missing from the JSON.</span></span>
* <span data-ttu-id="0f1ff-399">null을 허용하지 않는 형식의 속성은 JSON에 있지만, 값은 형식에 대한 기본값입니다(`int`는 0).</span><span class="sxs-lookup"><span data-stu-id="0f1ff-399">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="0f1ff-400">null 허용 값 형식의 속성이 JSON에 있지만, 값은 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-400">A property for a nullable value type is present in the JSON, but the value is null.</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="0f1ff-401">조건부로 속성 무시</span><span class="sxs-lookup"><span data-stu-id="0f1ff-401">Conditionally ignore a property</span></span>

<span data-ttu-id="0f1ff-402">`Newtonsoft.Json`은 직렬화 또는 역직렬화에서 속성을 조건부로 무시하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-402">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="0f1ff-403">`DefaultContractResolver`를 사용하면 임의의 조건에 따라 포함하거나 제외할 속성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-403">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span>
* <span data-ttu-id="0f1ff-404">`JsonSerializerSettings`의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용하면 모든 Null 값 또는 기본값 속성을 무시하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-404">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="0f1ff-405">`[JsonProperty]` 특성의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용하면 Null 또는 기본값으로 설정된 경우에 무시할 개별 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-405">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="0f1ff-406"><xref:System.Text.Json>은 직렬화하는 동안 다음과 같은 방법으로 속성을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-406"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="0f1ff-407">속성의 [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) 특성은 직렬화하는 동안 JSON에서 속성을 생략하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-407">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="0f1ff-408">[IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) 글로벌 옵션을 사용하면 모든 Null 값 속성을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-408">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="0f1ff-409">[IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) 글로벌 옵션을 사용하면 모든 읽기 전용 속성을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-409">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="0f1ff-410">이러한 옵션은 다음 기능이 **없습니다**.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-410">These options **don't** let you:</span></span>

* <span data-ttu-id="0f1ff-411">형식의 기본값이 있는 모든 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-411">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="0f1ff-412">형식의 기본값이 있는 속성 중 선택한 일부를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-412">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="0f1ff-413">선택한 속성의 값이 Null이면 해당 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-413">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="0f1ff-414">런타임에 평가되는 임의의 조건을 기준으로 선택한 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-414">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span>

<span data-ttu-id="0f1ff-415">이 기능을 사용하려면 사용자 지정 변환기를 작성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-415">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="0f1ff-416">다음은 이 방법을 보여주는 샘플 POCO 및 사용자 지정 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-416">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="0f1ff-417">`Summary` 속성의 값이 Null, 빈 문자열 또는 "N/A"이면 이 변환기는 직렬화에서 이 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-417">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span>

<span data-ttu-id="0f1ff-418">[클래스에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-418">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="0f1ff-419">이 방법은 다음과 같은 경우에 추가 논리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-419">This approach requires additional logic if:</span></span>

* <span data-ttu-id="0f1ff-420">POCO에 복합 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-420">The POCO includes complex properties.</span></span>
* <span data-ttu-id="0f1ff-421">`[JsonIgnore]`, 옵션(예: 사용자 지정 인코더) 같은 특성을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-421">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="0f1ff-422">날짜 형식 지정</span><span class="sxs-lookup"><span data-stu-id="0f1ff-422">Specify date format</span></span>

<span data-ttu-id="0f1ff-423">`Newtonsoft.Json`은 `DateTime` 및 `DateTimeOffset` 형식의 속성 직렬화 및 역직렬화 방식을 여러 가지 방법으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-423">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="0f1ff-424">`DateTimeZoneHandling` 설정을 사용하여 모든 `DateTime` 값을 UTC 날짜로 직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-424">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="0f1ff-425">`DateFormatString` 설정 및 `DateTime` 변환기를 사용하여 날짜 문자열의 형식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-425">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="0f1ff-426"><xref:System.Text.Json>에서 기본적으로 지원되는 유일한 형식은 널리 사용되고 모호하지 않고 라운드트립을 정확하게 수행하는 ISO 8601-1:2019입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-426">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="0f1ff-427">다른 형식을 사용하려면 사용자 지정 변환기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-427">To use any other format, create a custom converter.</span></span> <span data-ttu-id="0f1ff-428">자세한 내용은 [System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-428">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="callbacks"></a><span data-ttu-id="0f1ff-429">콜백</span><span class="sxs-lookup"><span data-stu-id="0f1ff-429">Callbacks</span></span>

<span data-ttu-id="0f1ff-430">`Newtonsoft.Json`은 다음과 같이 직렬화 또는 역직렬화 프로세스의 여러 지점에서 사용자 지정 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-430">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="0f1ff-431">OnDeserializing(개체 역직렬화를 시작할 때)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-431">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="0f1ff-432">OnDeserialized(개체 역직렬화가 완료될 때)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-432">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="0f1ff-433">OnSerializing(개체 직렬화를 시작할 때)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-433">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="0f1ff-434">OnSerialized(개체 직렬화가 완료될 때)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-434">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="0f1ff-435"><xref:System.Text.Json>에서는 사용자 지정 변환기를 작성하여 콜백을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-435">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="0f1ff-436">다음 예제에서는 POCO용 사용자 지정 변환기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-436">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="0f1ff-437">이 변환기에는 `Newtonsoft.Json` 콜백에 해당하는 각 지점에 메시지를 표시하는 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-437">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="0f1ff-438">[클래스에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-438">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="0f1ff-439">이전 샘플을 따르는 사용자 지정 변환기를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-439">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="0f1ff-440">`OnDeserializing` 코드는 새 POCO 인스턴스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-440">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="0f1ff-441">역직렬화를 시작할 때 새 POCO 인스턴스를 조작하려면 이 코드를 POCO 생성자에 배치하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-441">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="0f1ff-442">`Serialize` 또는 `Deserialize`를 재귀적으로 호출할 때 options 개체를 전달하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-442">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="0f1ff-443">options 개체는 `Converters` 컬렉션을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-443">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="0f1ff-444">이 개체를 `Serialize` 또는 `Deserialize`에 전달하면 변환기가 사용되어 스택 오버플로 예외로 이어지는 무한 루프가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-444">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="0f1ff-445">public 및 비-public 필드</span><span class="sxs-lookup"><span data-stu-id="0f1ff-445">Public and non-public fields</span></span>

<span data-ttu-id="0f1ff-446">`Newtonsoft.Json`은 속성뿐 아니라 필드까지 직렬화 및 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-446">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="0f1ff-447"><xref:System.Text.Json>은 public 속성에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-447"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="0f1ff-448">사용자 지정 변환기는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-448">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="0f1ff-449">Internal/private 속성 setter 및 getter</span><span class="sxs-lookup"><span data-stu-id="0f1ff-449">Internal and private property setters and getters</span></span>

<span data-ttu-id="0f1ff-450">`Newtonsoft.Json`은 `JsonProperty` 특성을 통해 private/internal 속성 setter 및 getter를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-450">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="0f1ff-451"><xref:System.Text.Json>은 public setter만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-451"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="0f1ff-452">사용자 지정 변환기는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-452">Custom converters can provide this functionality.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="0f1ff-453">기존 개체 채우기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-453">Populate existing objects</span></span>

<span data-ttu-id="0f1ff-454">`Newtonsoft.Json`의 `JsonConvert.PopulateObject` 메서드는 새 인스턴스를 만드는 대신 JSON 문서를 클래스의 기존 인스턴스로 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-454">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="0f1ff-455"><xref:System.Text.Json>은 항상 매개 변수 없는 기본 public 생성자를 사용하여 대상 형식의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-455"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="0f1ff-456">사용자 지정 변환기는 기존 인스턴스로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-456">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="0f1ff-457">속성을 바꾸지 않고 재사용</span><span class="sxs-lookup"><span data-stu-id="0f1ff-457">Reuse rather than replace properties</span></span>

<span data-ttu-id="0f1ff-458">`Newtonsoft.Json` `ObjectCreationHandling` 설정을 사용하면 역직렬화 중에 속성의 개체를 바꾸지 않고 재사용하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-458">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="0f1ff-459"><xref:System.Text.Json>은 항상 속성의 개체를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-459"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="0f1ff-460">사용자 지정 변환기는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-460">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="0f1ff-461">setter 없이 컬렉션에 추가</span><span class="sxs-lookup"><span data-stu-id="0f1ff-461">Add to collections without setters</span></span>

<span data-ttu-id="0f1ff-462">역직렬화를 수행하는 동안 `Newtonsoft.Json`은 속성에 setter가 없는 경우에도 개체를 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-462">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="0f1ff-463"><xref:System.Text.Json>은 setter가 없는 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-463"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="0f1ff-464">사용자 지정 변환기는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-464">Custom converters can provide this functionality.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="0f1ff-465">JsonSerializer가 현재 지원하지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="0f1ff-465">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="0f1ff-466">다음 시나리오는 해결 방법이 실용적이지 않거나 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-466">For the following scenarios, workarounds are not practical or possible.</span></span> <span data-ttu-id="0f1ff-467">이러한 `Newtonsoft.Json` 기능을 사용하는 경우 중요한 변경 없이는 마이그레이션을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-467">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="0f1ff-468">개체 참조 유지 및 루프 처리</span><span class="sxs-lookup"><span data-stu-id="0f1ff-468">Preserve object references and handle loops</span></span>

<span data-ttu-id="0f1ff-469">기본적으로 `Newtonsoft.Json`은 값으로 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-469">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="0f1ff-470">예를 들어 개체에 두 개의 속성이 있고 두 속성은 동일한 `Person` 개체에 대한 참조를 포함하는 경우 해당 `Person` 개체의 속성 값이 JSON에서 중복됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-470">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="0f1ff-471">`Newtonsoft.Json`에는 참조로 직렬화할 수 있는 `JsonSerializerSettings`에 대한 `PreserveReferencesHandling` 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-471">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="0f1ff-472">첫 번째 `Person` 개체에 대해 만든 JSON에 식별자 메타데이터가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-472">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="0f1ff-473">두 번째 `Person` 개체에 대해 만든 JSON에는 속성 값 대신 해당 식별자에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-473">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="0f1ff-474">`Newtonsoft.Json`에는 예외를 throw하는 대신 순환 참조를 무시할 수 있는 `ReferenceLoopHandling` 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-474">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="0f1ff-475"><xref:System.Text.Json>은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-475"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="0f1ff-476">System.Runtime.Serialization 특성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-476">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="0f1ff-477"><xref:System.Text.Json>은 `DataMemberAttribute` 및 `IgnoreDataMemberAttribute`와 같은 `System.Runtime.Serialization` 네임스페이스의 특성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-477"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="0f1ff-478">8진수</span><span class="sxs-lookup"><span data-stu-id="0f1ff-478">Octal numbers</span></span>

<span data-ttu-id="0f1ff-479">`Newtonsoft.Json`은 선행 0이 있는 숫자를 8진수로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-479">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="0f1ff-480">[RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 선행 0을 허용하지 않으므로 <xref:System.Text.Json>은 선행 0을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-480"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="0f1ff-481">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="0f1ff-481">MissingMemberHandling</span></span>

<span data-ttu-id="0f1ff-482">JSON이 대상 형식에 없는 속성을 포함하는 경우 역직렬화 중에 예외를 throw하도록 `Newtonsoft.Json`을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-482">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="0f1ff-483"><xref:System.Text.Json>은 [[JsonExtensionData] 특성](system-text-json-how-to.md#handle-overflow-json)를 사용하는 경우를 제외하고 JSON의 추가 속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-483"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="0f1ff-484">누락된 멤버 기능에 대한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-484">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="0f1ff-485">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="0f1ff-485">TraceWriter</span></span>

<span data-ttu-id="0f1ff-486">`Newtonsoft.Json`은 직렬화 또는 역직렬화에서 생성된 로그를 살펴보는 `TraceWriter`를 사용하여 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-486">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="0f1ff-487"><xref:System.Text.Json>은 로깅을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-487"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="0f1ff-488">JsonDocument 및 JsonElement과 JToken(예: JObject, JArray)의 비교</span><span class="sxs-lookup"><span data-stu-id="0f1ff-488">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="0f1ff-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 기존 JSON 페이로드의 **읽기 전용** DOM(문서 개체 모델)을 구문 분석하고 빌드하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="0f1ff-490">DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-490">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="0f1ff-491">페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-491">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="0f1ff-492">`JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-492">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="0f1ff-493">`JsonDocument`는 <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-493">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="0f1ff-494">JsonDocument는 IDisposable</span><span class="sxs-lookup"><span data-stu-id="0f1ff-494">JsonDocument is IDisposable</span></span>

<span data-ttu-id="0f1ff-495">`JsonDocument`는 데이터의 메모리 내 보기를 풀링된 버퍼에 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-495">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="0f1ff-496">따라서 `Newtonsoft.Json`의 `JObject` 또는 `JArray`와 달리, `JsonDocument` 형식은 `IDisposable`을 구현하며 using 블록 내에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-496">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span>

<span data-ttu-id="0f1ff-497">수명 소유권 및 폐기 책임을 호출자에 양도하려는 경우에만 API에서 `JsonDocument`를 반환하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-497">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="0f1ff-498">대부분의 시나리오에서는 이렇게 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-498">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="0f1ff-499">호출자가 전체 JSON 문서를 사용해야 하는 경우 <xref:System.Text.Json.JsonElement>인 <xref:System.Text.Json.JsonDocument.RootElement%2A>의 <xref:System.Text.Json.JsonElement.Clone%2A>을 반환하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-499">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="0f1ff-500">호출자가 JSON 문서 내의 특정 요소를 사용해야 하는 경우 해당 <xref:System.Text.Json.JsonElement>의 <xref:System.Text.Json.JsonElement.Clone%2A>을 반환하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-500">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="0f1ff-501">`Clone`을 만들지 않고 `RootElement` 또는 하위 요소를 직접 반환하면 해당 소유권을 가진 `JsonDocument`가 폐기된 후에 반환되는 `JsonElement`에 호출자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-501">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="0f1ff-502">다음은 `Clone`을 만들어야 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-502">Here's an example that requires you to make a `Clone`:</span></span>

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

<span data-ttu-id="0f1ff-503">위의 코드에는 `fileName` 속성을 포함하는 `JsonElement`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-503">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="0f1ff-504">위의 코드는 JSON 파일을 열고 `JsonDocument`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-504">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="0f1ff-505">이 메서드는 호출자가 전체 문서를 사용하려 한다고 가정하고 `RootElement`의 `Clone`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-505">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span>

<span data-ttu-id="0f1ff-506">`JsonElement`를 수신하고 하위 요소를 반환하는 경우에는 하위 요소의 `Clone`을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-506">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="0f1ff-507">호출자는 전달된 `JsonElement`가 속한 `JsonDocument`를 활성 상태로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-507">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="0f1ff-508">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0f1ff-508">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="0f1ff-509">JsonDocument는 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="0f1ff-509">JsonDocument is read-only</span></span>

<span data-ttu-id="0f1ff-510"><xref:System.Text.Json> DOM은 JSON 요소를 추가, 제거 또는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-510">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="0f1ff-511">이렇게 설계한 이유는 성능을 향상하고 일반 JSON 페이로드 크기를 구문 분석할 때 할당을 줄이는(즉, 1MB 미만) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-511">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="0f1ff-512">현재 시나리오에서 수정 가능한 DOM을 사용하는 경우 다음 해결 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-512">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="0f1ff-513">`JsonDocument`를 처음부터 새로 빌드하려면(즉, `Parse` 메서드에 기존 JSON 페이로드를 전달하지 않고) `Utf8JsonWriter`를 사용하여 JSON 텍스트를 작성하고 해당 출력을 구문 분석하여 새 `JsonDocument`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-513">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="0f1ff-514">기존 `JsonDocument`를 수정하려면 이를 사용하여 JSON 텍스트를 작성하고, 작성하는 동안 필요한 대로 변경하고, 해당 출력을 구문 분석하여 새 `JsonDocument`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-514">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="0f1ff-515">`Newtonsoft.Json`의 `JObject.Merge` 또는 `JContainer.Merge` API에 해당하는 기존 JSON 문서를 병합하려면 [이 GitHub 이슈](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-515">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="0f1ff-516">JsonElement는 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="0f1ff-516">JsonElement is a union struct</span></span>

<span data-ttu-id="0f1ff-517">`JsonDocument`는 `RootElement`를 JSON 요소를 포함하는 공용 구조체 형식인 <xref:System.Text.Json.JsonElement> 형식의 속성으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-517">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="0f1ff-518">`Newtonsoft.Json`은 `JObject`, `JArray`, `JToken` 등의 전용 계층형 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-518">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="0f1ff-519">`JsonElement`는 검색하고 열거할 수 있으며, `JsonElement`를 사용하여 JSON 요소를 .NET 형식으로 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-519">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="0f1ff-520">하위 요소의 JsonDocument 및 JsonElement를 검색하는 방법</span><span class="sxs-lookup"><span data-stu-id="0f1ff-520">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="0f1ff-521">`Newtonsoft.Json`에서 `JObject` 또는 `JArray`를 사용하여 JSON 토큰을 검색하면 일부 사전을 조회하기 때문에 비교적 속도가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-521">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="0f1ff-522">그에 비해, `JsonElement`에서 검색하려면 속성을 순차적으로 검색해야 하므로 상대적으로 느립니다(예: `TryGetProperty`를 사용하는 경우).</span><span class="sxs-lookup"><span data-stu-id="0f1ff-522">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="0f1ff-523"><xref:System.Text.Json>은 조회 시간이 아닌 초기 구문 분석 시간을 최소화하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-523"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="0f1ff-524">따라서 `JsonDocument` 개체를 검색할 때 성능을 최적화하려면 다음 방법을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-524">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="0f1ff-525">자체적으로 인덱싱 또는 루프를 수행하지 말고 기본 제공 열거자(<xref:System.Text.Json.JsonElement.EnumerateArray%2A> 및 <xref:System.Text.Json.JsonElement.EnumerateObject%2A>)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-525">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="0f1ff-526">`RootElement`를 사용하여 전체 `JsonDocument`의 모든 속성을 순차적으로 검색하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-526">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="0f1ff-527">그 대신, 알려진 JSON 데이터 구조체를 기반으로 중첩된 JSON 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-527">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="0f1ff-528">예를 들어 `Student` 개체에서 `Grade` 속성을 찾고 있는 경우 모든 `JsonElement` 개체를 검색하여 `Grade` 속성을 찾지 말고, `Student` 개체를 반복하여 각 개체의 `Grade` 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-528">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="0f1ff-529">모든 개체를 검색하면 동일한 데이터에 대해 불필요한 전달 과정이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-529">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="0f1ff-530">코드 예제는 [JsonDocument를 사용하여 데이터 액세스](system-text-json-how-to.md#use-jsondocument-for-access-to-data)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-530">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="0f1ff-531">Utf8JsonReader과 JsonTextReader 비교</span><span class="sxs-lookup"><span data-stu-id="0f1ff-531">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="0f1ff-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>은 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)에서 읽어온 UTF-8 인코딩 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="0f1ff-533">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-533">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="0f1ff-534">다음 섹션에서는 `Utf8JsonReader`를 사용할 때 권장하는 프로그래밍 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-534">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="0f1ff-535">Utf8JsonReader는 ref struct</span><span class="sxs-lookup"><span data-stu-id="0f1ff-535">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="0f1ff-536">`Utf8JsonReader` 형식은 *ref struct*이므로 [특정 제한](../../csharp/language-reference/builtin-types/struct.md#ref-struct)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-536">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span></span> <span data-ttu-id="0f1ff-537">예를 들어 ref struct가 아닌 클래스 또는 구조체에 필드로 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-537">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="0f1ff-538">고성능을 얻으려면 출력 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)를 캐시해야 하는데 그 자체가 ref struct이므로 이 형식은 `ref struct`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-538">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="0f1ff-539">또한 이 형식은 상태를 유지하기 때문에 변경 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-539">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="0f1ff-540">따라서 값이 아닌 **ref로 전달**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-540">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="0f1ff-541">값으로 전달하면 구조체 복사본이 생성되고 상태 변경 내용이 호출자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-541">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="0f1ff-542">`Newtonsoft.Json` `JsonTextReader`는 클래스이므로 `Newtonsoft.Json`과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-542">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="0f1ff-543">ref struct 사용 방법에 대한 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../csharp/write-safe-efficient-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-543">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="0f1ff-544">UTF-8 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-544">Read UTF-8 text</span></span>

<span data-ttu-id="0f1ff-545">`Utf8JsonReader`를 사용할 때 가능한 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코딩된 JSON 페이로드를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-545">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="0f1ff-546">코드 예제는 [Utf8JsonReader를 사용하여 데이터 필터링](system-text-json-how-to.md#filter-data-using-utf8jsonreader)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-546">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="0f1ff-547">Stream 또는 PipeReader를 사용하여 읽기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-547">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="0f1ff-548">`Utf8JsonReader`는 UTF-8로 인코딩된 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)에서 읽기(<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-548">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="0f1ff-549">동기 읽기의 경우 스트림의 끝에서 바이트 배열까지 JSON 페이로드를 읽은 후 판독기에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-549">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="0f1ff-550">문자열(UTF-16으로 인코딩되는)에서 읽으려면 <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A>를 호출하여</span><span class="sxs-lookup"><span data-stu-id="0f1ff-550">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="0f1ff-551">먼저 문자열을 UTF-8로 인코딩된 바이트 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-551">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="0f1ff-552">그런 다음, `Utf8JsonReader`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-552">Then pass that to the `Utf8JsonReader`.</span></span>

<span data-ttu-id="0f1ff-553">`Utf8JsonReader`는 입력을 JSON 텍스트로 간주하므로 UTF-8 BOM(바이트 순서 표시)은 잘못된 JSON으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-553">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="0f1ff-554">호출자는 데이터를 판독기에 전달하기 전에 필터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-554">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="0f1ff-555">코드 예제는 [Utf8JsonReader 사용](system-text-json-how-to.md#use-utf8jsonreader)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-555">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="0f1ff-556">다중 세그먼트 ReadOnlySequence를 사용하여 읽기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-556">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="0f1ff-557">JSON 입력이 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)이면 읽기 루프를 진행할 때 판독기의 `ValueSpan` 속성에서 각 JSON 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-557">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="0f1ff-558">그러나 입력이 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)(<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과)인 경우에는 일부 JSON 요소가 `ReadOnlySequence<byte>` 개체의 여러 세그먼트에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-558">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="0f1ff-559">이러한 요소는 연속 메모리 블록의 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-559">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="0f1ff-560">그 대신, 다중 세그먼트 `ReadOnlySequence<byte>`가 입력으로 사용될 때마다 판독기에서 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 속성을 폴링하여 현재 JSON 요소에 액세스하는 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-560">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="0f1ff-561">다음은 권장 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-561">Here's a recommended pattern:</span></span>

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="0f1ff-562">속성 이름 조회에 ValueTextEquals 사용</span><span class="sxs-lookup"><span data-stu-id="0f1ff-562">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="0f1ff-563"><xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>을 사용하여 바이트 단위 비교를 수행하려면 속성 이름 조회를 위한 <xref:System.MemoryExtensions.SequenceEqual%2A>을 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-563">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="0f1ff-564">그 대신 JSON에서 이스케이프된 모든 문자를 이스케이프 해제하는 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>를 호출하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-564">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="0f1ff-565">다음은 "name"이라는 속성을 검색하는 방법을 보여주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-565">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="0f1ff-566">Null 값을 null 허용 값 형식으로 읽기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-566">Read null values into nullable value types</span></span>

<span data-ttu-id="0f1ff-567">`Newtonsoft.Json`은 자동으로 `bool?`를 반환하여 `Null` `TokenType`을 처리하는 `ReadAsBoolean`처럼 <xref:System.Nullable%601>을 반환하는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-567">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="0f1ff-568">기본 제공 `System.Text.Json` API는 null을 허용하지 않는 값 형식만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-568">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="0f1ff-569">예를 들어 <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType>은 `bool`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-569">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="0f1ff-570">JSON에서 `Null`을 발견하면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-570">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="0f1ff-571">다음 예제에서는 Null을 처리하는 두 가지 방법을 보여줍니다. 하나는 null 허용 값 형식을 반환하는 방법이고, 다른 하나는 기본값을 반환하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-571">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a><span data-ttu-id="0f1ff-572">멀티 타기팅</span><span class="sxs-lookup"><span data-stu-id="0f1ff-572">Multi-targeting</span></span>

<span data-ttu-id="0f1ff-573">특정 대상 프레임워크에 `Newtonsoft.Json`을 계속 사용해야 하는 경우 다중 대상을 지정하여 두 가지를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-573">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="0f1ff-574">그러나 이 방법은 간단하지 않으며 `#ifdefs` 및 원본 복제가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-574">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="0f1ff-575">최대한 많은 코드를 공유하는 한 가지 방법은 `Utf8JsonReader` 및 `Newtonsoft.Json` `JsonTextReader` 주위에 `ref struct` 래퍼를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-575">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="0f1ff-576">이 래퍼는 동작의 차이를 격리하면서 공개 노출 영역을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-576">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="0f1ff-577">이렇게 하면 새 형식을 참조로 전달하는 것과 함께 변경 내용을 주로 형식 생성으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-577">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="0f1ff-578">다음은 [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리가 따르는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-578">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="0f1ff-579">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="0f1ff-579">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="0f1ff-580">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="0f1ff-580">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="0f1ff-581">Utf8JsonWriter와 JsonTextWriter 비교</span><span class="sxs-lookup"><span data-stu-id="0f1ff-581">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="0f1ff-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>은 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓸 수 있는 고성능 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="0f1ff-583">writer는 사용자 지정 직렬 변환기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-583">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="0f1ff-584">다음 섹션에서는 `Utf8JsonWriter`를 사용할 때 권장하는 프로그래밍 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-584">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="0f1ff-585">UTF-8 텍스트를 사용하여 쓰기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-585">Write with UTF-8 text</span></span>

<span data-ttu-id="0f1ff-586">`Utf8JsonWriter`를 사용할 때 가능한 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코드된 JSON 페이로드를 쓰세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-586">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="0f1ff-587">UTF-16 문자열 리터럴을 사용하는 대신 <xref:System.Text.Json.JsonEncodedText>를 사용하여 알려진 문자열 속성 이름 및 값을 정적으로 캐시 및 미리 인코딩하여 작성기에 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-587">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="0f1ff-588">이 방법이 UTF-8 바이트 배열을 캐시하여 사용하는 것보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-588">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="0f1ff-589">이 방법은 사용자 지정 이스케이프를 수행해야 하는 경우에도 통합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-589">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="0f1ff-590">`System.Text.Json`은 문자열을 작성하는 동안 이스케이프를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-590">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="0f1ff-591">그러나 사용자 지정 <xref:System.Text.Encodings.Web.JavaScriptEncoder>를 작성기에 옵션으로 전달하거나, 자체 `JavascriptEncoder`를 사용하여 이스케이프를 수행하는 고유한 `JsonEncodedText`를 만든 후 문자열 대신 `JsonEncodedText`를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-591">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="0f1ff-592">자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-592">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="0f1ff-593">원시 값 작성</span><span class="sxs-lookup"><span data-stu-id="0f1ff-593">Write raw values</span></span>

<span data-ttu-id="0f1ff-594">`Newtonsoft.Json` `WriteRawValue` 메서드는 값이 필요한 원시 JSON을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-594">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="0f1ff-595"><xref:System.Text.Json>에는 직접적으로 대응하는 기능이 없지만, 다음과 같은 해결 방법을 통해 유효한 JSON만 작성되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-595"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="0f1ff-596">문자 이스케이프 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0f1ff-596">Customize character escaping</span></span>

<span data-ttu-id="0f1ff-597">`JsonTextWriter`의 [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) 설정은 모든 비 ASCII 문자 **또는** HTML 문자를 이스케이프하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-597">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="0f1ff-598">기본적으로 `Utf8JsonWriter`는 모든 비 ASCII 문자 **및** HTML 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-598">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="0f1ff-599">이러한 이스케이프는 심층 방어 보안을 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-599">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="0f1ff-600">다른 이스케이프 정책을 지정하려면 <xref:System.Text.Encodings.Web.JavaScriptEncoder>를 만들고 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-600">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f1ff-601">자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-601">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="0f1ff-602">JSON 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0f1ff-602">Customize JSON format</span></span>

<span data-ttu-id="0f1ff-603">`JsonTextWriter`에는 다음과 같은 설정이 있으며, `Utf8JsonWriter`에는 해당 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-603">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="0f1ff-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - 들여쓸 문자 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="0f1ff-605">`Utf8JsonWriter`는 항상 2자 들여쓰기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-605">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="0f1ff-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - 들여쓰기에 사용할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="0f1ff-607">`Utf8JsonWriter`는 항상 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-607">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="0f1ff-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - 문자열 값을 묶는 데 사용할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="0f1ff-609">`Utf8JsonWriter`는 항상 큰따옴표를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-609">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="0f1ff-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - 속성 이름을 따옴표로 묶을지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="0f1ff-611">`Utf8JsonWriter`는 항상 속성 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-611">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="0f1ff-612">이러한 방법으로 `Utf8JsonWriter`에서 생성된 JSON을 사용자 지정할 수 있는 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-612">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="0f1ff-613">null 값 쓰기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-613">Write null values</span></span>

<span data-ttu-id="0f1ff-614">`Utf8JsonWriter`를 사용하여 null 값을 쓰려면 다음을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-614">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="0f1ff-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> - Null을 사용하는 키-값 쌍을 값으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="0f1ff-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> - Null을 JSON 배열의 요소로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="0f1ff-617">문자열 속성의 경우 문자열이 Null이면 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> 및 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>는 `WriteNull` 및 `WriteNullValue`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-617">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="0f1ff-618">Timespan, Uri 또는 char 값 쓰기</span><span class="sxs-lookup"><span data-stu-id="0f1ff-618">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="0f1ff-619">`JsonTextWriter`는 [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) 및 [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) 값에 대한 `WriteValue` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-619">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="0f1ff-620">`Utf8JsonWriter`에는 이에 해당하는 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-620">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="0f1ff-621">그 대신 이러한 값을 문자열로 포맷하고(예를 들어 `ToString()`을 호출) <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-621">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="0f1ff-622">멀티 타기팅</span><span class="sxs-lookup"><span data-stu-id="0f1ff-622">Multi-targeting</span></span>

<span data-ttu-id="0f1ff-623">특정 대상 프레임워크에 `Newtonsoft.Json`을 계속 사용해야 하는 경우 다중 대상을 지정하여 두 가지를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-623">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="0f1ff-624">그러나 이 방법은 간단하지 않으며 `#ifdefs` 및 원본 복제가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-624">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="0f1ff-625">최대한 많은 코드를 공유하는 한 가지 방법은 `Utf8JsonWriter` 및 `Newtonsoft` `JsonTextWriter` 주위에 래퍼를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-625">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="0f1ff-626">이 래퍼는 동작의 차이를 격리하면서 공개 노출 영역을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-626">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="0f1ff-627">이를 통해 변경 내용을 주로 형식 생성으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-627">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="0f1ff-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리는 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f1ff-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="0f1ff-629">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="0f1ff-629">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="0f1ff-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="0f1ff-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="0f1ff-631">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0f1ff-631">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* <span data-ttu-id="0f1ff-632">[System.Text.Json 개요](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-632">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="0f1ff-633">[System.Text.Json 사용 방법](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-633">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* [<span data-ttu-id="0f1ff-634">사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="0f1ff-634">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="0f1ff-635">[System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-635">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="0f1ff-636">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-636">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="0f1ff-637">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="0f1ff-637">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
