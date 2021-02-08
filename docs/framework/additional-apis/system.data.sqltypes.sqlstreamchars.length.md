---
description: '자세한 정보: SqlStreamChars. Length 속성'
title: SqlStreamChars. Length 속성 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b0a9686cadc6d4018c7f291f0326b71195fd5cf5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802595"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="75596-103">SqlStreamChars. Length 속성</span><span class="sxs-lookup"><span data-stu-id="75596-103">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="75596-104">파생 클래스에서 재정의 되는 경우 현재 스트림의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75596-104">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="75596-105">이 속성을 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75596-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="75596-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75596-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="75596-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75596-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="75596-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="75596-108">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="75596-109">속성 값</span><span class="sxs-lookup"><span data-stu-id="75596-109">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="75596-110">스트림의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="75596-110">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="75596-111">설명</span><span class="sxs-lookup"><span data-stu-id="75596-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="75596-112">`SqlStreamChars.Length`속성은 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75596-112">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="75596-113">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75596-113">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="75596-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75596-114">Requirements</span></span>

<span data-ttu-id="75596-115">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="75596-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="75596-116">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="75596-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="75596-117">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75596-117">**.NET Framework versions:** Available since 2.0.</span></span>
