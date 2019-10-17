---
title: PrepForRemoting 메서드 (System)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405899"
---
# <a name="exceptionprepforremoting-method"></a>PrepForRemoting 메서드

클라이언트 호출 사이트에서 예외가 다시 throw 되기 전에 서버 쪽 스택 추적을 메시지에 추가 하 여 유지 합니다.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>반환 값

<xref:System.Exception>  
이 <xref:System.Exception> 인스턴스입니다.

## <a name="remarks"></a>주의

> [!WARNING]
> @No__t-0 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System>

**어셈블리:** mscorlib.dll (mscorlib.dll)

**.NET Framework 버전:** 1.0부터 사용할 수 있습니다.
