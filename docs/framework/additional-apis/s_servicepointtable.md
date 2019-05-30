---
title: ServicePointManager.s_ServicePointTable Field
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301385"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="37881-102">ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="37881-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="37881-103">`ServicePointManager.s_ServicePointTable` <xref:System.Collections.Hashtable> 활성 HTTP 연결의 목록을 포함 하는 (<xref:System.Net.ServicePoint>s)에 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="37881-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="37881-104">구문</span><span class="sxs-lookup"><span data-stu-id="37881-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="37881-105">`ServicePointManager.s_ServicePointTable` 필드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37881-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="37881-106">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37881-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="37881-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37881-107">Requirements</span></span>

<span data-ttu-id="37881-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="37881-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="37881-109">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="37881-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="37881-110">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37881-110">**.NET Framework versions:** Available since 2.0.</span></span>
