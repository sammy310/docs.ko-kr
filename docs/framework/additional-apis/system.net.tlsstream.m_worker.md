---
description: '다음에 대 한 자세한 정보: TlsStream.m_Worker 필드'
title: TlsStream.m_Worker 필드 (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.TlsStream.m_Worker
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: d929b0b1949bc1902425c016bfd770d4c66a3257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699521"
---
# <a name="tlsstreamm_worker-field"></a>TlsStream.m_Worker 필드

SSL 스트림의 상태를 나타냅니다.

## <a name="syntax"></a>Syntax

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a>필드 값

`System.Net.Security.SslState`  
SSL 스트림의 상태입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `TlsStream.m_Worker`필드는 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
