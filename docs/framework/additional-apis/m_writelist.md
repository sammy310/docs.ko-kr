---
title: Connection.m_WriteList 필드
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: a7446b9cbbfd4d3a4d38368a8e24c99527cf9108
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705937"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="cc851-102">Connection.m\_WriteList 필드</span><span class="sxs-lookup"><span data-stu-id="cc851-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="cc851-103">`Connection.m_WriteList` <xref:System.Collections.ArrayList> 의 <xref:System.Net.HttpWebRequest> HTTP를 통해 보내도록 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cc851-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc851-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc851-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="cc851-105">`Connection.m_WriteList` 필드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc851-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="cc851-106">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc851-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc851-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc851-107">Requirements</span></span>

<span data-ttu-id="cc851-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="cc851-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="cc851-109">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="cc851-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="cc851-110">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc851-110">**.NET Framework versions:** Available since 2.0.</span></span>
