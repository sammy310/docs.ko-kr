---
title: ConnectionGroup. m_ConnectionList 필드
description: 동일한 URI를 제공 하 고 다른 속성의 값을 공유 하는 연결 개체를 포함 하는 .NET의 ConnectionGroup. m_ConnectionList 필드에 대해 알아봅니다.
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
ms.openlocfilehash: 478b2441c062e8df6f4e718bd66d7af329f20f12
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989726"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="035e7-103">ConnectionGroup. m \_ connectiongroup 필드</span><span class="sxs-lookup"><span data-stu-id="035e7-103">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="035e7-104">`ConnectionGroup.m_ConnectionList`는 <xref:System.Collections.ArrayList> 동일한 URI를 사용 하 고 만료 및 인증과 같은 다른 속성에 대해 동일한 값을 공유 하는 연결 개체의입니다.</span><span class="sxs-lookup"><span data-stu-id="035e7-104">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="035e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="035e7-105">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="035e7-106">`ConnectionGroup.m_ConnectionList`필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="035e7-106">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="035e7-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="035e7-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="035e7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="035e7-108">Requirements</span></span>

<span data-ttu-id="035e7-109">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="035e7-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="035e7-110">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="035e7-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="035e7-111">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="035e7-111">**.NET Framework versions:** Available since 2.0.</span></span>
