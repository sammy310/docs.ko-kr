---
title: 암호화 관련 호환성이 손상되는 변경
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 04/22/2020
ms.openlocfilehash: b755876624a7709cfe08b5993655e78be9f8e1f2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888615"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="a6bb0-103">암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="a6bb0-103">Cryptography breaking changes</span></span>

<span data-ttu-id="a6bb0-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6bb0-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a6bb0-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="a6bb0-105">Breaking change</span></span> | <span data-ttu-id="a6bb0-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a6bb0-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a6bb0-107">TripleDES.Create에서 생성된 인스턴스의 기본 FeedbackSize 값이 변경됨</span><span class="sxs-lookup"><span data-stu-id="a6bb0-107">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>](#default-feedbacksize-value-for-instances-created-by-tripledescreate-changed) | <span data-ttu-id="a6bb0-108">5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-108">5.0</span></span> |
| [<span data-ttu-id="a6bb0-109">암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6bb0-109">Instantiating default implementations of cryptographic abstractions is not supported</span></span>](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | <span data-ttu-id="a6bb0-110">5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-110">5.0</span></span> |
| [<span data-ttu-id="a6bb0-111">Linux의 .NET용 기본 TLS 암호 그룹</span><span class="sxs-lookup"><span data-stu-id="a6bb0-111">Default TLS cipher suites for .NET on Linux</span></span>](#default-tls-cipher-suites-for-net-on-linux) | <span data-ttu-id="a6bb0-112">5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-112">5.0</span></span> |
| [<span data-ttu-id="a6bb0-113">Blazor WebAssembly에서 지원되지 않는 System.Security.Cryptography API</span><span class="sxs-lookup"><span data-stu-id="a6bb0-113">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="a6bb0-114">5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-114">5.0</span></span> |
| [<span data-ttu-id="a6bb0-115">System.Security.Cryptography.Oid는 기능상 초기화 전용임</span><span class="sxs-lookup"><span data-stu-id="a6bb0-115">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="a6bb0-116">5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-116">5.0</span></span> |
| [<span data-ttu-id="a6bb0-117">Linux에서 더 이상 지원되지 않는 신뢰할 수 있는 인증서 구문 시작</span><span class="sxs-lookup"><span data-stu-id="a6bb0-117">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="a6bb0-118">3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-118">3.0</span></span> |
| [<span data-ttu-id="a6bb0-119">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="a6bb0-119">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="a6bb0-120">3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-120">3.0</span></span> |
| [<span data-ttu-id="a6bb0-121">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="a6bb0-121">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="a6bb0-122">3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-122">3.0</span></span> |
| [<span data-ttu-id="a6bb0-123">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="a6bb0-123">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="a6bb0-124">3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-124">3.0</span></span> |
| [<span data-ttu-id="a6bb0-125">CryptoStream.Dispose는 쓰는 경우에만 최종 블록을 변환함</span><span class="sxs-lookup"><span data-stu-id="a6bb0-125">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="a6bb0-126">3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-126">3.0</span></span> |
| [<span data-ttu-id="a6bb0-127">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="a6bb0-127">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="a6bb0-128">2.1</span><span class="sxs-lookup"><span data-stu-id="a6bb0-128">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="a6bb0-129">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-129">.NET 5.0</span></span>

[!INCLUDE [tripledes-default-feedback-size-change](../../../includes/core-changes/cryptography/5.0/tripledes-default-feedback-size-change.md)]

***

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

<span data-ttu-id="a6bb0-130">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a6bb0-130">\*\*_</span></span>

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="a6bb0-131">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a6bb0-131">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

_*_

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

_*_

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="a6bb0-132">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a6bb0-132">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="a6bb0-133">_\*\*</span><span class="sxs-lookup"><span data-stu-id="a6bb0-133">_\*\*</span></span>
