---
title: 연결 쿼리 예제(C#)
description: 이 예제에서는 C#에서 지연된 실행과 지연 계산을 모두 사용하는 두 쿼리를 연결할 때 발생하는 상황을 보여 줍니다.
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 0cfcfe1c8f537778fd1ef909277d95d83991af51
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105544"
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="9dbc5-103">연결 쿼리 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="9dbc5-103">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="9dbc5-104">이 예제에서는 이전 예제를 기반으로 하며 지연된 실행과 지연 계산을 모두 사용하는 두 쿼리를 연결할 때 발생하는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-104">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dbc5-105">예제</span><span class="sxs-lookup"><span data-stu-id="9dbc5-105">Example</span></span>  
 <span data-ttu-id="9dbc5-106">이 예제에는 지정된 문자열을 소스 컬렉션의 모든 문자열에 추가한 다음 새 문자열을 생성하는 `AppendString` 확장 메서드가 추가로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-106">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
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
  
 <span data-ttu-id="9dbc5-107">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-107">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="9dbc5-108">이 예제에서 각 확장 메서드가 소스 컬렉션의 항목마다 한 번씩 작동하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-108">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="9dbc5-109">이 예제에서 알아 두어야 할 점은 컬렉션을 생성하는 쿼리를 연결했지만 중간 컬렉션이 구체화되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-109">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="9dbc5-110">대신 각 항목이 한 지연 메서드에서 다음 지연 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-110">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="9dbc5-111">이렇게 하면 먼저 문자열 배열을 하나 가져온 다음 대문자로 변환된 두 번째 문자열 배열을 만들고 마지막으로 각 문자열 끝에 느낌표가 추가된 세 번째 문자열 배열을 만드는 방법보다 훨씬 적은 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-111">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="9dbc5-112">이 자습서의 다음 항목에서는 중간 구체화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9dbc5-112">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
- [<span data-ttu-id="9dbc5-113">중간 구체화(C#)</span><span class="sxs-lookup"><span data-stu-id="9dbc5-113">Intermediate Materialization (C#)</span></span>](./intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="9dbc5-114">참조</span><span class="sxs-lookup"><span data-stu-id="9dbc5-114">See also</span></span>

- [<span data-ttu-id="9dbc5-115">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="9dbc5-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
