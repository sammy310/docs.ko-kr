---
title: SqlStreamChars.Dispose(Boolean) 메서드 (System.Data.SqlTypes)
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
ms.openlocfilehash: 2cad6015c1c4d72300d8413b7accead12f79a0be
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634309"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="7f6d8-102">SqlStreamChars.Dispose(Boolean) 메서드</span><span class="sxs-lookup"><span data-stu-id="7f6d8-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="7f6d8-103">파생된 클래스에서 재정의 되 면 스트림을 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="7f6d8-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="7f6d8-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="7f6d8-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="7f6d8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f6d8-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="7f6d8-108">관리되는 리소스와 관리되지 않는 리소스를 모두 해제하려면 `true`로 설정하고, 관리되지 않는 리소스만 해제하려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f6d8-109">설명</span><span class="sxs-lookup"><span data-stu-id="7f6d8-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="7f6d8-110">`SqlStreamChars.Dispose` 메서드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7f6d8-111">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f6d8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f6d8-112">Requirements</span></span>

<span data-ttu-id="7f6d8-113">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="7f6d8-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="7f6d8-114">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="7f6d8-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="7f6d8-115">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f6d8-115">**.NET Framework versions:** Available since 2.0.</span></span>
