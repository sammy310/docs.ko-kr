---
title: ServicePointManager. s_ServicePointTable 필드
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119997"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="197c9-102">ServicePointManager\_Servicepointmanager 필드</span><span class="sxs-lookup"><span data-stu-id="197c9-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="197c9-103">`ServicePointManager.s_ServicePointTable`는 <xref:System.AppDomain>의 활성 HTTP 연결 (<xref:System.Net.ServicePoint>s) 목록이 포함 된 <xref:System.Collections.Hashtable>입니다.</span><span class="sxs-lookup"><span data-stu-id="197c9-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="197c9-104">구문</span><span class="sxs-lookup"><span data-stu-id="197c9-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="197c9-105">`ServicePointManager.s_ServicePointTable` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="197c9-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="197c9-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="197c9-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="197c9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="197c9-107">Requirements</span></span>

<span data-ttu-id="197c9-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="197c9-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="197c9-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="197c9-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="197c9-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197c9-110">**.NET Framework versions:** Available since 2.0.</span></span>
