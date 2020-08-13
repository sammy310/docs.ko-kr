---
title: 기본 클래스 라이브러리 호환성이 손상되는 변경
description: 핵심 .NET 라이브러리의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/27/2020
ms.openlocfilehash: 0667d975ce5bba5692fe5d179341235bd3c61790
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024704"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="0fe21-103">핵심 .NET 라이브러리의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="0fe21-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="0fe21-104">핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe21-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="0fe21-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe21-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="0fe21-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="0fe21-106">Breaking change</span></span> | <span data-ttu-id="0fe21-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0fe21-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="0fe21-108">IntPtr 및 UIntPtr에서 IFormattable 구현</span><span class="sxs-lookup"><span data-stu-id="0fe21-108">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="0fe21-109">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-109">5.0</span></span> |
| [<span data-ttu-id="0fe21-110">PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe21-110">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="0fe21-111">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-111">5.0</span></span> |
| [<span data-ttu-id="0fe21-112">ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨</span><span class="sxs-lookup"><span data-stu-id="0fe21-112">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="0fe21-113">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-113">5.0</span></span> |
| [<span data-ttu-id="0fe21-114">UTF-7 코드 경로가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="0fe21-114">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="0fe21-115">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-115">5.0</span></span> |
| [<span data-ttu-id="0fe21-116">Vector\<T>가 지원되지 않는 형식에 대해 항상 NotSupportedException을 throw</span><span class="sxs-lookup"><span data-stu-id="0fe21-116">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="0fe21-117">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-117">5.0</span></span> |
| [<span data-ttu-id="0fe21-118">기본 ActivityIdFormat이 W3C임</span><span class="sxs-lookup"><span data-stu-id="0fe21-118">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="0fe21-119">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-119">5.0</span></span> |
| [<span data-ttu-id="0fe21-120">Vector2.Lerp 및 Vector4.Lerp의 동작 변경</span><span class="sxs-lookup"><span data-stu-id="0fe21-120">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="0fe21-121">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-121">5.0</span></span> |
| [<span data-ttu-id="0fe21-122">SSE 및 SSE2 CompareGreaterThan 메서드가 NaN 입력을 올바르게 처리함</span><span class="sxs-lookup"><span data-stu-id="0fe21-122">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="0fe21-123">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-123">5.0</span></span> |
| [<span data-ttu-id="0fe21-124">CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="0fe21-124">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="0fe21-125">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-125">5.0</span></span> |
| [<span data-ttu-id="0fe21-126">Microsoft.DotNet.PlatformAbstractions 패키지가 제거됨</span><span class="sxs-lookup"><span data-stu-id="0fe21-126">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="0fe21-127">5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-127">5.0</span></span> |
| [<span data-ttu-id="0fe21-128">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="0fe21-128">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="0fe21-129">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-129">3.0</span></span> |
| [<span data-ttu-id="0fe21-130">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="0fe21-130">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="0fe21-131">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-131">3.0</span></span> |
| [<span data-ttu-id="0fe21-132">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="0fe21-132">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="0fe21-133">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-133">3.0</span></span> |
| [<span data-ttu-id="0fe21-134">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="0fe21-134">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="0fe21-135">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-135">3.0</span></span> |
| [<span data-ttu-id="0fe21-136">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="0fe21-136">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="0fe21-137">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-137">3.0</span></span> |
| [<span data-ttu-id="0fe21-138">잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름</span><span class="sxs-lookup"><span data-stu-id="0fe21-138">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="0fe21-139">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-139">3.0</span></span> |
| [<span data-ttu-id="0fe21-140">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="0fe21-140">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="0fe21-141">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-141">3.0</span></span> |
| [<span data-ttu-id="0fe21-142">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="0fe21-142">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="0fe21-143">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-143">3.0</span></span> |
| [<span data-ttu-id="0fe21-144">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="0fe21-144">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="0fe21-145">3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-145">3.0</span></span> |
| [<span data-ttu-id="0fe21-146">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="0fe21-146">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="0fe21-147">2.1</span><span class="sxs-lookup"><span data-stu-id="0fe21-147">2.1</span></span> |
| [<span data-ttu-id="0fe21-148">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="0fe21-148">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="0fe21-149">2.1</span><span class="sxs-lookup"><span data-stu-id="0fe21-149">2.1</span></span> |
| [<span data-ttu-id="0fe21-150">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="0fe21-150">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="0fe21-151">2.1</span><span class="sxs-lookup"><span data-stu-id="0fe21-151">2.1</span></span> |
| [<span data-ttu-id="0fe21-152">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="0fe21-152">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="0fe21-153">1.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-153">1.0</span></span> |
| [<span data-ttu-id="0fe21-154">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="0fe21-154">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="0fe21-155">1.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-155">1.0</span></span> |
| [<span data-ttu-id="0fe21-156">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="0fe21-156">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="0fe21-157">1.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-157">1.0</span></span> |
| [<span data-ttu-id="0fe21-158">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="0fe21-158">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="0fe21-159">1.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-159">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="0fe21-160">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-160">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="0fe21-161">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-161">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="0fe21-162">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0fe21-162">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="0fe21-163">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0fe21-163">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
