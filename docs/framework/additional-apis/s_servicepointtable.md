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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214915"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="e6aa1-102">ServicePointManager\_Servicepointmanager 필드</span><span class="sxs-lookup"><span data-stu-id="e6aa1-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="e6aa1-103">`ServicePointManager.s_ServicePointTable`는 <xref:System.AppDomain>의 활성 HTTP 연결 (<xref:System.Net.ServicePoint>s) 목록이 포함 된 <xref:System.Collections.Hashtable>입니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa1-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6aa1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6aa1-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="e6aa1-105">`ServicePointManager.s_ServicePointTable` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa1-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="e6aa1-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa1-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6aa1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6aa1-107">Requirements</span></span>

<span data-ttu-id="e6aa1-108">**네임 스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e6aa1-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e6aa1-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="e6aa1-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e6aa1-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa1-110">**.NET Framework versions:** Available since 2.0.</span></span>
