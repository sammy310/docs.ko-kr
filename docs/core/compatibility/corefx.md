---
title: 기본 클래스 라이브러리 호환성이 손상되는 변경
description: 핵심 .NET 라이브러리의 호환성이 손상되는 변경을 나열합니다.
ms.date: 09/20/2019
ms.openlocfilehash: ca50123b842c256607d47010dbef9b216ece4661
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420433"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="03cce-103">핵심 .NET 라이브러리의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="03cce-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="03cce-104">핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03cce-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="03cce-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03cce-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="03cce-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="03cce-106">Breaking change</span></span> | <span data-ttu-id="03cce-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="03cce-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="03cce-108">SSE 및 SSE2 CompareGreaterThan 메서드가 NaN 입력을 올바르게 처리함</span><span class="sxs-lookup"><span data-stu-id="03cce-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="03cce-109">5.0</span><span class="sxs-lookup"><span data-stu-id="03cce-109">5.0</span></span> |
| [<span data-ttu-id="03cce-110">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="03cce-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="03cce-111">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-111">3.0</span></span> |
| [<span data-ttu-id="03cce-112">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="03cce-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="03cce-113">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-113">3.0</span></span> |
| [<span data-ttu-id="03cce-114">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="03cce-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="03cce-115">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-115">3.0</span></span> |
| [<span data-ttu-id="03cce-116">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="03cce-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="03cce-117">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-117">3.0</span></span> |
| [<span data-ttu-id="03cce-118">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="03cce-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="03cce-119">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-119">3.0</span></span> |
| [<span data-ttu-id="03cce-120">잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름</span><span class="sxs-lookup"><span data-stu-id="03cce-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="03cce-121">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-121">3.0</span></span> |
| [<span data-ttu-id="03cce-122">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="03cce-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="03cce-123">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-123">3.0</span></span> |
| [<span data-ttu-id="03cce-124">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="03cce-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="03cce-125">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-125">3.0</span></span> |
| [<span data-ttu-id="03cce-126">JSON 직렬 변환기 예외 형식이 JsonException에서 NotSupportedException으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="03cce-126">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="03cce-127">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-127">3.0</span></span> |
| [<span data-ttu-id="03cce-128">Utf8JsonWriter에서 (문자열)null의 의미 체계가 변경됨</span><span class="sxs-lookup"><span data-stu-id="03cce-128">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="03cce-129">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-129">3.0</span></span> |
| [<span data-ttu-id="03cce-130">JsonEncodedText.Encode 메서드에 JavaScriptEncoder 인수 추가</span><span class="sxs-lookup"><span data-stu-id="03cce-130">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="03cce-131">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-131">3.0</span></span> |
| [<span data-ttu-id="03cce-132">JsonFactoryConverter.CreateConverter 서명이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03cce-132">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="03cce-133">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-133">3.0</span></span> |
| [<span data-ttu-id="03cce-134">JsonElement API 변경 내용</span><span class="sxs-lookup"><span data-stu-id="03cce-134">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="03cce-135">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-135">3.0</span></span> |
| [<span data-ttu-id="03cce-136">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="03cce-136">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="03cce-137">3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-137">3.0</span></span> |
| [<span data-ttu-id="03cce-138">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="03cce-138">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="03cce-139">2.1</span><span class="sxs-lookup"><span data-stu-id="03cce-139">2.1</span></span> |
| [<span data-ttu-id="03cce-140">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="03cce-140">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="03cce-141">2.1</span><span class="sxs-lookup"><span data-stu-id="03cce-141">2.1</span></span> |
| [<span data-ttu-id="03cce-142">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="03cce-142">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="03cce-143">2.1</span><span class="sxs-lookup"><span data-stu-id="03cce-143">2.1</span></span> |
| [<span data-ttu-id="03cce-144">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="03cce-144">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="03cce-145">1.0</span><span class="sxs-lookup"><span data-stu-id="03cce-145">1.0</span></span> |
| [<span data-ttu-id="03cce-146">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="03cce-146">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="03cce-147">1.0</span><span class="sxs-lookup"><span data-stu-id="03cce-147">1.0</span></span> |
| [<span data-ttu-id="03cce-148">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="03cce-148">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="03cce-149">1.0</span><span class="sxs-lookup"><span data-stu-id="03cce-149">1.0</span></span> |
| [<span data-ttu-id="03cce-150">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="03cce-150">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="03cce-151">1.0</span><span class="sxs-lookup"><span data-stu-id="03cce-151">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="03cce-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="03cce-152">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="03cce-153">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="03cce-153">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="03cce-154">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="03cce-154">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="03cce-155">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="03cce-155">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
