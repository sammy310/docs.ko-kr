---
description: '자세한 정보: SqlStreamChars. IsNull 속성'
title: SqlStreamChars. IsNull 속성 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b1408a8ba9cd1c38f73d5fa6b818f441d6223bc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791922"
---
# <a name="sqlstreamcharsisnull-property"></a>SqlStreamChars. IsNull 속성

파생 클래스에서 재정의 되는 경우 스트림이 인지 여부를 나타내는 값을 가져옵니다 `null` . 이 속성을 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다. SQL Server에서 사용 하기 위한 것입니다. 다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

## <a name="syntax"></a>Syntax

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>속성 값

<xref:System.Boolean>\
`true` 스트림이 이면 `null` 이 고, 그렇지 않으면 `false` 입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `SqlStreamChars.IsNull`속성은 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.Data(System.Data.dll에서)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
