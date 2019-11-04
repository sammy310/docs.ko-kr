---
title: 암호화 관련 호환성이 손상되는 변경, 버전 2.2-3.0 - .NET Core
description: .NET Core, ASP.NET Core, EF Core 버전 2.2에서 버전 3.0으로의 호환성이 손상되는 변경 사항 사항을 나열합니다.
ms.date: 09/10/2019
ms.openlocfilehash: ba330bdef4be8cfe0e74f5645adaf66b2e0051ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089579"
---
# <a name="breaking-changes-for-migration-from-version-22-to-30"></a><span data-ttu-id="d048b-103">버전 2.2에서 3.0으로 마이그레이션 시 호환성이 손상되는 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d048b-103">Breaking changes for migration from Version 2.2 to 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d048b-104">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-104">This article is under construction.</span></span> <span data-ttu-id="d048b-105">이것은 .NET Core 호환성이 손상되는 변경 사항의 완전한 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="d048b-106">.NET Core 호환성이 손상되는 변경 사항에 대한 자세한 내용은 GitHub의 dotnet/docs 리포지토리에 있는 개별 [호환성이 손상되는 변경 문제](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d048b-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="d048b-107">.NET Core, ASP.NET Core 또는 EF Core 버전 2.2에서 버전 3.0으로 마이그레이션하는 경우, 앱에 영향을 줄 수 있는 호환성이 손상되는 변경에 대한 다음 항목을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="d048b-107">If you are migrating from version 2.2 to version 3.0 of .NET Core, ASP.NET Core, or EF Core, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="corefx"></a><span data-ttu-id="d048b-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="d048b-108">CoreFx</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]

## <a name="cryptography"></a><span data-ttu-id="d048b-109">암호화</span><span class="sxs-lookup"><span data-stu-id="d048b-109">Cryptography</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]

## <a name="globalization"></a><span data-ttu-id="d048b-110">전역화</span><span class="sxs-lookup"><span data-stu-id="d048b-110">Globalization</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/c-locale-maps-to-invariant-locale.md)]

## <a name="visual-basic"></a><span data-ttu-id="d048b-111">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d048b-111">Visual Basic</span></span>

[!INCLUDE[vbNewLine is obsolete](~/includes/core-changes/visualbasic/vbnewline-is-obsolete.md)]

## <a name="entity-framework-core"></a><span data-ttu-id="d048b-112">Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="d048b-112">Entity Framework Core</span></span>

[<span data-ttu-id="d048b-113">Entity Framework Core 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="d048b-113">Entity Framework Core breaking changes</span></span>](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
