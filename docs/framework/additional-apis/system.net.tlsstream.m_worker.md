---
title: TlsStream 필드 (System.Net)
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
ms.openlocfilehash: d335820d13e1e15e054e824a284615cdbf6c2094
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847243"
---
# <a name="tlsstreamm_worker-field"></a>TlsStream. m_Worker 필드

SSL 스트림의 상태를 나타냅니다.

## <a name="syntax"></a>구문

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a>필드 값

`System.Net.Security.SslState`  
SSL 스트림의 상태입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> `TlsStream.m_Worker` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
