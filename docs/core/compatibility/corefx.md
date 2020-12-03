---
title: .NET 라이브러리 호환성이 손상되는 변경
description: .NET Core 버전 1.0~3.0의 핵심 .NET 라이브러리 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/27/2020
ms.openlocfilehash: 0f42429e44776fc70bb99ed3bdf346f0d5dbc9eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "96032045"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a><span data-ttu-id="66123-103">.NET Core 1.0~3.0의 핵심 .NET 라이브러리 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="66123-103">Core .NET libraries breaking changes in .NET Core 1.0-3.0</span></span>

<span data-ttu-id="66123-104">핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66123-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="66123-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66123-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="66123-106">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="66123-106">Breaking change</span></span> | <span data-ttu-id="66123-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="66123-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="66123-108">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="66123-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="66123-109">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-109">3.0</span></span> |
| [<span data-ttu-id="66123-110">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="66123-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="66123-111">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-111">3.0</span></span> |
| [<span data-ttu-id="66123-112">부동 소수점 서식 및 구문 분석 동작 변경</span><span class="sxs-lookup"><span data-stu-id="66123-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="66123-113">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-113">3.0</span></span> |
| [<span data-ttu-id="66123-114">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="66123-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="66123-115">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-115">3.0</span></span> |
| [<span data-ttu-id="66123-116">InvalidAsynchronousStateException이 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="66123-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="66123-117">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-117">3.0</span></span> |
| [<span data-ttu-id="66123-118">잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름</span><span class="sxs-lookup"><span data-stu-id="66123-118">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="66123-119">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-119">3.0</span></span> |
| [<span data-ttu-id="66123-120">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="66123-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="66123-121">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-121">3.0</span></span> |
| [<span data-ttu-id="66123-122">ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="66123-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="66123-123">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-123">3.0</span></span> |
| [<span data-ttu-id="66123-124">FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw</span><span class="sxs-lookup"><span data-stu-id="66123-124">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="66123-125">3.0</span><span class="sxs-lookup"><span data-stu-id="66123-125">3.0</span></span> |
| [<span data-ttu-id="66123-126">기본 제공 구조체 형식에 추가된 프라이빗 필드</span><span class="sxs-lookup"><span data-stu-id="66123-126">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="66123-127">2.1</span><span class="sxs-lookup"><span data-stu-id="66123-127">2.1</span></span> |
| [<span data-ttu-id="66123-128">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="66123-128">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="66123-129">2.1</span><span class="sxs-lookup"><span data-stu-id="66123-129">2.1</span></span> |
| [<span data-ttu-id="66123-130">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="66123-130">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="66123-131">2.1</span><span class="sxs-lookup"><span data-stu-id="66123-131">2.1</span></span> |
| [<span data-ttu-id="66123-132">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="66123-132">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="66123-133">1.0</span><span class="sxs-lookup"><span data-stu-id="66123-133">1.0</span></span> |
| [<span data-ttu-id="66123-134">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="66123-134">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="66123-135">1.0</span><span class="sxs-lookup"><span data-stu-id="66123-135">1.0</span></span> |
| [<span data-ttu-id="66123-136">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="66123-136">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="66123-137">1.0</span><span class="sxs-lookup"><span data-stu-id="66123-137">1.0</span></span> |
| [<span data-ttu-id="66123-138">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="66123-138">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="66123-139">1.0</span><span class="sxs-lookup"><span data-stu-id="66123-139">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="66123-140">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="66123-140">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

<span data-ttu-id="66123-141">\*\*_</span><span class="sxs-lookup"><span data-stu-id="66123-141">\*\*_</span></span>

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="66123-142">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="66123-142">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="66123-143">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="66123-143">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="66123-144">_\*\*</span><span class="sxs-lookup"><span data-stu-id="66123-144">_\*\*</span></span>
