---
title: ServicePoint. m_ConnectionGroupList 필드
description: ServicePoint. m_ConnectionGroupList 필드를 이해 합니다 .이 필드에는 각각 .NET의 ServicePoint URI에 대 한 연결을 보유 하는 연결 그룹의 해시 테이블이 있습니다.
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
ms.openlocfilehash: 0ebfeb782147f21abfde536b8053fa15b1e1a602
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989709"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="6ce85-103">ServicePoint. m \_ ConnectionGroupList 필드</span><span class="sxs-lookup"><span data-stu-id="6ce85-103">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="6ce85-104">`ServicePoint.m_ConnectionGroupList`는 <xref:System.Collections.Hashtable> 의 URI에 대 한 연결을 보유 하는 연결 그룹의입니다 <xref:System.Net.ServicePoint> .</span><span class="sxs-lookup"><span data-stu-id="6ce85-104">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ce85-105">구문</span><span class="sxs-lookup"><span data-stu-id="6ce85-105">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="6ce85-106">`ServicePoint.m_ConnectionGroupList`필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce85-106">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6ce85-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce85-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ce85-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ce85-108">Requirements</span></span>

<span data-ttu-id="6ce85-109">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6ce85-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6ce85-110">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="6ce85-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6ce85-111">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce85-111">**.NET Framework versions:** Available since 2.0.</span></span>
