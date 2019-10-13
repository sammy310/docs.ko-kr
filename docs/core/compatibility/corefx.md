---
title: CoreFx 관련 호환성이 손상되는 변경 - .NET Core
description: 기본 클래스 라이브러리인 .NET CoreFx 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7681dadbbbae737cb1cbc260613baea9d34527a8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002441"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="94ec5-103">CoreFx 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="94ec5-103">CoreFx breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94ec5-104">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="94ec5-104">This article is under construction.</span></span> <span data-ttu-id="94ec5-105">이것은 .NET Core 호환성이 손상되는 변경 사항의 완전한 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="94ec5-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="94ec5-106">.NET Core 호환성이 손상되는 변경 사항에 대한 자세한 내용은 GitHub의 dotnet/docs 리포지토리에 있는 개별 [호환성이 손상되는 변경 문제](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94ec5-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="94ec5-107">다음은 .NET Core 버전별 CoreFx 관련 호환성이 손상되는 변경 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="94ec5-107">The following is a list of CoreFx breaking changes by .NET Core version.</span></span> <span data-ttu-id="94ec5-108">CoreFx는 .NET Core에서 사용되는 기본 형식과 기타 일반적인 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94ec5-108">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

## <a name="net-core-30-preview-7"></a><span data-ttu-id="94ec5-109">.NET Core 3.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="94ec5-109">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/jsonelement-api-changes.md)]

## <a name="net-core-30-preview-8"></a><span data-ttu-id="94ec5-110">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="94ec5-110">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/jsonfactoryconverter-createconverter.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="94ec5-111">.NET Core 3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="94ec5-111">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Json serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/serializer-throws-notsupportedexception.md)]

## <a name="net-core-30"></a><span data-ttu-id="94ec5-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="94ec5-112">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]
