---
title: '호환성이 손상되는 변경: 암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.'
description: 암호화 추상화에 대한 매개 변수가 없는 Create() 오버로드가 사용되지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/16/2020
ms.openlocfilehash: b75f3568317d1db8ae1bb629f760aaec7e69776a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256792"
---
# <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a>암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.

암호화 추상화에 대한 매개 변수가 없는 `Create()` 오버로드는 .NET 5.0부터 경고로 사용되지 않습니다.

## <a name="change-description"></a>변경 내용 설명

.NET Framework 2.0 - 4.8에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 다른 알고리즘을 반환하도록 구성할 수 있습니다. 예를 들어 .NET Framework 4.8의 기본 설치에서 매개 변수가 없는 정적 메서드 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>은 다음 코드 조각과 같이 SHA1 알고리즘의 인스턴스를 반환합니다.

**.NET Framework만 해당**

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

프로그래밍 방식으로 `CryptoConfig`를 호출할 필요 없이 [머신 전체 구성](../../../../framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)을 사용하여 기본 알고리즘을 변경할 수도 있습니다.

.NET Core 2.0 - 3.1에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

.NET 5 이상 버전에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 사용되지 않는 것으로 표시되고 ID `SYSLIB0007`을 사용하여 컴파일 시간 경고를 생성합니다. 런타임 시 이러한 메서드는 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

이는 컴파일 시간 전용 변경입니다. .NET Core의 이전 버전에서 런타임 변경은 없습니다.

> [!NOTE]
>
> - `Create()` 메서드의 매개 변수가 없는 오버로드만 사용되지 않습니다. 매개 변수가 있는 오버로드는 더 이상 사용되지 않으며 예상대로 계속 작동합니다.
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - *특정* 알고리즘 패밀리(추상화 아님)의 매개 변수가 없는 오버로드는 더 이상 사용되지 않으며 예상대로 계속 작동합니다.
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

## <a name="reason-for-change"></a>변경 이유

레거시 시스템이 적절한 암호화 민첩성을 허용하지 않기 때문에 .NET Framework에 있는 암호화 구성 시스템은 더 이상 .NET Core 및 .NET 5.0+에 존재하지 않습니다. .NET의 이전 버전과의 호환성 요구 사항은 또한 프레임워크가 암호화의 발전을 따라 잡기 위해 특정 암호화 API를 업데이트하는 것을 금지합니다. 예를 들어, <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> 메서드는 SHA-1 해시 알고리즘이 최첨단이었을 때 .NET Framework 1.0에서 도입되었습니다. 그 후 20년이 지났고 이제 SHA-1이 중단된 것으로 간주되지만 다른 알고리즘을 반환하도록 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>을 변경할 수 없습니다. 그렇게 하면 사용하는 애플리케이션에 허용할 수 없는 주요 변경 사항이 발생합니다.

모범 사례에 따르면 암호화 기본 요소(예: AES, SHA-* 및 RSA)를 사용하는 라이브러리는 이러한 기본 요소를 사용하는 방법을 완전히 제어해야 합니다. 미래를 대비해야 하는 애플리케이션은 이러한 기본 요소를 래핑하고 키 관리 및 암호화 민첩성 기능을 추가하는 상위 레벨 라이브러리를 활용해야 합니다. 이러한 라이브러리는 종종 호스팅 환경에서 제공됩니다. 한 가지 예는 호출 애플리케이션을 대신하여 이러한 문제를 처리하는 [ASP.NET의 데이터 보호 라이브러리](/aspnet/core/security/data-protection/)입니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- 권장되는 조치 과정은 현재 사용되지 않는 API에 대한 호출을 특정 알고리즘(예: <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>)에 대한 팩터리 메소드 호출로 대체하는 것입니다. 이렇게 하면 인스턴스화되는 알고리즘을 완전히 제어할 수 있습니다.

- 현재 사용되지 않는 API를 사용하는 .NET Framework 앱에서 생성된 기존 페이로드와의 호환성을 유지해야 하는 경우 다음 표에 제안된 대체 항목을 사용합니다. 표는 .NET Framework 기본 알고리즘에서 해당 .NET 5+까지의 매핑을 제공합니다.

  | .NET Framework | .NET Core/.NET 5.0+ 호환 대체 항목 | 설명 |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | SHA-1 알고리즘은 중단된 것으로 간주합니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | 대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | 대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- 더 이상 사용되지 않는 매개 변수가 없는 `Create()` 오버로드를 계속 호출해야 하는 경우 코드에서 `SYSLIB0007` 경고를 표시하지 않을 수 있습니다.

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  프로젝트 파일에서 경고를 표시하지 않을 수도 있습니다. 이렇게 하면 프로젝트 내의 모든 소스 파일에 대한 경고를 사용할 수 없게 됩니다.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > `SYSLIB0007`을 표시하지 않으면 여기에 나열된 암호화 API에 대한 삭제 경고만 사용하지 않게 됩니다. 다른 경고를 사용하지 않도록 설정하는 것은 아닙니다. 또한 경고를 표시하지 않더라도 사용되지 않는 API는 런타임 시 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

### Category

- Cryptography

-->
