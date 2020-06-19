---
title: ServicePointManager. s_ServicePointTable 필드
description: .NET의 ServicePointManager. s_ServicePointTable 필드에 대해 읽어 보십시오. 이 해시 테이블 필드에는 AppDomain의 활성 HTTP 연결 (ServicePoints)이 포함 되어 있습니다.
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
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989546"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="43577-104">ServicePointManager. s \_ servicepointmanager 필드</span><span class="sxs-lookup"><span data-stu-id="43577-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="43577-105">`ServicePointManager.s_ServicePointTable`는의 <xref:System.Collections.Hashtable> 활성 HTTP 연결 목록을 포함 하는입니다 <xref:System.Net.ServicePoint> <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="43577-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="43577-106">구문</span><span class="sxs-lookup"><span data-stu-id="43577-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="43577-107">`ServicePointManager.s_ServicePointTable`필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43577-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="43577-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43577-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="43577-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43577-109">Requirements</span></span>

<span data-ttu-id="43577-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="43577-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="43577-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="43577-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="43577-112">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43577-112">**.NET Framework versions:** Available since 2.0.</span></span>
