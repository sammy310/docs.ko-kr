---
title: 암호화 관련 호환성이 손상되는 변경 - .NET Core
description: .NET Core의 암호화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 09/20/2019
ms.openlocfilehash: 4b13985a12ee0530edd3a0960923aafef1696d90
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116472"
---
# <a name="cryptography-breaking-changes"></a>암호화 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

- [EnvelopedCms를 기본적으로 AES-256 암호화로 설정](#envelopedcms-defaults-to-aes-256-encryption)
- [RSAOpenSsl 키 생성 최소 크기가 증가](#minimum-size-for-rsaopenssl-key-generation-has-increased)
- [.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.](#net-core-30-prefers-openssl-11x-to-openssl-10x)
- [Pkcs8PrivateKeyInfo 생성자의 인수 유효성 검사를 개선](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor)

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-30-preview-9"></a>.NET Core 3.0 미리 보기 9

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***
