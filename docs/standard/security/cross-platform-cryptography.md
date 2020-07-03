---
title: .NET Core 및 .NET 5의 플랫폼 간 암호화
description: .NET에서 지 원하는 플랫폼의 암호화 기능에 대해 알아봅니다.
ms.date: 06/19/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography, cross-platform
- encryption, cross-platform
ms.openlocfilehash: 793a9bc55e5bd660374abd2ae81899e63ce3f36a
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85854028"
---
# <a name="cross-platform-cryptography-in-net-core-and-net-5"></a>.NET Core 및 .NET 5의 플랫폼 간 암호화

.NET Core 및 .NET 5의 암호화 작업은 OS (운영 체제) 라이브러리에 의해 수행 됩니다. 이 종속성에는 다음과 같은 이점이 있습니다.

* .NET 앱은 OS 안정성을 활용 합니다. 암호화 라이브러리를 취약성 으로부터 안전 하 게 유지 하는 것은 OS 공급 업체의 높은 우선 순위입니다. 이렇게 하려면 시스템 관리자가 적용 해야 하는 업데이트를 제공 합니다.
* .NET 앱은 fips 유효성 검사가 수행 되는 경우 FIPS 유효성 검사 알고리즘에 액세스할 수 있습니다.

OS 라이브러리에 대 한 종속성은 .NET 앱에서 OS가 지 원하는 암호화 기능만 사용할 수 있음을 의미 합니다. 모든 플랫폼은 특정 핵심 기능을 지원 하지만, 일부 플랫폼에서는 .NET에서 지 원하는 일부 기능을 사용할 수 없습니다. 이 문서에서는 각 플랫폼에서 지원 되는 기능을 식별 합니다.

이 문서에서는 .NET의 암호화에 대해 잘 알고 있다고 가정 합니다. 자세한 내용은 [.Net 암호화 모델](cryptography-model.md) 및 [.net 암호화 서비스](cryptographic-services.md)를 참조 하세요.

## <a name="hash-algorithms"></a>해시 알고리즘

모든 해시 알고리즘과 클래스를 포함 한 HMAC (해시 기반 메시지 인증) 클래스는 `*Managed` OS 라이브러리에 대해 지연 됩니다. 다양 한 OS 라이브러리는 성능에 차이가 있지만 호환 되어야 합니다.

## <a name="symmetric-encryption"></a>대칭 암호화

기본 암호화 및 연결은 시스템 라이브러리에서 수행 되며 모든 플랫폼에서 지원 됩니다.

| 암호화 + 모드 | Windows | Linux | macOS |
|---------------|---------|-------|-------|
| AES-CBC       | ✔️     | ✔️    | ✔️   |
| AES-ECB       | ✔️     | ✔️    | ✔️   |
| 3DES-CBC      | ✔️     | ✔️    | ✔️   |
| 3DES-ECB      | ✔️     | ✔️    | ✔️   |
| DES-CBC       | ✔️     | ✔️    | ✔️   |
| DES-ECB       | ✔️     | ✔️    | ✔️   |

## <a name="authenticated-encryption"></a>인증 된 암호화

AE (인증 된 암호화) 지원은 및 클래스를 통해 AES-CCM 및 AES GCM에 대해 제공 됩니다 <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName> <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName> .

Windows 및 Linux에서 AES-CCM 및 AES-GCM의 구현은 OS 라이브러리에서 제공 됩니다.

### <a name="aes-ccm-and-aes-gcm-on-macos"></a>MacOS에서 AES-CCM 및 AES-GCM

MacOS에서 시스템 라이브러리는 타사 코드에 대 한 AES-CCM 또는 AES-GCM을 지원 하지 않으므로 <xref:System.Security.Cryptography.AesCcm> 및 클래스는 <xref:System.Security.Cryptography.AesGcm> OpenSSL를 사용 하 여 지원을 제공 합니다. MacOS의 사용자는 이러한 유형이 작동 하기 위해 적합 한 OpenSSL (라이브러리)를 가져와야 하며, 기본적으로 시스템에서 라이브러리를 로드 하는 경로에 있어야 합니다. 패키지 관리자 (예: Homebrew)에서 OpenSSL를 설치 하는 것이 좋습니다.

