---
description: '자세한 정보: SqlStreamChars. Read (Char [], Int32, Int32) 메서드'
title: SqlStreamChars. Read (Char [], Int32, Int32) 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: a899ddff7b7242fcc32aaf7b7f7794970596027b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802582"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="84b53-103">SqlStreamChars. Read (Char [], Int32, Int32) 메서드</span><span class="sxs-lookup"><span data-stu-id="84b53-103">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="84b53-104">파생 클래스에서 재정의 되는 경우 입력 스트림에서 다음 문자 집합을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-104">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="84b53-105">이 메서드를 포함 하는 어셈블리에 SQLAccess.dll와의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="84b53-106">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="84b53-107">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="84b53-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84b53-108">Parameters</span></span>

`buffer`\
<span data-ttu-id="84b53-109">읽을 char 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-109">A char array to read.</span></span>

`offset`\
<span data-ttu-id="84b53-110">원점을 기준으로 하는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-110">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="84b53-111">현재 스트림에서 읽을 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-111">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="84b53-112">반환</span><span class="sxs-lookup"><span data-stu-id="84b53-112">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="84b53-113">버퍼로 읽어온 총 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-113">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="84b53-114">설명</span><span class="sxs-lookup"><span data-stu-id="84b53-114">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="84b53-115">`SqlStreamChars.Read`메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-115">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="84b53-116">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-116">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="84b53-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84b53-117">Requirements</span></span>

<span data-ttu-id="84b53-118">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="84b53-118">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="84b53-119">**어셈블리:** System.Data(System.Data.dll에서)</span><span class="sxs-lookup"><span data-stu-id="84b53-119">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="84b53-120">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b53-120">**.NET Framework versions:** Available since 2.0.</span></span>
