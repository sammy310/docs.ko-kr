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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ebcf5c3f13b3bd30a8e091be09ae546eee1eaffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675444"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="1b54a-102">ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="1b54a-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="1b54a-103">`ServicePointManager.s_ServicePointTable` <xref:System.Collections.Hashtable> 활성 HTTP 연결의 목록을 포함 하는 (<xref:System.Net.ServicePoint>s)에 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="1b54a-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b54a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b54a-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="1b54a-105">`ServicePointManager.s_ServicePointTable` 필드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b54a-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="1b54a-106">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b54a-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b54a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b54a-107">Requirements</span></span>

<span data-ttu-id="1b54a-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1b54a-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1b54a-109">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="1b54a-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="1b54a-110">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b54a-110">**.NET Framework versions:** Available since 2.0.</span></span>
