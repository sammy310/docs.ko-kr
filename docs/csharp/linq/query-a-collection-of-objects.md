---
title: 개체의 컬렉션 쿼리(C#의 LINQ)
description: C#에서 LINQ를 사용하여 컬렉션을 쿼리하는 방법을 알아봅니다.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659815"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="c6ca0-103">개체의 컬렉션 쿼리</span><span class="sxs-lookup"><span data-stu-id="c6ca0-103">Query a collection of objects</span></span>

<span data-ttu-id="c6ca0-104">다음 예제는 `Student` 개체의 목록에 대해 간단한 쿼리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="c6ca0-105">각 `Student` 개체에는 학생에 대한 몇 가지 기본 정보와 네 개 시험에서 학생의 점수를 나타내는 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="c6ca0-106">이 애플리케이션은 이 섹션에서 동일한 `students` 데이터 소스를 사용하는 많은 다른 예제의 프레임워크 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ca0-107">예제</span><span class="sxs-lookup"><span data-stu-id="c6ca0-107">Example</span></span>

<span data-ttu-id="c6ca0-108">다음 쿼리는 첫 번째 시험에서 90점 이상의 점수를 받은 학생을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="c6ca0-109">이 쿼리는 사용자가 실험할 수 있도록 의도적으로 간단하게 만든 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="c6ca0-110">예를 들어, `where` 절에서 더 많은 조건을 시도하거나 `orderby` 절을 사용하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6ca0-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ca0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6ca0-111">See also</span></span>

- [<span data-ttu-id="c6ca0-112">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c6ca0-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="c6ca0-113">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="c6ca0-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
