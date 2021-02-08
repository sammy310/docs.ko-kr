---
description: '자세한 정보: SqlChars 속성'
title: SqlChars. Stream 속성 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9af0df98b268a749d890ab1b40dddbbe98ced8d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802647"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="afac8-103">SqlChars.Stream 속성</span><span class="sxs-lookup"><span data-stu-id="afac8-103">SqlChars.Stream Property</span></span>

<span data-ttu-id="afac8-104">문자 스트림을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-104">Gets or sets the character stream.</span></span> <span data-ttu-id="afac8-105">이 속성을 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="afac8-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="afac8-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="afac8-108">속성 값</span><span class="sxs-lookup"><span data-stu-id="afac8-108">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="afac8-109">문자 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-109">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="afac8-110">설명</span><span class="sxs-lookup"><span data-stu-id="afac8-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="afac8-111">`SqlChars.Stream`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-111">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="afac8-112">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="afac8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afac8-113">Requirements</span></span>

<span data-ttu-id="afac8-114">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="afac8-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="afac8-115">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="afac8-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="afac8-116">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afac8-116">**.NET Framework versions:** Available since 2.0.</span></span>
