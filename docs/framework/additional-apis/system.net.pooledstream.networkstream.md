---
title: PooledStream. NetworkStream 속성 (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847231"
---
# <a name="pooledstreamnetworkstream-property"></a>PooledStream. NetworkStream 속성

`PooledStream` 소켓의 네트워크 스트림을 가져오거나 설정 합니다.

## <a name="syntax"></a>구문

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>속성 값

<xref:System.Net.Sockets.NetworkStream>  
`PooledStream` 소켓의 네트워크 스트림입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> `PooledStream.NetworkStream` 속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
