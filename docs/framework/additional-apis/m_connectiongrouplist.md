---
title: ServicePoint. m_ConnectionGroupList 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
ms.openlocfilehash: f2759f82f335415edf7bab33edbd446eec6ffbb5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215514"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="5c3e6-102">ServicePoint. m\_ConnectionGroupList 필드</span><span class="sxs-lookup"><span data-stu-id="5c3e6-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="5c3e6-103">`ServicePoint.m_ConnectionGroupList`는 각각 <xref:System.Net.ServicePoint>의 URI에 대 한 연결을 보유 하는 연결 그룹의 <xref:System.Collections.Hashtable>입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3e6-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c3e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c3e6-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="5c3e6-105">`ServicePoint.m_ConnectionGroupList` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c3e6-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="5c3e6-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c3e6-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c3e6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c3e6-107">Requirements</span></span>

<span data-ttu-id="5c3e6-108">**네임 스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5c3e6-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5c3e6-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="5c3e6-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5c3e6-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c3e6-110">**.NET Framework versions:** Available since 2.0.</span></span>
