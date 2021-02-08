---
description: '자세한 정보: SqlStreamChars. SetLength (Int64) 메서드'
title: SqlStreamChars. SetLength (Int64) 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d10ce55126ae09062fe895c3a686ce5d94174554
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804142"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="bf035-103">SqlStreamChars. SetLength (Int64) 메서드</span><span class="sxs-lookup"><span data-stu-id="bf035-103">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="bf035-104">파생 클래스에서 재정의 되는 경우 스트림에 사용 되는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-104">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="bf035-105">이 메서드를 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="bf035-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="bf035-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="bf035-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf035-108">Parameters</span></span>

`value`\
<span data-ttu-id="bf035-109">원하는 현재 스트림의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-109">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf035-110">설명</span><span class="sxs-lookup"><span data-stu-id="bf035-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bf035-111">`SqlStreamChars.SetLength`메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-111">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bf035-112">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf035-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf035-113">Requirements</span></span>

<span data-ttu-id="bf035-114">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="bf035-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="bf035-115">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="bf035-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="bf035-116">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf035-116">**.NET Framework versions:** Available since 2.0.</span></span>
