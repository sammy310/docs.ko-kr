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
# <a name="connectionm_writelist-field"></a><span data-ttu-id="41582-104">연결. m \_ writelist 필드</span><span class="sxs-lookup"><span data-stu-id="41582-104">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="41582-105">`Connection.m_WriteList`HTTP를 <xref:System.Collections.ArrayList> <xref:System.Net.HttpWebRequest> 통해 전송 되기 위해 큐에 대기 중인 개체의입니다.</span><span class="sxs-lookup"><span data-stu-id="41582-105">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="41582-106">구문</span><span class="sxs-lookup"><span data-stu-id="41582-106">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="41582-107">`Connection.m_WriteList`필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41582-107">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="41582-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41582-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="41582-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41582-109">Requirements</span></span>

<span data-ttu-id="41582-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="41582-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="41582-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="41582-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="41582-112">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41582-112">**.NET Framework versions:** Available since 2.0.</span></span>
