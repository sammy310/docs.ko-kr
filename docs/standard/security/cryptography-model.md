---
title: .NET 암호화 모델
description: .NET에서 일반적인 암호화 알고리즘의 구현을 검토 합니다. 개체 상속, 스트림 디자인 & 구성의 확장 가능한 암호화 모델에 대해 알아봅니다.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 0b3e07238bf0932572c222f7b947cfa7ae0221a9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556997"
---
# <a name="net-cryptography-model"></a>.NET 암호화 모델

.NET에서는 많은 표준 암호화 알고리즘의 구현을 제공 하며 .NET 암호화 모델을 확장할 수 있습니다.

## <a name="object-inheritance"></a>개체 상속

.NET 암호화 시스템은 파생 클래스 상속의 확장 가능한 패턴을 구현 합니다. 계층 구조는 다음과 같습니다.

- 알고리즘 유형 클래스 (예: <xref:System.Security.Cryptography.SymmetricAlgorithm> , <xref:System.Security.Cryptography.AsymmetricAlgorithm> 또는) <xref:System.Security.Cryptography.HashAlgorithm> 이 수준은 추상 클래스입니다.

- 알고리즘 형식 클래스에서 상속되는 알고리즘 클래스. 예를 들어 <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> 또는 <xref:System.Security.Cryptography.ECDiffieHellman>입니다. 이 수준은 추상 클래스입니다.

- 알고리즘 클래스에서 상속되는 알고리즘 클래스의 구현. 예를 들어 <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> 또는 <xref:System.Security.Cryptography.ECDiffieHellmanCng>입니다. 이 수준은 완전히 구현됩니다.

이 패턴의 파생 클래스를 사용 하 여 새 알고리즘 또는 기존 알고리즘의 새 구현을 추가할 수 있습니다. 예를 들어 새로운 공용 키 알고리즘을 만들려면 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스에서 상속합니다. 특정 알고리즘의 새 구현을 만들려면 해당 알고리즘의 비추상 파생 클래스를 만듭니다.

## <a name="how-algorithms-are-implemented-in-net"></a>.NET에서 알고리즘을 구현 하는 방법

알고리즘에 사용할 수 있는 다양한 구현의 예로 대칭 알고리즘을 고려해 보세요. 모든 대칭 알고리즘의 기본은, <xref:System.Security.Cryptography.SymmetricAlgorithm> <xref:System.Security.Cryptography.Aes> <xref:System.Security.Cryptography.TripleDES> 및 더 이상 권장 되지 않는 다른 항목에서 상속 되는입니다.

<xref:System.Security.Cryptography.Aes>는, 및에 상속 됩니다 <xref:System.Security.Cryptography.AesCryptoServiceProvider> <xref:System.Security.Cryptography.AesCng> <xref:System.Security.Cryptography.AesManaged> .

Windows의 .NET Framework:

* `*CryptoServiceProvider`와 같은 알고리즘 클래스는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 알고리즘의 CAPI (Windows CRYPTOGRAPHY API) 구현을 중심으로 하는 래퍼입니다.
* `*Cng`와 같은 알고리즘 클래스는 <xref:System.Security.Cryptography.ECDiffieHellmanCng> CNG (Windows Cryptography Next generation) 구현을 둘러싼 래퍼입니다.
* `*Managed`와 같은 클래스는 <xref:System.Security.Cryptography.AesManaged> 완전히 관리 코드로 작성 됩니다. `*Managed`구현은 연방 FIPS (정보 처리 표준)의 인증을 받지 않으며 `*CryptoServiceProvider` 및 래퍼 클래스 보다 느릴 수 있습니다 `*Cng` .

.NET Core 및 .NET 5 이상 버전에서 모든 구현 클래스 ( `*CryptoServiceProvider` , `*Managed` 및 `*Cng` )는 os (운영 체제) 알고리즘에 대 한 래퍼입니다. OS 알고리즘이 FIPS 인증 인 경우 .NET은 FIPS 인증 알고리즘을 사용 합니다. 자세한 내용은 [플랫폼 간 암호화](cross-platform-cryptography.md)를 참조 하세요.

대부분의 경우와 같은 알고리즘 구현 클래스를 직접 참조할 필요가 없습니다 `AesCryptoServiceProvider` . 일반적으로 필요한 메서드 및 속성은와 같은 기본 알고리즘 클래스에 있습니다 `Aes` . 기본 알고리즘 클래스에서 팩터리 메서드를 사용 하 여 기본 구현 클래스의 인스턴스를 만들고 기본 알고리즘 클래스를 참조 합니다. 예를 들어 다음 예제에서 강조 표시 된 코드 줄을 참조 하세요.

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a>암호화 구성

암호화 구성을 사용 하면 알고리즘의 특정 구현을 알고리즘 이름으로 확인 하 여 .NET 암호화 클래스의 확장성을 허용할 수 있습니다. 알고리즘의 고유한 하드웨어 또는 소프트웨어 구현을 추가하고 선택한 알고리즘 이름에 해당 구현을 매핑할 수 있습니다. 구성 파일에 알고리즘이 지정되지 않은 경우 기본 설정이 사용됩니다.

## <a name="choosing-an-algorithm"></a>알고리즘 선택

데이터 무결성, 데이터 프라이버시 또는 키 생성과 같은 다양한 이유로 알고리즘을 선택할 수 있습니다. 대칭 및 해시 알고리즘은 무결성(변경 차단) 또는 프라이버시(보기 차단)를 위해 데이터를 보호하는 데 사용됩니다. 해시 알고리즘은 주로 데이터 무결성을 위해 사용됩니다.

애플리케이션에서 권장하는 알고리즘 목록은 다음과 같습니다.

- 데이터 프라이버시:
  - <xref:System.Security.Cryptography.Aes>
- 데이터 무결성:
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- 디지털 서명:
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- 키 교환:
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- 난수 생성:
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- 암호에서 키 생성:
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>참고 항목

- [암호화 서비스](cryptographic-services.md)
- [플랫폼 간 암호화](cross-platform-cryptography.md)
- [ASP.NET Core 데이터 보호](/aspnet/core/security/data-protection/introduction)
