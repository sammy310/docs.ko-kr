---
title: 기본 클래스 라이브러리 호환성이 손상되는 변경
description: 기본 클래스 라이브러리인 .NET CoreFx 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 09/20/2019
ms.openlocfilehash: 7c59f2a96545e74e4099b6078ff52009740699c6
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449561"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="213e9-103">CoreFx 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="213e9-103">CoreFx breaking changes</span></span>

<span data-ttu-id="213e9-104">CoreFx는 .NET Core에서 사용되는 기본 형식과 기타 일반적인 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213e9-104">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="213e9-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213e9-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="213e9-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="213e9-106">Breaking change</span></span> | <span data-ttu-id="213e9-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="213e9-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="213e9-108">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="213e9-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="213e9-109">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-109">3.0</span></span> |
| [<span data-ttu-id="213e9-110">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="213e9-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="213e9-111">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-111">3.0</span></span> |
| [<span data-ttu-id="213e9-112">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="213e9-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="213e9-113">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-113">3.0</span></span> |
| [<span data-ttu-id="213e9-114">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="213e9-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="213e9-115">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-115">3.0</span></span> |
| [<span data-ttu-id="213e9-116">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="213e9-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="213e9-117">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-117">3.0</span></span> |
| [<span data-ttu-id="213e9-118">.NET Core 3.0이 잘못된 형식의 UTF-8 바이트 시퀀스를 대체할 때 유니코드 모범 사례를 적용</span><span class="sxs-lookup"><span data-stu-id="213e9-118">NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | <span data-ttu-id="213e9-119">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-119">3.0</span></span> |
| [<span data-ttu-id="213e9-120">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="213e9-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="213e9-121">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-121">3.0</span></span> |
| [<span data-ttu-id="213e9-122">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="213e9-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="213e9-123">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-123">3.0</span></span> |
| [<span data-ttu-id="213e9-124">JSON 직렬 변환기 예외 형식이 JsonException에서 NotSupportedException으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="213e9-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="213e9-125">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-125">3.0</span></span> |
| [<span data-ttu-id="213e9-126">Utf8JsonWriter에서 (문자열)null의 의미 체계가 변경됨</span><span class="sxs-lookup"><span data-stu-id="213e9-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="213e9-127">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-127">3.0</span></span> |
| [<span data-ttu-id="213e9-128">JsonEncodedText.Encode 메서드에 JavaScriptEncoder 인수 추가</span><span class="sxs-lookup"><span data-stu-id="213e9-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="213e9-129">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-129">3.0</span></span> |
| [<span data-ttu-id="213e9-130">JsonFactoryConverter.CreateConverter 서명이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="213e9-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="213e9-131">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-131">3.0</span></span> |
| [<span data-ttu-id="213e9-132">JsonElement API 변경 내용</span><span class="sxs-lookup"><span data-stu-id="213e9-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="213e9-133">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-133">3.0</span></span> |
| [<span data-ttu-id="213e9-134">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="213e9-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="213e9-135">3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-135">3.0</span></span> |
| [<span data-ttu-id="213e9-136">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="213e9-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="213e9-137">2.1</span><span class="sxs-lookup"><span data-stu-id="213e9-137">2.1</span></span> |
| [<span data-ttu-id="213e9-138">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="213e9-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="213e9-139">2.1</span><span class="sxs-lookup"><span data-stu-id="213e9-139">2.1</span></span> |
| [<span data-ttu-id="213e9-140">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="213e9-140">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="213e9-141">1.0</span><span class="sxs-lookup"><span data-stu-id="213e9-141">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="213e9-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="213e9-142">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="213e9-143">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="213e9-143">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="213e9-144">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="213e9-144">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
