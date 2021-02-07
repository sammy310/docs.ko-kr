---
description: '자세한 정보: SslState. Sslstate 속성'
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
ms.openlocfilehash: b0b9bebf23fcd8d643d06f1cff10c260c77a7c08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699625"
---
# <a name="sslstatesslprotocol-property"></a>SslState. Sslstate 속성

SSL 프로토콜 버전을 가져옵니다.

## <a name="syntax"></a>Syntax

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>속성 값

<xref:System.Security.Authentication.SslProtocols>  
SSL 프로토콜 버전을 지정 하는 열거형 값의 비트 조합입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `SslState.SslProtocol`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net.Security>

**어셈블리:** 시스템 (System.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
