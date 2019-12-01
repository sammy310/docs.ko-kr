---
title: 암호화 관련 호환성이 손상되는 변경 - .NET Core
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 09/20/2019
ms.openlocfilehash: 1bd0a79d84885d475609c1f758797690e595a36d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567947"
---
# <a name="cryptography-breaking-changes"></a>암호화 관련 호환성이 손상되는 변경

다음은 .NET Core 버전별 암호화 관련 호환성이 손상되는 변경 목록입니다.

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

## <a name="net-core-30-preview-9"></a>.NET Core 3.0 미리 보기 9

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]
