---
description: '자세한 정보: SqlStreamChars. Dispose (Boolean) 메서드'
title: SqlStreamChars. Dispose (Boolean) 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce24cc885d87a3ff0bbcdbea7992ca78ee592454
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802608"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="cc835-103">SqlStreamChars. Dispose (Boolean) 메서드</span><span class="sxs-lookup"><span data-stu-id="cc835-103">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="cc835-104">파생 클래스에서 재정의 되는 경우 스트림에 사용 되는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-104">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="cc835-105">이 메서드를 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="cc835-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="cc835-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="cc835-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc835-108">Parameters</span></span>

`disposing`\
<span data-ttu-id="cc835-109">관리되는 리소스와 관리되지 않는 리소스를 모두 해제하려면 `true`로 설정하고, 관리되지 않는 리소스만 해제하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-109">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc835-110">설명</span><span class="sxs-lookup"><span data-stu-id="cc835-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="cc835-111">`SqlStreamChars.Dispose`메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-111">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cc835-112">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc835-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc835-113">Requirements</span></span>

<span data-ttu-id="cc835-114">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="cc835-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="cc835-115">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="cc835-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="cc835-116">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc835-116">**.NET Framework versions:** Available since 2.0.</span></span>
