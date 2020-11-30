---
title: SYSLIB0007 경고
description: 컴파일 시간 경고 SYSLIB0007을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: db7150fa3e3c566adf110034734e068fac079c6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685021"
---
# <a name="syslib0007-default-implementations-of-cryptography-algorithms-not-supported"></a>SYSLIB0007: 암호화 알고리즘의 기본 구현이 지원되지 않음

.NET Framework의 암호화 구성 시스템은 적절한 암호화 민첩성을 허용하지 않으며 .NET Core 및 .NET 5+에 존재하지 않습니다. .NET의 이전 버전과의 호환성 요구 사항은 또한 프레임워크가 암호화의 발전을 따라 잡기 위해 특정 암호화 API를 업데이트하는 것을 금지합니다. 따라서 다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0007` 경고가 생성됩니다.

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

## <a name="workarounds"></a>해결 방법

- 권장되는 조치 과정은 현재 사용되지 않는 API에 대한 호출을 특정 알고리즘(예: <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>)에 대한 팩터리 메소드 호출로 대체하는 것입니다. 이렇게 하면 인스턴스화되는 알고리즘을 완전히 제어할 수 있습니다.

- 현재 사용되지 않는 API를 사용하는 .NET Framework 앱에서 생성된 기존 페이로드와의 호환성을 유지해야 하는 경우 다음 표에 제안된 대체 항목을 사용합니다. 표는 .NET Framework 기본 알고리즘에서 해당 .NET 5+까지의 매핑을 제공합니다.

  | .NET Framework | .NET Core/.NET 5.0+ 호환 대체 항목 | 설명 |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | SHA-1 알고리즘은 중단된 것으로 간주합니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | 대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | 대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다. 가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다. 자세한 지침은 보안 관리자에게 문의하세요. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>추가 정보

- [암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.](cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)
