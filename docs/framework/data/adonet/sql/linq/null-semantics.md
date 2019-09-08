---
title: Null 의미 체계
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: d0b18c0a699840d11f5e4add05147672f9bb69e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792973"
---
# <a name="null-semantics"></a><span data-ttu-id="e1ea8-102">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="e1ea8-102">Null Semantics</span></span>
<span data-ttu-id="e1ea8-103">다음 표에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `null` (`Nothing` Visual Basic) 문제에 대해 설명 하는 설명서의 여러 부분에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ea8-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="e1ea8-104">항목</span><span class="sxs-lookup"><span data-stu-id="e1ea8-104">Topic</span></span>|<span data-ttu-id="e1ea8-105">설명</span><span class="sxs-lookup"><span data-stu-id="e1ea8-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e1ea8-106">SQL-CLR 형식 불일치</span><span class="sxs-lookup"><span data-stu-id="e1ea8-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="e1ea8-107">이 항목의 "Null 의미 체계" 섹션에는 세 가지 상태 SQL 부울 및 두 가지 상태 CLR (공용 <xref:System.Boolean>언어 런타임), 리터럴 `Nothing` (Visual Basic) 및 `null` (C#)에 대 한 설명 및 기타 유사한 내용이 포함 되어 있습니다. 문제도.</span><span class="sxs-lookup"><span data-stu-id="e1ea8-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="e1ea8-108">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="e1ea8-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="e1ea8-109">이 항목의 "Null 의미 체계" 단원에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 null을 의미론적으로 비교 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ea8-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="e1ea8-110">System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="e1ea8-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="e1ea8-111">이 항목의 ".NET과의 차이점" 단원에서는 문자열이 null인 것을 의미할 수도 있고 찾은 위치가 0인 것을 의미할 수도 있는 <xref:System.String.LastIndexOf%2A> 의 반환 값 0에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ea8-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="e1ea8-112">숫자 시퀀스에서 값의 합계 계산</span><span class="sxs-lookup"><span data-stu-id="e1ea8-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="e1ea8-113">연산자가 <xref:System.Linq.Enumerable.Sum%2A> null만 있는 시퀀스 또는`Nothing` 빈 시퀀스에 대해 0이 아닌 (Visual Basic)로 `null` 계산 되는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1ea8-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1ea8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1ea8-114">See also</span></span>

- [<span data-ttu-id="e1ea8-115">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="e1ea8-115">Data Types and Functions</span></span>](data-types-and-functions.md)
