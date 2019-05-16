---
title: SmiOrderProperty.Item 속성 (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2d8788f610d80c30baf51bff0131f0834d59fcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634579"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="1a119-102">SmiOrderProperty.Item 속성</span><span class="sxs-lookup"><span data-stu-id="1a119-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="1a119-103">엔터티에 대 한 열 순서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-103">Gets the column order for the entity.</span></span> <span data-ttu-id="1a119-104">이 속성을 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="1a119-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="1a119-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a119-107">구문</span><span class="sxs-lookup"><span data-stu-id="1a119-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="1a119-108">속성 값</span><span class="sxs-lookup"><span data-stu-id="1a119-108">Property value</span></span>

<span data-ttu-id="1a119-109">열 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a119-110">설명</span><span class="sxs-lookup"><span data-stu-id="1a119-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="1a119-111">`SmiOrderProperty.Item` 속성은 내부용 이며 사용자 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1a119-112">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 속성의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a119-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a119-113">Requirements</span></span>

<span data-ttu-id="1a119-114">**네임스페이스:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="1a119-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="1a119-115">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="1a119-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="1a119-116">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a119-116">**.NET Framework versions:** Available since 2.0.</span></span>
