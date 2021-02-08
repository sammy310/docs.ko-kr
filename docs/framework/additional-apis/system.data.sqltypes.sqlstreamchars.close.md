---
description: '자세한 정보: SqlStreamChars. Close 메서드'
title: SqlStreamChars. Close 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 27f2ea6e288d166f3b63979a83a1cf80eeced334
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782379"
---
# <a name="sqlstreamcharsclose-method"></a>SqlStreamChars. Close 메서드

현재 스트림을 닫고 스트림과 연결 된 시스템 리소스를 모두 해제 합니다. 이 메서드를 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다. SQL Server에서 사용 하기 위한 것입니다. 다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

```csharp
public virtual void Close ();
```

## <a name="remarks"></a>설명

> [!WARNING]
> `SqlStreamChars.Close`메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.Data(System.Data.dll에서)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
