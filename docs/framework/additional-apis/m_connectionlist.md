---
title: ConnectionGroup. m_ConnectionList 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a06e535c554f765161d619d97f2e70072fbd0d5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120013"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="a1697-102">ConnectionGroup m\_Connectiongroup 필드</span><span class="sxs-lookup"><span data-stu-id="a1697-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="a1697-103">`ConnectionGroup.m_ConnectionList`는 동일한 URI를 사용 하 고 만료 및 인증과 같은 일부 다른 속성에 대해 동일한 값을 공유 하는 연결 개체의 <xref:System.Collections.ArrayList>입니다.</span><span class="sxs-lookup"><span data-stu-id="a1697-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1697-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1697-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="a1697-105">`ConnectionGroup.m_ConnectionList` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1697-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a1697-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1697-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1697-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1697-107">Requirements</span></span>

<span data-ttu-id="a1697-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a1697-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a1697-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="a1697-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a1697-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1697-110">**.NET Framework versions:** Available since 2.0.</span></span>
