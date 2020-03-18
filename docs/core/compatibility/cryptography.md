---
title: 암호화 관련 호환성이 손상되는 변경
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 02/10/2020
ms.openlocfilehash: c25eefa8e3ee01ed7a1df4ec4aa9225f2c347a4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449225"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="f2cb4-103">암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="f2cb4-103">Cryptography breaking changes</span></span>

<span data-ttu-id="f2cb4-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cb4-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="f2cb4-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="f2cb4-105">Breaking change</span></span> | <span data-ttu-id="f2cb4-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f2cb4-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="f2cb4-107">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="f2cb4-107">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="f2cb4-108">3.0</span><span class="sxs-lookup"><span data-stu-id="f2cb4-108">3.0</span></span> |
| [<span data-ttu-id="f2cb4-109">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="f2cb4-109">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="f2cb4-110">3.0</span><span class="sxs-lookup"><span data-stu-id="f2cb4-110">3.0</span></span> |
| [<span data-ttu-id="f2cb4-111">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cb4-111">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="f2cb4-112">3.0</span><span class="sxs-lookup"><span data-stu-id="f2cb4-112">3.0</span></span> |
| [<span data-ttu-id="f2cb4-113">Pkcs8PrivateKeyInfo 생성자의 인수 유효성 검사를 개선</span><span class="sxs-lookup"><span data-stu-id="f2cb4-113">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="f2cb4-114">3.0</span><span class="sxs-lookup"><span data-stu-id="f2cb4-114">3.0</span></span> |
| [<span data-ttu-id="f2cb4-115">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="f2cb4-115">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="f2cb4-116">2.1</span><span class="sxs-lookup"><span data-stu-id="f2cb4-116">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="f2cb4-117">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f2cb4-117">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="f2cb4-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f2cb4-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