`libcrypto.0.9.7.dylib` `libcrypto.0.9.8.dylib` Macos에 포함 된 및 라이브러리는 이전 버전의 OpenSSL에서 제공 되며 사용 되지 않습니다. `libcrypto.35.dylib`, `libcrypto.41.dylib` 및 라이브러리는 `libcrypto.42.dylib` 라이브러리에서 가져온 것 이며 사용 되지 않습니다.

### <a name="aes-ccm-keys-nonces-and-tags"></a>AES-CCM 키, nonce 및 태그

* 키 크기

  AES-CCM은 128, 192 및 256 비트 키와 함께 작동 합니다.

* Nonce 크기

  <xref:System.Security.Cryptography.AesCcm>클래스는 56, 64, 72, 80, 88, 96 및 104 비트 (7, 8, 9, 10, 11, 12 및 13 바이트) nonce 지원 합니다.

* 태그 크기

  <xref:System.Security.Cryptography.AesCcm>클래스는 32, 48, 64, 80, 96, 112 및 128 비트 (4, 8, 10, 12, 14 및 16 바이트) 태그를 만들거나 처리 하는 기능을 지원 합니다.

### <a name="aes-gcm-keys-nonces-and-tags"></a>AES-GCM keys, nonce 및 태그

* 키 크기

  AES GCM은 128, 192 및 256 비트 키를 사용 합니다.

* Nonce 크기

  <xref:System.Security.Cryptography.AesGcm>클래스는 96 비트 (12 바이트) nonce 지원 합니다.

* 태그 크기

  <xref:System.Security.Cryptography.AesGcm>클래스는 96, 104, 112, 120 및 128 비트 (12, 13, 14, 15 및 16 바이트) 태그를 만들거나 처리 하는 기능을 지원 합니다.

## <a name="asymmetric-cryptography"></a>비대칭 암호화

이 섹션에는 다음 하위 섹션이 포함 되어 있습니다.

