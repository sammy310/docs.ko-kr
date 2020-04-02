---
title: 쿼리 식의 Null 값 처리(C#의 LINQ)
description: C#에서 LINQ 쿼리 식의 Null 값을 처리하는 방법을 알아봅니다.
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: 3da490b72bd518df7be8c14b34655af8c6f84929
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249307"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="aace6-103">쿼리 식의 Null 값 처리</span><span class="sxs-lookup"><span data-stu-id="aace6-103">Handle null values in query expressions</span></span>

<span data-ttu-id="aace6-104">이 예제에서는 소스 컬렉션에서 가능한 null 값을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="aace6-105"><xref:System.Collections.Generic.IEnumerable%601> 등의 개체 컬렉션에는 값이 [null](../language-reference/keywords/null.md)인 요소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="aace6-106">소스 컬렉션이 null이거나 값이 null인 요소를 포함하고 사용 중인 쿼리가 null 값을 처리하지 않는 경우 쿼리를 실행하면 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="aace6-107">예제</span><span class="sxs-lookup"><span data-stu-id="aace6-107">Example</span></span>

<span data-ttu-id="aace6-108">다음 예제와 같이 null 참조 예외를 피하도록 방어적으로 코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

<span data-ttu-id="aace6-109">이전 예제에서 `where` 절은 범주 시퀀스에서 모든 null 요소를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="aace6-110">이 방법은 join 절의 null 확인과 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="aace6-111">`Products.CategoryID`가 `Nullable<int>`의 축약형인 `int?` 형식이므로 이 예제에서는 null이 있는 조건식이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>

## <a name="example"></a><span data-ttu-id="aace6-112">예제</span><span class="sxs-lookup"><span data-stu-id="aace6-112">Example</span></span>

<span data-ttu-id="aace6-113">join 절에서 비교 키 중 하나만 null 허용 값 형식인 경우에는 쿼리 식에서 다른 키를 null 허용 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable value type in the query expression.</span></span> <span data-ttu-id="aace6-114">다음 예제에서는 `EmployeeID`가 `int?` 형식의 값이 포함된 열이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aace6-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="aace6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aace6-115">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="aace6-116">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="aace6-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="aace6-117">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="aace6-117">Nullable value types</span></span>](../language-reference/builtin-types/nullable-value-types.md)
