---
title: 문자열의 문자를 쿼리하는 방법(LINQ)(C#)
description: LINQ에서 문자열을 문자 시퀀스로 쿼리할 수 있습니다. 이 C# 예제에서는 문자열을 쿼리하여 문자열에 포함된 숫자 자릿수를 확인합니다.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 3512be7c30843fcd8e881eab59761706a84a3ac8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104546"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="0258f-104">문자열의 문자를 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="0258f-104">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="0258f-105"><xref:System.String> 클래스는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하기 때문에 모든 문자열을 문자 시퀀스로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="0258f-106">그러나 LINQ는 일반적으로 이 용도로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="0258f-107">복잡한 패턴 일치 작업의 경우 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0258f-108">예제</span><span class="sxs-lookup"><span data-stu-id="0258f-108">Example</span></span>  
 <span data-ttu-id="0258f-109">다음 예제에서는 문자열을 쿼리하여 문자열에 포함된 숫자 자릿수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="0258f-110">쿼리가 처음 실행된 후 "다시 사용"됩니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="0258f-111">이 작업은 쿼리 자체가 실제 결과를 저장하지 않기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-111">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0258f-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0258f-112">Compiling the Code</span></span>  
 <span data-ttu-id="0258f-113">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0258f-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0258f-114">참조</span><span class="sxs-lookup"><span data-stu-id="0258f-114">See also</span></span>

- [<span data-ttu-id="0258f-115">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="0258f-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="0258f-116">LINQ 쿼리와 정규식 결합 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="0258f-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
