---
title: 연결. m_WriteList 필드
description: .NET의 m_WriteList 필드 연결에 대 한 정보를 가져옵니다. 이 ArrayList 필드에는 HTTP를 통해 전송 되기 위해 큐에 대기 된 HttpWebRequest 개체가 있습니다.
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
ms.openlocfilehash: a627cb062036e3ab098c2d6e97f9a77ebfa75a33
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989595"
---
# <a name="connectionm_writelist-field"></a>연결. m \_ writelist 필드

`Connection.m_WriteList`HTTP를 <xref:System.Collections.ArrayList> <xref:System.Net.HttpWebRequest> 통해 전송 되기 위해 큐에 대기 중인 개체의입니다.

## <a name="syntax"></a>구문
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> `Connection.m_WriteList`필드는 private 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
