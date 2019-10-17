---
title: SqlStreamChars. Length 속성 (SqlTypes)
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
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395602"
---
# <a name="sqlstreamcharslength-property"></a>SqlStreamChars. Length 속성

파생 클래스에서 재정의 되는 경우 현재 스트림의 길이를 가져옵니다. 이 속성을 포함 하는 어셈블리에는 SQLAccess .dll과의 friend 관계가 있습니다. SQL Server에서 사용 하기 위한 것입니다. 다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

## <a name="syntax"></a>구문

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>속성 값

<xref:System.Int64>\
스트림의 길이입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> @No__t-0 속성은 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.object (system.string)입니다.

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
