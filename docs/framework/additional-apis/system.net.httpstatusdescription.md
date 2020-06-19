---
title: HttpStatusDescription 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990477"
---
# <a name="httpstatusdescription-class"></a>HttpStatusDescription 클래스

표준 HTTP 상태 설명을 제공 합니다. 이 클래스는 상속할 수 없습니다.

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="get-method"></a>Get 메서드

지정 된 HTTP 상태 코드와 연결 된 설명을 반환 합니다.

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a>매개 변수

`code` <xref:System.Int32>

HTTP 상태 코드입니다 (예:) `404` .

### <a name="return-value"></a>반환 값

<xref:System.String?displayProperty=nameWithType>

HTTP 상태 설명입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
