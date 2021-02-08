---
description: '자세한 정보: SqlStreamChars. .Canseek 속성'
title: SqlStreamChars. .Canseek 속성 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5919a66bef9ac31e0ef15ad4af64b456700605f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802621"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="d8795-103">SqlStreamChars. .Canseek 속성</span><span class="sxs-lookup"><span data-stu-id="d8795-103">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="d8795-104">파생 클래스에서 재정의 되는 경우 현재 스트림에서 seek 작업을 지원 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-104">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="d8795-105">이 속성을 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d8795-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d8795-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="d8795-108">속성 값</span><span class="sxs-lookup"><span data-stu-id="d8795-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="d8795-109">`true` 현재 스트림 검색 작업을 지원 하면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-109">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8795-110">설명</span><span class="sxs-lookup"><span data-stu-id="d8795-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d8795-111">`SqlStreamChars.CanSeek`속성은 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-111">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d8795-112">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8795-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8795-113">Requirements</span></span>

<span data-ttu-id="d8795-114">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d8795-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d8795-115">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="d8795-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d8795-116">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8795-116">**.NET Framework versions:** Available since 2.0.</span></span>
