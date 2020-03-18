---
title: 쿼리 키워드 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 01134eda540c5141afbd11b2c89ff779da495a9a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173525"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="6078f-102">쿼리 키워드(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6078f-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="6078f-103">이 섹션에는 쿼리 식에 사용되는 상황별 키워드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6078f-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6078f-104">In this section</span></span>

|<span data-ttu-id="6078f-105">절</span><span class="sxs-lookup"><span data-stu-id="6078f-105">Clause</span></span>|<span data-ttu-id="6078f-106">설명</span><span class="sxs-lookup"><span data-stu-id="6078f-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="6078f-107">from</span><span class="sxs-lookup"><span data-stu-id="6078f-107">from</span></span>](from-clause.md)|<span data-ttu-id="6078f-108">데이터 소스와 범위 변수(반복 변수와 유사함)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="6078f-109">where</span><span class="sxs-lookup"><span data-stu-id="6078f-109">where</span></span>](where-clause.md)|<span data-ttu-id="6078f-110">논리적 AND 및 OR 연산자(`&&` 또는 <code>&#124;&#124;</code>)로 구분된 하나 이상의 부울 식을 기준으로 소스 요소를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="6078f-111">select</span><span class="sxs-lookup"><span data-stu-id="6078f-111">select</span></span>](select-clause.md)|<span data-ttu-id="6078f-112">쿼리를 실행할 때 반환된 시퀀스의 요소에 사용할 형식 및 모양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="6078f-113">group</span><span class="sxs-lookup"><span data-stu-id="6078f-113">group</span></span>](group-clause.md)|<span data-ttu-id="6078f-114">지정된 키 값에 따라 쿼리 결과를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="6078f-115">into</span><span class="sxs-lookup"><span data-stu-id="6078f-115">into</span></span>](into.md)|<span data-ttu-id="6078f-116">join, group 또는 select 절의 결과에 대한 참조로 사용할 수 있는 식별자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="6078f-117">orderby</span><span class="sxs-lookup"><span data-stu-id="6078f-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="6078f-118">요소 형식에 대한 기본 비교자에 따라 오름차순 또는 내림차순으로 쿼리 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="6078f-119">join</span><span class="sxs-lookup"><span data-stu-id="6078f-119">join</span></span>](join-clause.md)|<span data-ttu-id="6078f-120">지정한 두 일치 조건 간의 같음 비교를 기반으로 하여 두 데이터 소스를 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="6078f-121">let</span><span class="sxs-lookup"><span data-stu-id="6078f-121">let</span></span>](let-clause.md)|<span data-ttu-id="6078f-122">쿼리 식에 하위 식 결과를 저장할 범위 변수를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="6078f-123">in</span><span class="sxs-lookup"><span data-stu-id="6078f-123">in</span></span>](in.md)|<span data-ttu-id="6078f-124">[join](join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6078f-125">on</span><span class="sxs-lookup"><span data-stu-id="6078f-125">on</span></span>](on.md)|<span data-ttu-id="6078f-126">[join](join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6078f-127">equals</span><span class="sxs-lookup"><span data-stu-id="6078f-127">equals</span></span>](equals.md)|<span data-ttu-id="6078f-128">[join](join-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6078f-129">by</span><span class="sxs-lookup"><span data-stu-id="6078f-129">by</span></span>](by.md)|<span data-ttu-id="6078f-130">[group](group-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="6078f-131">ascending</span><span class="sxs-lookup"><span data-stu-id="6078f-131">ascending</span></span>](ascending.md)|<span data-ttu-id="6078f-132">[orderby](orderby-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="6078f-133">descending</span><span class="sxs-lookup"><span data-stu-id="6078f-133">descending</span></span>](descending.md)|<span data-ttu-id="6078f-134">[orderby](orderby-clause.md) 절의 상황별 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6078f-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6078f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6078f-135">See also</span></span>

- [<span data-ttu-id="6078f-136">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="6078f-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6078f-137">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="6078f-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6078f-138">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="6078f-138">LINQ in C#</span></span>](../../linq/index.md)
