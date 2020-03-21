---
title: 서비스포인트관리자.s_ServicePointTable 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155818"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>서비스포인트관리자서비스포인트테이블필드\_

`ServicePointManager.s_ServicePointTable`<xref:System.Collections.Hashtable> 은 에서 활성 HTTP 연결(들)<xref:System.Net.ServicePoint>목록을 포함하는 을 <xref:System.AppDomain>입니다.

## <a name="syntax"></a>구문
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> 필드는 `ServicePointManager.s_ServicePointTable` 비공개이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 필드의 사용을 지원하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:**<xref:System.Net>

**어셈블리:** 시스템(시스템.dll)

**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.
