---
title: Null 의미 체계
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147543"
---
# <a name="null-semantics"></a><span data-ttu-id="982f4-102">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="982f4-102">Null Semantics</span></span>

<span data-ttu-id="982f4-103">다음 표에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `null` ( `Nothing` Visual Basic) 문제에 대해 설명 하는 설명서의 여러 부분에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="982f4-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="982f4-104">항목</span><span class="sxs-lookup"><span data-stu-id="982f4-104">Topic</span></span>|<span data-ttu-id="982f4-105">설명</span><span class="sxs-lookup"><span data-stu-id="982f4-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="982f4-106">SQL-CLR 형식 불일치</span><span class="sxs-lookup"><span data-stu-id="982f4-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="982f4-107">이 항목의 "Null 의미 체계" 섹션에는 세 가지 상태 SQL 부울 및 두 가지 상태 CLR (공용 언어 런타임) <xref:System.Boolean> , 리터럴 `Nothing` (Visual Basic), `null` (c #) 및 기타 유사한 문제에 대 한 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="982f4-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="982f4-108">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="982f4-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="982f4-109">이 항목의 "Null 의미 체계" 단원에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 null을 의미론적으로 비교 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="982f4-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="982f4-110">System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="982f4-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="982f4-111">이 항목의 ".NET과의 차이점" 단원에서는 문자열이 null인 것을 의미할 수도 있고 찾은 위치가 0인 것을 의미할 수도 있는 <xref:System.String.LastIndexOf%2A> 의 반환 값 0에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="982f4-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="982f4-112">숫자 시퀀스에서 값의 합계 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="982f4-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="982f4-113"><xref:System.Linq.Enumerable.Sum%2A>연산자가 `null` `Nothing` null만 있는 시퀀스 또는 빈 시퀀스에 대해 0이 아닌 (Visual Basic)로 계산 되는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="982f4-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="982f4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="982f4-114">See also</span></span>

- [<span data-ttu-id="982f4-115">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="982f4-115">Data Types and Functions</span></span>](data-types-and-functions.md)
