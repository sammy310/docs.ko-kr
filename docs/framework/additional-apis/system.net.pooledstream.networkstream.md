---
description: '자세한 정보: PooledStream. NetworkStream 속성'
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
ms.openlocfilehash: 8a4f1d6bd9297028e763ef73bf96f85cbbfdafd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699638"
---
# <a name="pooledstreamnetworkstream-property"></a>PooledStream. NetworkStream 속성

소켓의 네트워크 스트림을 가져오거나 설정 합니다 `PooledStream` .

## <a name="syntax"></a>Syntax

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>속성 값

<xref:System.Net.Sockets.NetworkStream>  
소켓의 네트워크 스트림입니다 `PooledStream` .

## <a name="remarks"></a>설명

> [!WARNING]
> `PooledStream.NetworkStream`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
