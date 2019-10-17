---
title: SqlStreamChars. Write (Char [], Int32, Int32) 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395581"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>SqlStreamChars. Write (Char [], Int32, Int32) 메서드

파생 클래스에서 재정의 되는 경우 현재 스트림에 문자 시퀀스를 쓰고 쓴 문자 수 만큼이 스트림 내의 현재 위치를 앞으로 이동 합니다. 이 메서드를 포함 하는 어셈블리에는 SQLAccess .dll과의 friend 관계가 있습니다. SQL Server에서 사용 하기 위한 것입니다. 다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>매개 변수

`buffer`  
쓸 문자 배열입니다.

`offset`  
원점을 기준으로 하는 오프셋입니다.

`count`  
현재 스트림에 쓸 문자 수입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> @No__t-0 메서드는 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법 작성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.object (system.string)입니다.

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
