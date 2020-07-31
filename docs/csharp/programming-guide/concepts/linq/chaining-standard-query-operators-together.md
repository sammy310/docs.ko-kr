---
title: 여러 표준 쿼리 연산자 연결(C#)
description: 이 예제에서는 표준 쿼리 연산자를 C#에서 함께 연결하는 방법을 보여줍니다. 쿼리가 중간 결과를 구체화하지 않습니다.
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 41a7e4c7910c783d07181fe16254b0cac6902794
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104068"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="b20b1-104">여러 표준 쿼리 연산자 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="b20b1-104">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="b20b1-105">이는 [자습서: 여러 쿼리 연결(C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) 자습서의 마지막 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-105">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) tutorial.</span></span>  
  
 <span data-ttu-id="b20b1-106">표준 쿼리 연산자도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-106">The standard query operators can also be chained together.</span></span> <span data-ttu-id="b20b1-107">예를 들어, <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 연산자를 삽입할 수 있으며 이 연산자는 지연 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-107">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="b20b1-108">이 연산자는 중간 결과를 유형화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-108">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20b1-109">예제</span><span class="sxs-lookup"><span data-stu-id="b20b1-109">Example</span></span>  
 <span data-ttu-id="b20b1-110">이 예제에서 <xref:System.Linq.Enumerable.Where%2A> 메서드는 `ConvertCollectionToUpperCase`를 호출하기 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-110">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="b20b1-111"><xref:System.Linq.Enumerable.Where%2A> 메서드는 이 자습서의 이전 예제에서 사용되는 지연 메서드인 `ConvertCollectionToUpperCase` 및 `AppendString`과 거의 똑같은 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-111">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="b20b1-112">한 가지 차이점은 이 경우에 <xref:System.Linq.Enumerable.Where%2A> 메서드는 소스 컬렉션을 반복하고 첫 번째 항목이 조건자를 통과하지 않는 것을 확인한 다음 조건자를 통과하는 다음 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-112">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="b20b1-113">그런 다음 두 번째 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-113">It then yields the second item.</span></span>  
  
 <span data-ttu-id="b20b1-114">그러나 기본 개념은 동일합니다. 중간 컬렉션은 필요하지 않는 한 구체화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-114">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="b20b1-115">쿼리 식이 사용되는 경우 쿼리 식은 표준 쿼리 연산자에 대한 호출로 변환되고 동일한 원칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-115">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="b20b1-116">Office Open XML 문서를 쿼리하는 이 단원의 모든 예제에서는 동일한 원칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-116">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="b20b1-117">지연된 실행과 지연 계산은 LINQ와 LINQ to XML을 효과적으로 사용하기 위해 이해해야 하는 기본 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-117">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            where s.CompareTo("D") >= 0  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b20b1-118">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b20b1-118">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
