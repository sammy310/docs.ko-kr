---
title: M_WriteList 필드
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120021"
---
# <a name="connectionm_writelist-field"></a>연결 m\_WriteList 필드

`Connection.m_WriteList`는 HTTP를 통해 전송 되기 위해 큐에 대기 되는 <xref:System.Net.HttpWebRequest> 개체의 <xref:System.Collections.ArrayList>입니다.

## <a name="syntax"></a>구문
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> `Connection.m_WriteList` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.
> 
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
