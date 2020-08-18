---
title: 기본 클래스 라이브러리 호환성이 손상되는 변경
description: 핵심 .NET 라이브러리의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/27/2020
ms.openlocfilehash: c8eb5ec7d2bb1879a38a18337463230c7b731d29
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137480"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="8b6b4-103">핵심 .NET 라이브러리의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="8b6b4-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="8b6b4-104">핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6b4-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="8b6b4-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6b4-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="8b6b4-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8b6b4-106">Breaking change</span></span> | <span data-ttu-id="8b6b4-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8b6b4-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="8b6b4-108">LINQ OrderBy.First{OrDefault}의 복잡성이 증가함</span><span class="sxs-lookup"><span data-stu-id="8b6b4-108">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="8b6b4-109">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-109">5.0</span></span> |
| [<span data-ttu-id="8b6b4-110">IntPtr 및 UIntPtr에서 IFormattable 구현</span><span class="sxs-lookup"><span data-stu-id="8b6b4-110">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="8b6b4-111">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-111">5.0</span></span> |
| [<span data-ttu-id="8b6b4-112">PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6b4-112">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="8b6b4-113">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-113">5.0</span></span> |
| [<span data-ttu-id="8b6b4-114">ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨</span><span class="sxs-lookup"><span data-stu-id="8b6b4-114">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="8b6b4-115">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-115">5.0</span></span> |
| [<span data-ttu-id="8b6b4-116">UTF-7 코드 경로가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-116">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="8b6b4-117">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-117">5.0</span></span> |
| [<span data-ttu-id="8b6b4-118">Vector\<T>가 지원되지 않는 형식에 대해 항상 NotSupportedException을 throw</span><span class="sxs-lookup"><span data-stu-id="8b6b4-118">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="8b6b4-119">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-119">5.0</span></span> |
| [<span data-ttu-id="8b6b4-120">기본 ActivityIdFormat이 W3C임</span><span class="sxs-lookup"><span data-stu-id="8b6b4-120">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="8b6b4-121">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-121">5.0</span></span> |
| [<span data-ttu-id="8b6b4-122">Vector2.Lerp 및 Vector4.Lerp의 동작 변경</span><span class="sxs-lookup"><span data-stu-id="8b6b4-122">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="8b6b4-123">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-123">5.0</span></span> |
| [<span data-ttu-id="8b6b4-124">SSE 및 SSE2 CompareGreaterThan 메서드가 NaN 입력을 올바르게 처리함</span><span class="sxs-lookup"><span data-stu-id="8b6b4-124">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="8b6b4-125">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-125">5.0</span></span> |
| [<span data-ttu-id="8b6b4-126">CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="8b6b4-126">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="8b6b4-127">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-127">5.0</span></span> |
| [<span data-ttu-id="8b6b4-128">Microsoft.DotNet.PlatformAbstractions 패키지가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8b6b4-128">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="8b6b4-129">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-129">5.0</span></span> |
| [<span data-ttu-id="8b6b4-130">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="8b6b4-130">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="8b6b4-131">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-131">3.0</span></span> |
| [<span data-ttu-id="8b6b4-132">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-132">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="8b6b4-133">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-133">3.0</span></span> |
| [<span data-ttu-id="8b6b4-134">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="8b6b4-134">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="8b6b4-135">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-135">3.0</span></span> |
| [<span data-ttu-id="8b6b4-136">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-136">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="8b6b4-137">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-137">3.0</span></span> |
| [<span data-ttu-id="8b6b4-138">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8b6b4-138">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="8b6b4-139">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-139">3.0</span></span> |
| [<span data-ttu-id="8b6b4-140">잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름</span><span class="sxs-lookup"><span data-stu-id="8b6b4-140">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="8b6b4-141">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-141">3.0</span></span> |
| [<span data-ttu-id="8b6b4-142">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8b6b4-142">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="8b6b4-143">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-143">3.0</span></span> |
| [<span data-ttu-id="8b6b4-144">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-144">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="8b6b4-145">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-145">3.0</span></span> |
| [<span data-ttu-id="8b6b4-146">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="8b6b4-146">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="8b6b4-147">3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-147">3.0</span></span> |
| [<span data-ttu-id="8b6b4-148">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="8b6b4-148">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="8b6b4-149">2.1</span><span class="sxs-lookup"><span data-stu-id="8b6b4-149">2.1</span></span> |
| [<span data-ttu-id="8b6b4-150">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="8b6b4-150">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="8b6b4-151">2.1</span><span class="sxs-lookup"><span data-stu-id="8b6b4-151">2.1</span></span> |
| [<span data-ttu-id="8b6b4-152">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="8b6b4-152">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="8b6b4-153">2.1</span><span class="sxs-lookup"><span data-stu-id="8b6b4-153">2.1</span></span> |
| [<span data-ttu-id="8b6b4-154">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="8b6b4-154">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="8b6b4-155">1.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-155">1.0</span></span> |
| [<span data-ttu-id="8b6b4-156">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-156">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="8b6b4-157">1.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-157">1.0</span></span> |
| [<span data-ttu-id="8b6b4-158">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="8b6b4-158">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="8b6b4-159">1.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-159">1.0</span></span> |
| [<span data-ttu-id="8b6b4-160">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="8b6b4-160">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="8b6b4-161">1.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-161">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="8b6b4-162">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-162">.NET 5.0</span></span>

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="8b6b4-163">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-163">.NET Core 3.0</span></span>

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

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="8b6b4-164">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8b6b4-164">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="8b6b4-165">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="8b6b4-165">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
