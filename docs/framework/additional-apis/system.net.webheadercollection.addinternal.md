---
description: 다음에 대해 자세히 알아보세요. WebHeaderCollection. AddInternal 메서드
title: WebHeaderCollection. AddInternal 메서드 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7bc84f84e6656dba5230b627fe9decfc4e0b4746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699482"
---
# <a name="webheadercollectionaddinternal-method"></a>WebHeaderCollection. AddInternal 메서드

검사를 무시 하 고 컬렉션에 지정 된 이름과 값을 가진 새 헤더를 추가 합니다.

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> 이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="parameters"></a>매개 변수

- `name` <xref:System.String>

  헤더의 이름입니다.

- `value` <xref:System.String>

  헤더의 값입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
