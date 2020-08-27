---
title: 암호화 관련 호환성이 손상되는 변경
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 04/22/2020
ms.openlocfilehash: f7d580938fb7620728b8ff7f67412c9f5bbbb6c3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558007"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="e84f2-103">암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="e84f2-103">Cryptography breaking changes</span></span>

<span data-ttu-id="e84f2-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e84f2-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e84f2-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e84f2-105">Breaking change</span></span> | <span data-ttu-id="e84f2-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e84f2-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="e84f2-107">System.Security.Cryptography.Oid는 기능상 초기화 전용임</span><span class="sxs-lookup"><span data-stu-id="e84f2-107">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="e84f2-108">5.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-108">5.0</span></span> |
| [<span data-ttu-id="e84f2-109">Linux에서 더 이상 지원되지 않는 신뢰할 수 있는 인증서 구문 시작</span><span class="sxs-lookup"><span data-stu-id="e84f2-109">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="e84f2-110">3.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-110">3.0</span></span> |
| [<span data-ttu-id="e84f2-111">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="e84f2-111">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="e84f2-112">3.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-112">3.0</span></span> |
| [<span data-ttu-id="e84f2-113">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="e84f2-113">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="e84f2-114">3.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-114">3.0</span></span> |
| [<span data-ttu-id="e84f2-115">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="e84f2-115">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="e84f2-116">3.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-116">3.0</span></span> |
| [<span data-ttu-id="e84f2-117">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="e84f2-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="e84f2-118">2.1</span><span class="sxs-lookup"><span data-stu-id="e84f2-118">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="e84f2-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-119">.NET 5.0</span></span>

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="e84f2-120">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e84f2-120">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="e84f2-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e84f2-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
