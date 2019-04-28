---
title: SqlStreamChars.CanSeek 속성 (System.Data.SqlTypes)
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
ms.openlocfilehash: 52f88a3551e20c74d7a1144c3cd6859a023980db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675184"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="04445-102">SqlStreamChars.CanSeek 속성</span><span class="sxs-lookup"><span data-stu-id="04445-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="04445-103">파생된 클래스에서 재정의 되 면 현재 스트림이 검색 작업을 지원 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04445-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="04445-104">이 속성을 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="04445-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="04445-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04445-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="04445-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04445-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="04445-107">속성 값</span><span class="sxs-lookup"><span data-stu-id="04445-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="04445-108">`true` 현재 스트림이 seek 작업을 지 원하는 경우 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="04445-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="04445-109">설명</span><span class="sxs-lookup"><span data-stu-id="04445-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="04445-110">`SqlStreamChars.CanSeek` 속성은 전용 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04445-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="04445-111">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04445-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="04445-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04445-112">Requirements</span></span>

<span data-ttu-id="04445-113">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="04445-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="04445-114">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="04445-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="04445-115">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04445-115">**.NET Framework versions:** Available since 2.0.</span></span>