* [RSA](#rsa)
* [ECDSA](#ecdsa)
* [ECDH](#ecdh)
* [DSA](#dsa)

### <a name="rsa"></a>RSA

RSA (Rivest – Rivest-shamir-adleman – Rivest-shamir-adleman) 키 생성은 OS 라이브러리에 의해 수행 되며 크기 제한 및 성능 특성이 적용 됩니다.

RSA 키 작업은 OS 라이브러리에 의해 수행 되며 로드할 수 있는 키의 유형은 OS 요구 사항에 따라 달라 집니다.

.NET에서는 "raw" (채워지지 않은) RSA 작업을 노출 하지 않습니다.

OS 라이브러리는 암호화 및 암호 해독 패딩에 사용 됩니다. 모든 플랫폼이 동일한 패딩 옵션을 지 원하는 것은 아닙니다.

| 패딩 모드                          | Windows (CNG) | Linux (OpenSSL) | macOS | Windows (CAPI) |
|---------------------------------------|---------------|-----------------|-------|----------------|
| PKCS1 암호화                      | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP                          | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP (SHA256, SHA384, SHA512) | ✔️           | ✔️              | ✔️   | ❌             |
| PKCS1 서명 (MD5, SHA-1)          | ✔️           | ✔️              | ✔️   | ✔️             |
| PKCS1 서명 (SHA-2)               | ✔️           | ✔️              | ✔️   | ⚠️\*           |
| PSS                                   | ✔️           | ✔️              | ✔️   | ❌             |

\*Windows CryptoAPI (CAPI)는 PKCS1 알고리즘을 사용 하 여 서명할 수 있습니다. 하지만 개별 RSA 개체는이를 지원 하지 않는 CSP (암호화 서비스 공급자)에서 로드 될 수 있습니다.

#### <a name="rsa-on-windows"></a>Windows의 RSA

* Windows CryptoAPI (CAPI)는가 사용 될 때마다 사용 됩니다 [`new RSACryptoServiceProvider()`](xref:System.Security.Cryptography.RSACryptoServiceProvider) .
* 를 사용할 때마다 Windows CNG (Cryptography API Next Generation)가 사용 됩니다 [`new RSACng()`](xref:System.Security.Cryptography.RSACng) .
* 에서 반환 되는 개체는 <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> 내부적으로 WINDOWS CNG에 의해 제공 됩니다. 이 Windows CNG의 용도는 구현 세부 정보 이며 변경 될 수 있습니다.
* <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A>의 확장 메서드는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 인스턴스를 반환 합니다 <xref:System.Security.Cryptography.RSACng> . 이러한 용도는 <xref:System.Security.Cryptography.RSACng> 구현 세부 정보 이며 변경 될 수 있습니다.
* <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A>현재의 확장 메서드는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> <xref:System.Security.Cryptography.RSACng> 인스턴스를 선호 하지만 키를 <xref:System.Security.Cryptography.RSACng> 열 수 없는 경우이 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 시도 됩니다. 기본 공급자는 구현 세부 정보 이며 변경 될 수 있습니다.

#### <a name="rsa-native-interop"></a>RSA 네이티브 interop

.NET에서는 프로그램이 .NET 암호화 코드에서 사용 하는 OS 라이브러리와 상호 운용할 수 있도록 형식을 노출 합니다. 관련 된 형식은 플랫폼 간에 변환 되지 않으므로 필요한 경우에만 직접 사용 해야 합니다.

| Type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.RSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup>| ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.RSACng>                   | ✔️     | ❌            | ❌            |
| <xref:System.Security.Cryptography.RSAOpenSsl>               | ❌     | ✔️            | ⚠️<sup>sr-2</sup> |

<sup>1</sup> Macos 및 Linux에서 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 는 기존 프로그램과의 호환성을 위해 사용 될 수 있습니다. 이 경우 명명 된 키를 여는 것과 같이 OS interop를 필요로 하는 모든 메서드는을 throw <xref:System.PlatformNotSupportedException> 합니다.

<sup>2</sup> Macos에서 <xref:System.Security.Cryptography.RSAOpenSsl> OpenSSL가 설치 되 고 동적 라이브러리 로드를 통해 적절 한 dylib crypto을 찾을 수 있는 경우 작동 합니다. 적절 한 라이브러리를 찾을 수 없는 경우 예외가 throw 됩니다.

### <a name="ecdsa"></a>ECDSA

ECDSA (타원 Curve Digital Signature Algorithm) 키 생성은 OS 라이브러리에 의해 수행 되며 크기 제한 및 성능 특성이 적용 됩니다.

ECDSA 키 곡선은 OS 라이브러리에 의해 정의 되며 해당 제한 사항이 적용 됩니다.

| 타원 곡선(Elliptic Curve)                     | 윈도우 10    | Windows 7-8.1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| Brainpool 곡선 (명명 된 곡선) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| 기타 명명 된 곡선                 | ⚠️<sup>sr-2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| 명시적 곡선                    | ✔️           | ❌              | ✔️           | ❌            |
| 명시적으로 내보내기 또는 가져오기       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> Linux 배포판은 모두 동일한 명명 된 곡선을 지원 하지 않습니다.

<sup>2</sup> 명명 된 곡선에 대 한 지원은 windows 10의 windows CNG에 추가 되었습니다. 자세한 내용은 [타원 커브로 명명 된 CNG](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx)를 참조 하세요. Windows 7의 세 가지 곡선을 제외 하 고 이전 버전의 Windows에서는 명명 된 곡선을 사용할 수 없습니다.

<sup>3</sup> 명시적 곡선 매개 변수를 사용한 내보내기는 macos 또는 이전 버전의 Windows에서 사용할 수 없는 OS 라이브러리를 지원 해야 합니다.

#### <a name="ecdsa-native-interop"></a>ECDSA 네이티브 Interop

.NET에서는 프로그램이 .NET 암호화 코드에서 사용 하는 OS 라이브러리와 상호 운용할 수 있도록 형식을 노출 합니다. 관련 된 형식은 플랫폼 간에 변환 되지 않으므로 필요한 경우에만 직접 사용 해야 합니다.

| Type                                             | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDsaCng>     | ✔️     | ❌    | ❌    |
| <xref:System.Security.Cryptography.ECDsaOpenSsl> | ❌     | ✔️    | ⚠️\*  |

\*MacOS에서 <xref:System.Security.Cryptography.ECDsaOpenSsl> OpenSSL가 시스템에 설치 되어 있고 동적 라이브러리 로드를 통해 적절 한 dylib crypto을 찾을 수 있는 경우 작동 합니다. 적절 한 라이브러리를 찾을 수 없는 경우 예외가 throw 됩니다.

### <a name="ecdh"></a>ECDH

ECDH (타원 Curve Diffie-hellman) 키 생성은 OS 라이브러리에 의해 수행 되며 크기 제한 및 성능 특성이 적용 됩니다.

<xref:System.Security.Cryptography.ECDiffieHellman>클래스가 ECDH 계산의 "raw" 값을 반환 하지 않습니다. 반환 된 데이터는 모두 키 파생 함수를 기준으로 합니다.

* 해시 (Z)
* HASH (앞에 | | 추가 Z | | 추가할
* HMAC (키, Z)
* HMAC (키, 앞에 | | Z | | 추가할
* HMAC (Z, Z)
* HMAC (Z, 앞에 | | Z | | 추가할
* Tls11Prf (레이블, 초기값)

ECDH 키 곡선은 OS 라이브러리에 의해 정의 되며 해당 제한 사항이 적용 됩니다.

| 타원 곡선(Elliptic Curve)                     | 윈도우 10    | Windows 7-8.1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| brainpool 곡선 (명명 된 곡선) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| 기타 명명 된 곡선                 | ⚠️<sup>sr-2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| 명시적 곡선                    | ✔️           | ❌              | ✔️           | ❌            |
| 명시적으로 내보내기 또는 가져오기       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> Linux 배포판은 모두 동일한 명명 된 곡선을 지원 하지 않습니다.

<sup>2</sup> 명명 된 곡선에 대 한 지원은 windows 10의 windows CNG에 추가 되었습니다. 자세한 내용은 [타원 커브로 명명 된 CNG](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx)를 참조 하세요. Windows 7의 세 가지 곡선을 제외 하 고 이전 버전의 Windows에서는 명명 된 곡선을 사용할 수 없습니다.

<sup>3</sup> 명시적 곡선 매개 변수를 사용한 내보내기는 macos 또는 이전 버전의 Windows에서 사용할 수 없는 OS 라이브러리를 지원 해야 합니다.

#### <a name="ecdh-native-interop"></a>ECDH 네이티브 interop

.NET에서는 프로그램이 .NET에서 사용 하는 OS 라이브러리와 상호 운용할 수 있도록 형식을 노출 합니다. 관련 된 형식은 플랫폼 간에 변환 되지 않으므로 필요한 경우에만 직접 사용 해야 합니다.

| Type                                                       | Windows | Linux | macOS |
|------------------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDiffieHellmanCng>     | ✔️     | ❌    | ❌   |
| <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> | ❌     | ✔️    | ⚠️\* |

\*MacOS에서 <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> OpenSSL가 설치 되 고 동적 라이브러리 로드를 통해 적절 한 dylib crypto을 찾을 수 있는 경우 작동 합니다. 적절 한 라이브러리를 찾을 수 없는 경우 예외가 throw 됩니다.

### <a name="dsa"></a>DSA

DSA (디지털 서명 알고리즘) 키 생성은 시스템 라이브러리에 의해 수행 되며 크기 제한 및 성능 특성이 적용 됩니다.

| 함수                      | Windows CNG | Linux | macOS         | Windows CAPI |
|-------------------------------|-------------|-------|---------------|--------------|
| 키 만들기 (<= 1024 비트)   | ✔️         | ✔️    | ❌            | ✔️           |
| 키 생성 (> 1024 비트)    | ✔️         | ✔️    | ❌            | ❌            |
| 키 로드 중 (<= 1024 비트)   | ✔️         | ✔️    | ✔️            | ✔️           |
| 키 로드 (> 1024 비트)    | ✔️         | ✔️    | ⚠️\*          | ❌            |
| FIPS 186-2                    | ✔️         | ✔️    | ✔️            | ✔️           |
| FIPS 186-3 (SHA-2 서명) | ✔️         | ✔️    | ❌            | ❌            |

\*macOS는 1024 비트 보다 큰 DSA 키를 로드 하지만 해당 키의 동작이 정의 되지 않습니다. FIPS 186-3에 따라 동작 하지 않습니다.

#### <a name="dsa-on-windows"></a>Windows의 DSA

* Windows CryptoAPI (CAPI)는가 사용 될 때마다 사용 됩니다 [`new DSACryptoServiceProvider()`](xref:System.Security.Cryptography.DSACryptoServiceProvider) .
* 를 사용할 때마다 Windows CNG (Cryptography API Next Generation)가 사용 됩니다 [`new DSACng()`](xref:System.Security.Cryptography.DSACng) .
* 에서 반환 되는 개체는 <xref:System.Security.Cryptography.DSA.Create%2A?displayProperty=nameWithType> 내부적으로 WINDOWS CNG에 의해 제공 됩니다. 이 Windows CNG의 용도는 구현 세부 정보 이며 변경 될 수 있습니다.
* <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A>의 확장 메서드는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 인스턴스를 반환 합니다 <xref:System.Security.Cryptography.DSACng> . 이러한 용도는 <xref:System.Security.Cryptography.DSACng> 구현 세부 정보 이며 변경 될 수 있습니다.
* <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A>의 확장 메서드는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> <xref:System.Security.Cryptography.DSACng> 인스턴스를 선호 하지만 키를 <xref:System.Security.Cryptography.DSACng> 열 수 없는 경우이 <xref:System.Security.Cryptography.DSACryptoServiceProvider> 시도 됩니다.  기본 공급자는 구현 세부 정보 이며 변경 될 수 있습니다.

#### <a name="dsa-native-interop"></a>DSA 네이티브 interop

.NET에서는 프로그램이 .NET 암호화 코드에서 사용 하는 OS 라이브러리와 상호 운용할 수 있도록 형식을 노출 합니다. 관련 된 형식은 플랫폼 간에 변환 되지 않으므로 필요한 경우에만 직접 사용 해야 합니다.

| Type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.DSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup> | ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.DSACng>                   | ✔️     | ❌             | ❌            |
| <xref:System.Security.Cryptography.DSAOpenSsl>               | ❌      | ✔️            | ⚠️<sup>sr-2</sup> |

<sup>1</sup> Macos 및 Linux에서 <xref:System.Security.Cryptography.DSACryptoServiceProvider> 는 기존 프로그램과의 호환성을 위해 사용 될 수 있습니다. 이 경우 명명 된 키를 여는 것과 같이 시스템 interop를 필요로 하는 모든 메서드는을 throw <xref:System.PlatformNotSupportedException> 합니다.

<sup>2</sup> Macos에서 <xref:System.Security.Cryptography.DSAOpenSsl> OpenSSL가 설치 되 고 동적 라이브러리 로드를 통해 적절 한 dylib crypto을 찾을 수 있는 경우 작동 합니다. 적절 한 라이브러리를 찾을 수 없는 경우 예외가 throw 됩니다.

## <a name="x509-certificates"></a>X.509 인증서

.NET의 x.509 인증서에 대 한 대부분의 지원은 OS 라이브러리에서 제공 됩니다. 인증서를 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> <xref:System.Security.Cryptography.X509Certificates.X509Certificate> .net의 또는 인스턴스로 로드 하려면 기본 OS 라이브러리에서 인증서를 로드 해야 합니다.

### <a name="read-a-pkcs12pfx"></a>PKCS12/PFX 읽기

| 시나리오                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ✔️   |
| 인증서 1 개, 개인 키 없음              | ✔️     | ✔️    | ✔️   |
| 개인 키가 있는 인증서 1 개            | ✔️     | ✔️    | ✔️   |
| 여러 인증서, 개인 키 없음       | ✔️     | ✔️    | ✔️   |
| 여러 인증서, 하나의 개인 키       | ✔️     | ✔️    | ✔️   |
| 여러 인증서, 여러 개인 키 | ✔️     | ⚠️\*  | ✔️   |

\*.NET 5 preview 릴리스에서 사용할 수 있습니다.

### <a name="write-a-pkcs12pfx"></a>PKCS12/PFX 작성

| 시나리오                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ⚠️\* |
| 인증서 1 개, 개인 키 없음              | ✔️     | ✔️    | ⚠️\* |
| 개인 키가 있는 인증서 1 개            | ✔️     | ✔️    | ✔️   |
| 여러 인증서, 개인 키 없음       | ✔️     | ✔️    | ⚠️\* |
| 여러 인증서, 하나의 개인 키       | ✔️     | ✔️    | ✔️   |
| 여러 인증서, 여러 개인 키 | ✔️     | ⚠️\*  | ✔️   |
| 임시 로드                            | ✔️     | ✔️    | ⚠️\* |

\*.NET 5 preview 릴리스에서 사용할 수 있습니다.

macOS는 키 집합 개체가 없는 인증서 개인 키를 로드할 수 없습니다 .이 경우 디스크에 써야 합니다. Keychains은 PFX를 로드 하기 위해 자동으로 생성 되며 더 이상 사용 되지 않을 때 삭제 됩니다. 옵션은 <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> 개인 키를 디스크에 쓰지 않아야 함을 의미 하므로 macOS에서 해당 플래그를 어설션하 면이 발생 <xref:System.PlatformNotSupportedException> 합니다.

### <a name="write-a-pkcs7-certificate-collection"></a>PKCS7 인증서 컬렉션 작성

Windows 및 Linux 모두 DER로 인코딩된 PKCS7 blob을 내보냅니다. macOS는 길이가 무제한 인 CER 인코딩된 PKCS7 blob을 내보냅니다.

### <a name="x509store"></a>X509Store

Windows에서 클래스는 <xref:System.Security.Cryptography.X509Certificates.X509Store> Windows 인증서 저장소 api를 표현한 것입니다. 이러한 Api는 .NET Framework 에서처럼 .NET Core 및 .NET 5에서 동일 하 게 작동 합니다.

Linux에서 클래스는 <xref:System.Security.Cryptography.X509Certificates.X509Store> 시스템 신뢰 결정 (읽기 전용), 사용자 신뢰 결정 (읽기-쓰기) 및 사용자 키 저장소 (읽기-쓰기)의 프로젝션입니다.

MacOS에서 클래스는 <xref:System.Security.Cryptography.X509Certificates.X509Store> 시스템 신뢰 결정 (읽기 전용), 사용자 신뢰 결정 (읽기 전용) 및 사용자 키 저장소 (읽기-쓰기)의 프로젝션입니다.

다음 표에서는 각 플랫폼에서 지원 되는 시나리오를 보여 줍니다. 지원 되지 않는 시나리오 ( ❌ 테이블)의 경우 <xref:System.Security.Cryptography.CryptographicException> 이 throw 됩니다.

#### <a name="the-my-store"></a>내 저장소

| 시나리오                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Open CurrentUser\My (ReadOnly)                   | ✔️     | ✔️    | ✔️   |
| Open CurrentUser\My (ReadWrite)                  | ✔️     | ✔️    | ✔️   |
| Open CurrentUser\My (ExistingOnly)               | ✔️     | ⚠️    | ✔️   |
| LocalMachine\My 열기                             | ✔️     | ❌    | ✔️   |

Linux에서 저장소는 처음 쓸 때 만들어지며, 기본적으로 사용자 저장소는 없으므로 `CurrentUser\My` 를 사용 하 여 열 `ExistingOnly` 수 없게 됩니다.

MacOS에서 저장소는 `CurrentUser\My` 기본적으로 사용자의 기본 키 집합입니다 `login.keychain` . `LocalMachine\My`저장소가 인 경우 `System.keychain`

#### <a name="the-root-store"></a>루트 저장소

| 시나리오                              | Windows | Linux | macOS           |
|---------------------------------------|---------|-------|-----------------|
| Open CurrentUser\Root (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Open CurrentUser\Root (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Open CurrentUser\Root (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (ReadOnly 인 경우) |
| Open LocalMachine\Root (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Open LocalMachine\Root (ReadWrite)    | ✔️     | ❌    | ❌              |
| Open LocalMachine\Root (ExistingOnly) | ✔️     | ⚠️    | ✔️ (ReadOnly 인 경우) |

Linux에서 저장소는 `LocalMachine\Root` OpenSSL의 기본 경로에 있는 CA 번들의 해석입니다.

MacOS에서 저장소는 `CurrentUser\Root` `SecTrustSettings` 사용자 트러스트 도메인의 결과를 해석 합니다. `LocalMachine\Root`저장소는 `SecTrustSettings` 관리 및 시스템 신뢰 도메인에 대 한 결과를 해석 합니다.

#### <a name="the-intermediate-store"></a>중간 저장소

| 시나리오                                      | Windows | Linux | macOS           |
|-----------------------------------------------|---------|-------|-----------------|
| Open CurrentUser\Intermediate (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Open CurrentUser\Intermediate (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Open CurrentUser\Intermediate (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (ReadOnly 인 경우) |
| Open LocalMachine\Intermediate (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Open LocalMachine\Intermediate (ReadWrite)    | ✔️     | ❌    | ❌              |
| Open LocalMachine\Intermediate (ExistingOnly) | ✔️     | ⚠️    | ✔️ (ReadOnly 인 경우) |

Linux에서 저장소는 `CurrentUser\Intermediate` 성공한 X509Chain 빌드에 대 한 권한 정보 액세스 레코드에 의해 중간 ca를 다운로드 하는 경우 캐시로 사용 됩니다. `LocalMachine\Intermediate`저장소는 OpenSSL의 기본 경로에 있는 CA 번들의 해석입니다.

#### <a name="the-disallowed-store"></a>허용 되지 않는 저장소

| 시나리오                                    | Windows | Linux | macOS           |
|---------------------------------------------|---------|-------|-----------------|
| Open CurrentUser\Disallowed (ReadOnly)      | ✔️     | ⚠️    | ✔️             |
| Open CurrentUser\Disallowed (ReadWrite)     | ✔️     | ⚠️    | ❌              |
| Open CurrentUser\Disallowed (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (ReadOnly 인 경우) |
| Open LocalMachine\Disallowed (ReadOnly)     | ✔️     | ❌    | ✔️             |
| Open LocalMachine\Disallowed (ReadWrite)    | ✔️     | ❌    | ❌              |
| Open LocalMachine\Disallowed (ExistingOnly) | ✔️     | ❌    | ✔️ (ReadOnly 인 경우) |

Linux에서 저장소는 `Disallowed` 체인을 빌드하는 데 사용 되지 않으며, 콘텐츠를 추가 하려고 시도 하면이 발생 <xref:System.Security.Cryptography.CryptographicException> 합니다. <xref:System.Security.Cryptography.CryptographicException> `Disallowed` 이미 콘텐츠를 가져온 경우 저장소를 열 때이 throw 됩니다.

MacOS에서 CurrentUser\Disallowed 및 LocalMachine\Disallowed 저장소는 신뢰가로 설정 된 인증서에 대 한 적절 한 SecTrustSettings 결과를 해석 합니다 `Always Deny` .

#### <a name="nonexistent-store"></a>존재 하지 않는 저장소

| 시나리오                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| 존재 하지 않는 저장소 열기 (ExistingOnly)           | ❌     | ❌     | ❌    |
| 존재 하지 않는 저장소 열기 (ReadWrite)  | ✔️     | ✔️     | ⚠️   |
| 존재 하지 않는 저장소 열기 (ReadWrite) | ✔️     | ❌     | ❌    |

MacOS에서 X509Store API를 사용 하 여 사용자 지정 저장소 만들기는 위치에 대해서만 지원 됩니다 `CurrentUser` . 사용자의 키 집합 디렉터리에 암호 없이 새 키 집합을 만듭니다 (*~/Er/wvkeykeyl*). 암호를 사용 하 여 키 집합을 만들려면 P/Invoke를 사용할 수 있습니다 `SecKeychainCreate` . 마찬가지로를 `SecKeychainOpen` 사용 하 여 다른 위치에서 keykey를 열 수 있습니다. 결과를 `IntPtr` 에 전달 하 여 [`new X509Store(IntPtr)`](xref:System.Security.Cryptography.X509Certificates.X509Store.%23ctor(System.IntPtr)) 현재 사용자의 사용 권한에 따라 읽기/쓰기 가능 저장소를 가져올 수 있습니다.

### <a name="x509chain"></a>X509Chain

macOS는 오프 라인 CRL 사용률을 지원 하지 않으므로 `X509RevocationMode.Offline` 는로 처리 됩니다 `X509RevocationMode.Online` .

macOS는 CRL (인증서 해지 목록)/a p (온라인 인증서 상태 프로토콜)/AIA (기관 정보 액세스)를 다운로드 하는 동안 사용자가 시작한 시간 제한을 지원 하지 않으므로 `X509ChainPolicy.UrlRetrievalTimeout` 가 무시 됩니다.

## <a name="additional-resources"></a>추가 자료

* [.NET 암호화 모델](cryptography-model.md)
* [.NET 암호화 서비스](cryptographic-services.md)
