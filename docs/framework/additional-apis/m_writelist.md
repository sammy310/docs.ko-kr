---
title: 연결.m_WriteList 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
ms.openlocfilehash: 6c60831ddf23ce8ac9afcf244383d24732c3ef8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155839"
---
# <a name="connectionm_writelist-field"></a>연결.m\_쓰기 목록 필드

`Connection.m_WriteList`은 <xref:System.Collections.ArrayList> HTTP를 통해 전송되도록 큐에 대기중인 개체의 <xref:System.Net.HttpWebRequest> 입니다.

## <a name="syntax"></a>구문
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> 필드는 `Connection.m_WriteList` 비공개이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 필드의 사용을 지원하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:**<xref:System.Net>

**어셈블리:** 시스템(시스템.dll)

**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.
