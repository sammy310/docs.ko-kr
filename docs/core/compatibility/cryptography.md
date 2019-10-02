---
title: 암호화 관련 호환성이 손상되는 변경 - .NET Core
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80b62f9b32487e88a309ea7686f78d68af8f2e0a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216986"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="a7156-103">암호화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="a7156-103">Cryptography breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7156-104">이 문서는 작성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a7156-104">This article is under construction.</span></span> <span data-ttu-id="a7156-105">이것은 .NET Core 호환성이 손상되는 변경 사항의 완전한 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a7156-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="a7156-106">.NET Core 호환성이 손상되는 변경 사항에 대한 자세한 내용은 GitHub의 dotnet/docs 리포지토리에 있는 개별 [호환성이 손상되는 변경 문제](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7156-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="a7156-107">다음은 .NET Core 버전별 암호화 관련 호환성이 손상되는 변경 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a7156-107">The following is a list of cryptography-related breaking changes by .NET Core version.</span></span>

## <a name="net-core-30-preview-9"></a><span data-ttu-id="a7156-108">.NET Core 3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="a7156-108">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

## <a name="net-core-30"></a><span data-ttu-id="a7156-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a7156-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]
