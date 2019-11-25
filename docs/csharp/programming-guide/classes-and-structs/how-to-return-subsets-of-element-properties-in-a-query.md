---
title: 쿼리에서 요소 속성의 하위 집합을 반환하는 방법 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 1266b866d671854c787d907b91f654c128681de9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970452"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="29a24-102">쿼리에서 요소 속성의 하위 집합을 반환하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="29a24-102">How to return subsets of element properties in a query (C# Programming Guide)</span></span>
<span data-ttu-id="29a24-103">이러한 조건이 둘 다 적용되는 경우 쿼리 식에서 무명 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="29a24-104">각 소스 요소의 속성 중 일부만 반환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-104">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="29a24-105">쿼리가 실행되는 메서드의 범위 외부에 쿼리 결과를 저장할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="29a24-106">각 소스 요소에서 하나의 속성 또는 필드만 반환하려는 경우 `select` 절에 점 연산자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="29a24-107">예를 들어 각 `student`의 `ID`만 반환하려면 `select` 절을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="29a24-108">예</span><span class="sxs-lookup"><span data-stu-id="29a24-108">Example</span></span>  
 <span data-ttu-id="29a24-109">다음 예제에서는 무명 형식을 사용하여 지정된 조건과 일치하는 각 소스 요소의 속성 하위 집합만 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="29a24-110">이름이 지정되지 않은 경우 무명 형식은 소스 요소의 이름을 해당 속성에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="29a24-111">무명 형식의 속성에 새 이름을 지정하려면 `select` 문을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="29a24-112">앞의 예제에서 이 작업을 수행하는 경우 `Console.WriteLine` 문도 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29a24-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="29a24-113">Compiling the Code</span></span>  
  
<span data-ttu-id="29a24-114">이 코드를 실행하려면 System.Linq에 대한 `using` 지시문을 통해 클래스를 복사하여 C# 콘솔 애플리케이션 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="29a24-114">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29a24-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29a24-115">See also</span></span>

- [<span data-ttu-id="29a24-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="29a24-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="29a24-117">익명 형식</span><span class="sxs-lookup"><span data-stu-id="29a24-117">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="29a24-118">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="29a24-118">LINQ in C#</span></span>](../../linq/index.md)
