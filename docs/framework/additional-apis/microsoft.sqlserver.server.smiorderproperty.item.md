---
description: '자세히 알아보기: SmiOrderProperty 속성'
title: SmiOrderProperty 속성 (Microsoft. SqlServer)
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
ms.openlocfilehash: fc2151d3f36a6746e80e2fd6d611a803b2c3162e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767988"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="4a50c-103">SmiOrderProperty 속성</span><span class="sxs-lookup"><span data-stu-id="4a50c-103">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="4a50c-104">엔터티에 대 한 열 순서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-104">Gets the column order for the entity.</span></span> <span data-ttu-id="4a50c-105">이 속성을 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="4a50c-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="4a50c-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a50c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a50c-108">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="4a50c-109">속성 값</span><span class="sxs-lookup"><span data-stu-id="4a50c-109">Property value</span></span>

<span data-ttu-id="4a50c-110">열 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-110">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a50c-111">설명</span><span class="sxs-lookup"><span data-stu-id="4a50c-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4a50c-112">`SmiOrderProperty.Item`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-112">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4a50c-113">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-113">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a50c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a50c-114">Requirements</span></span>

<span data-ttu-id="4a50c-115">**네임스페이스:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="4a50c-115">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="4a50c-116">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="4a50c-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="4a50c-117">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a50c-117">**.NET Framework versions:** Available since 2.0.</span></span>
