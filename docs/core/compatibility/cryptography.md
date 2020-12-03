---
title: 암호화 관련 호환성이 손상되는 변경
description: .NET Core 2.1~3.0의 암호화 관련 호환성이 손상되는 변경을 나열합니다.
ms.date: 04/22/2020
ms.openlocfilehash: a4801bb4d5a859e2c8c2b536ee0597cb4db2f65d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682655"
---
# <a name="cryptography-breaking-changes-for-net-core-21-30"></a><span data-ttu-id="45fd2-103">.NET Core 2.1~3.0의 암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="45fd2-103">Cryptography breaking changes for .NET Core 2.1-3.0</span></span>

<span data-ttu-id="45fd2-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fd2-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="45fd2-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="45fd2-105">Breaking change</span></span> | <span data-ttu-id="45fd2-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="45fd2-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="45fd2-107">Linux에서 더 이상 지원되지 않는 신뢰할 수 있는 인증서 구문 시작</span><span class="sxs-lookup"><span data-stu-id="45fd2-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="45fd2-108">3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-108">3.0</span></span> |
| [<span data-ttu-id="45fd2-109">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="45fd2-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="45fd2-110">3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-110">3.0</span></span> |
| [<span data-ttu-id="45fd2-111">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="45fd2-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="45fd2-112">3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-112">3.0</span></span> |
| [<span data-ttu-id="45fd2-113">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="45fd2-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="45fd2-114">3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-114">3.0</span></span> |
| [<span data-ttu-id="45fd2-115">CryptoStream.Dispose는 쓰는 경우에만 최종 블록을 변환함</span><span class="sxs-lookup"><span data-stu-id="45fd2-115">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="45fd2-116">3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-116">3.0</span></span> |
| [<span data-ttu-id="45fd2-117">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="45fd2-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="45fd2-118">2.1</span><span class="sxs-lookup"><span data-stu-id="45fd2-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="45fd2-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="45fd2-119">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

<span data-ttu-id="45fd2-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="45fd2-120">\*\*_</span></span>

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="45fd2-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="45fd2-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="45fd2-122">_\*\*</span><span class="sxs-lookup"><span data-stu-id="45fd2-122">_\*\*</span></span>
