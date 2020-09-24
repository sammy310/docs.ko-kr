---
ms.openlocfilehash: 6ffd4147a99a59d0a2e50d3f88279608e286aed1
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90680017"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>CryptoStream.Dispose는 쓰는 경우에만 최종 블록을 변환함

`CryptoStream` 연산을 완료하기 위해 사용되는 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> 메서드는 읽을 때 더 이상 최종 블록을 변환하려고 시도하지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 사용자가 <xref:System.Security.Cryptography.CryptoStreamMode.Read> 모드에서 <xref:System.Security.Cryptography.CryptoStream>을 사용할 때 불완전한 읽기를 수행하는 경우 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> 메서드가 예외를 throw할 수 있습니다(예: 패딩이 포함된 AES를 사용할 경우). 최종 블록을 변환하려고 시도했지만 데이터가 불완전하기 때문에 예외가 throw되었습니다.

.NET Core 3.0 이상 버전에서 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A>는 읽을 때 더 이상 최종 블록을 변환(불완전한 읽기가 가능함)하려고 시도하지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

이렇게 변경하면 네트워크 작업이 취소되는 경우 예외를 catch하지 않고도 암호화 스트림에서 불완전한 읽기가 가능합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

대부분의 앱은 이 변경의 영향을 받지 않습니다.

불완전한 읽기 발생 시 애플리케이션이 이전에 예외를 catch했다면 해당 `catch` 블록을 삭제할 수 있습니다.
해시 시나리오에서 앱이 최종 블록의 변환을 사용한 경우 삭제하기 전에 전체 스트림을 읽었는지 확인해야 할 수도 있습니다.

#### <a name="category"></a>범주

암호화

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
