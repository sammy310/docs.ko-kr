---
title: 기본 클래스 라이브러리 호환성이 손상되는 변경
description: 핵심 .NET 라이브러리의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/27/2020
ms.openlocfilehash: c3207ac7630d794f77c793cc6d1d52e158c0c084
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738825"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="8711c-103">핵심 .NET 라이브러리의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="8711c-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="8711c-104">핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8711c-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="8711c-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8711c-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="8711c-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8711c-106">Breaking change</span></span> | <span data-ttu-id="8711c-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8711c-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="8711c-108">RC1에서 매개 변수 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="8711c-108">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="8711c-109">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-109">5.0</span></span> |
| [<span data-ttu-id="8711c-110">OSPlatform 특성이 제거되었거나 특성 이름이 바뀜</span><span class="sxs-lookup"><span data-stu-id="8711c-110">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="8711c-111">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-111">5.0</span></span> |
| [<span data-ttu-id="8711c-112">Thread.Abort는 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-112">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="8711c-113">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-113">5.0</span></span> |
| [<span data-ttu-id="8711c-114">ConsoleLoggerOptions에서 사용되지 않는 속성</span><span class="sxs-lookup"><span data-stu-id="8711c-114">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="8711c-115">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-115">5.0</span></span> |
| [<span data-ttu-id="8711c-116">중첩 형식의 경우 하드웨어 내장 IsSupported 검사가 다를 수 있음</span><span class="sxs-lookup"><span data-stu-id="8711c-116">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="8711c-117">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-117">5.0</span></span> |
| [<span data-ttu-id="8711c-118">참조 어셈블리의 매개 변수 이름 변경됨</span><span class="sxs-lookup"><span data-stu-id="8711c-118">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="8711c-119">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-119">5.0</span></span> |
| [<span data-ttu-id="8711c-120">Unix에서 비ASCII 문자를 포함하는 URI 경로가 올바르게 구문 분석됨</span><span class="sxs-lookup"><span data-stu-id="8711c-120">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="8711c-121">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-121">5.0</span></span> |
| [<span data-ttu-id="8711c-122">Unix에서 UNC 경로의 URI 인식</span><span class="sxs-lookup"><span data-stu-id="8711c-122">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="8711c-123">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-123">5.0</span></span> |
| [<span data-ttu-id="8711c-124">Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨</span><span class="sxs-lookup"><span data-stu-id="8711c-124">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="8711c-125">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-125">5.0</span></span> |
| [<span data-ttu-id="8711c-126">LINQ OrderBy.First{OrDefault}의 복잡성이 증가함</span><span class="sxs-lookup"><span data-stu-id="8711c-126">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="8711c-127">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-127">5.0</span></span> |
| [<span data-ttu-id="8711c-128">IntPtr 및 UIntPtr에서 IFormattable 구현</span><span class="sxs-lookup"><span data-stu-id="8711c-128">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="8711c-129">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-129">5.0</span></span> |
| [<span data-ttu-id="8711c-130">PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8711c-130">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="8711c-131">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-131">5.0</span></span> |
| [<span data-ttu-id="8711c-132">ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨</span><span class="sxs-lookup"><span data-stu-id="8711c-132">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="8711c-133">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-133">5.0</span></span> |
| [<span data-ttu-id="8711c-134">UTF-7 코드 경로가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-134">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="8711c-135">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-135">5.0</span></span> |
| [<span data-ttu-id="8711c-136">Vector\<T>가 지원되지 않는 형식에 대해 항상 NotSupportedException을 throw</span><span class="sxs-lookup"><span data-stu-id="8711c-136">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="8711c-137">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-137">5.0</span></span> |
| [<span data-ttu-id="8711c-138">기본 ActivityIdFormat이 W3C임</span><span class="sxs-lookup"><span data-stu-id="8711c-138">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="8711c-139">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-139">5.0</span></span> |
| [<span data-ttu-id="8711c-140">Vector2.Lerp 및 Vector4.Lerp의 동작 변경</span><span class="sxs-lookup"><span data-stu-id="8711c-140">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="8711c-141">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-141">5.0</span></span> |
| [<span data-ttu-id="8711c-142">SSE 및 SSE2 CompareGreaterThan 메서드가 NaN 입력을 올바르게 처리함</span><span class="sxs-lookup"><span data-stu-id="8711c-142">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="8711c-143">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-143">5.0</span></span> |
| [<span data-ttu-id="8711c-144">CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="8711c-144">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="8711c-145">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-145">5.0</span></span> |
| [<span data-ttu-id="8711c-146">Microsoft.DotNet.PlatformAbstractions 패키지가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8711c-146">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="8711c-147">5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-147">5.0</span></span> |
| [<span data-ttu-id="8711c-148">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="8711c-148">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="8711c-149">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-149">3.0</span></span> |
| [<span data-ttu-id="8711c-150">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="8711c-150">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="8711c-151">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-151">3.0</span></span> |
| [<span data-ttu-id="8711c-152">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="8711c-152">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="8711c-153">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-153">3.0</span></span> |
| [<span data-ttu-id="8711c-154">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-154">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="8711c-155">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-155">3.0</span></span> |
| [<span data-ttu-id="8711c-156">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8711c-156">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="8711c-157">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-157">3.0</span></span> |
| [<span data-ttu-id="8711c-158">잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름</span><span class="sxs-lookup"><span data-stu-id="8711c-158">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="8711c-159">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-159">3.0</span></span> |
| [<span data-ttu-id="8711c-160">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8711c-160">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="8711c-161">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-161">3.0</span></span> |
| [<span data-ttu-id="8711c-162">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-162">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="8711c-163">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-163">3.0</span></span> |
| [<span data-ttu-id="8711c-164">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="8711c-164">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="8711c-165">3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-165">3.0</span></span> |
| [<span data-ttu-id="8711c-166">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="8711c-166">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="8711c-167">2.1</span><span class="sxs-lookup"><span data-stu-id="8711c-167">2.1</span></span> |
| [<span data-ttu-id="8711c-168">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="8711c-168">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="8711c-169">2.1</span><span class="sxs-lookup"><span data-stu-id="8711c-169">2.1</span></span> |
| [<span data-ttu-id="8711c-170">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="8711c-170">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="8711c-171">2.1</span><span class="sxs-lookup"><span data-stu-id="8711c-171">2.1</span></span> |
| [<span data-ttu-id="8711c-172">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="8711c-172">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="8711c-173">1.0</span><span class="sxs-lookup"><span data-stu-id="8711c-173">1.0</span></span> |
| [<span data-ttu-id="8711c-174">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-174">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="8711c-175">1.0</span><span class="sxs-lookup"><span data-stu-id="8711c-175">1.0</span></span> |
| [<span data-ttu-id="8711c-176">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="8711c-176">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="8711c-177">1.0</span><span class="sxs-lookup"><span data-stu-id="8711c-177">1.0</span></span> |
| [<span data-ttu-id="8711c-178">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="8711c-178">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="8711c-179">1.0</span><span class="sxs-lookup"><span data-stu-id="8711c-179">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="8711c-180">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8711c-180">.NET 5.0</span></span>

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

***

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

***

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

***

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="8711c-181">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8711c-181">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="8711c-182">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8711c-182">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="8711c-183">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="8711c-183">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
