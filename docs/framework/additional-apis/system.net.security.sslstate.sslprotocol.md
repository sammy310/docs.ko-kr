---
title: SslState. Sslstate 속성 (시스템 .Net. 보안)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847249"
---
# <a name="sslstatesslprotocol-property"></a>SslState. Sslstate 속성

SSL 프로토콜 버전을 가져옵니다.

## <a name="syntax"></a>구문

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>속성 값

<xref:System.Security.Authentication.SslProtocols>  
SSL 프로토콜 버전을 지정 하는 열거형 값의 비트 조합입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> `SslState.SslProtocol` 속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net.Security>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
