---
title: SqlStreamChars.Length 속성 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c2ef66fa493512e1fa062e22858ea251ced39453
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634143"
---
# <a name="sqlstreamcharslength-property"></a>SqlStreamChars.Length Property

파생된 클래스에서 재정의 되 면 현재 스트림의 길이 가져옵니다. 이 속성을 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다. SQL Server에서 사용할 것입니다. 다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

## <a name="syntax"></a>구문

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>속성 값

<xref:System.Int64>\
스트림의 길이입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `SqlStreamChars.Length` 속성은 전용 이며 코드에서 직접 사용할 하려고 하지 않습니다.
>
> Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.Data (System.Data.dll)

**.NET framework 버전:** 2.0부터 사용할 수 있습니다.