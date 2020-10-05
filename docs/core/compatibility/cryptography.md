---
title: 암호화 관련 호환성이 손상되는 변경
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 04/22/2020
ms.openlocfilehash: 667d983fc6f2592c2169f97d328cd7947c8bcc81
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406151"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="27e45-103">암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="27e45-103">Cryptography breaking changes</span></span>

<span data-ttu-id="27e45-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27e45-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="27e45-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="27e45-105">Breaking change</span></span> | <span data-ttu-id="27e45-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="27e45-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="27e45-107">Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API</span><span class="sxs-lookup"><span data-stu-id="27e45-107">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="27e45-108">5.0</span><span class="sxs-lookup"><span data-stu-id="27e45-108">5.0</span></span> |
| [<span data-ttu-id="27e45-109">System.Security.Cryptography.Oid는 기능상 초기화 전용임</span><span class="sxs-lookup"><span data-stu-id="27e45-109">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="27e45-110">5.0</span><span class="sxs-lookup"><span data-stu-id="27e45-110">5.0</span></span> |
| [<span data-ttu-id="27e45-111">Linux에서 더 이상 지원되지 않는 신뢰할 수 있는 인증서 구문 시작</span><span class="sxs-lookup"><span data-stu-id="27e45-111">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="27e45-112">3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-112">3.0</span></span> |
| [<span data-ttu-id="27e45-113">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="27e45-113">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="27e45-114">3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-114">3.0</span></span> |
| [<span data-ttu-id="27e45-115">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="27e45-115">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="27e45-116">3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-116">3.0</span></span> |
| [<span data-ttu-id="27e45-117">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="27e45-117">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="27e45-118">3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-118">3.0</span></span> |
| [<span data-ttu-id="27e45-119">CryptoStream.Dispose는 쓰는 경우에만 최종 블록을 변환함</span><span class="sxs-lookup"><span data-stu-id="27e45-119">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="27e45-120">3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-120">3.0</span></span> |
| [<span data-ttu-id="27e45-121">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="27e45-121">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="27e45-122">2.1</span><span class="sxs-lookup"><span data-stu-id="27e45-122">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="27e45-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="27e45-123">.NET 5.0</span></span>

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="27e45-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="27e45-124">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="27e45-125">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="27e45-125">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
