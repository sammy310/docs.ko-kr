---
description: '자세한 정보: SqlStreamChars. Flush 메서드'
title: SqlStreamChars. Flush 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8f519ffb8248a17608319eb0fbfe598f9ee3487a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684466"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="4799f-103">SqlStreamChars. Flush 메서드</span><span class="sxs-lookup"><span data-stu-id="4799f-103">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="4799f-104">파생 클래스에서 재정의되면 이 스트림에 대해 모든 버퍼를 지우고 버퍼링된 데이터가 내부 디바이스에 쓰여지도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-104">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="4799f-105">이 메서드를 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="4799f-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="4799f-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="4799f-108">구문</span><span class="sxs-lookup"><span data-stu-id="4799f-108">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="4799f-109">설명</span><span class="sxs-lookup"><span data-stu-id="4799f-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4799f-110">`SqlStreamChars.Flush`메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-110">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4799f-111">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4799f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4799f-112">Requirements</span></span>

<span data-ttu-id="4799f-113">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="4799f-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="4799f-114">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="4799f-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="4799f-115">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4799f-115">**.NET Framework versions:** Available since 2.0.</span></span>
