---
title: 두 목록 간의 차집합을 구하는 방법(LINQ)(C#)
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 227405428a1b418cbe6ceb3d0e3274595307e5ef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345932"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="1838a-102">두 목록 간의 차집합을 구하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="1838a-102">How to find the set difference between two lists (LINQ) (C#)</span></span>
<span data-ttu-id="1838a-103">이 예제에서는 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 names1.txt에 있지만 names2.txt에는 없는 줄만 출력하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1838a-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="1838a-104">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="1838a-104">To create the data files</span></span>  
  
1. <span data-ttu-id="1838a-105">[문자열 컬렉션을 결합 및 비교 방법(LINQ)(C#)](./how-to-combine-and-compare-string-collections-linq.md)에 표시된 대로 names1.txt 및 names2.txt를 솔루션 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1838a-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to combine and compare string collections (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1838a-106">예제</span><span class="sxs-lookup"><span data-stu-id="1838a-106">Example</span></span>  
  
```csharp  
class CompareLists  
{          
    static void Main()  
    {  
        // Create the IEnumerable data sources.  
        string[] names1 = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] names2 = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Create the query. Note that method syntax must be used here.  
        IEnumerable<string> differenceQuery =  
          names1.Except(names2);  
  
        // Execute the query.  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt");  
        foreach (string s in differenceQuery)  
            Console.WriteLine(s);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
     The following lines are in names1.txt but not names2.txt  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
     */  
```  
  
 <span data-ttu-id="1838a-107"><xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, <xref:System.Linq.Enumerable.Concat%2A> 등 C#에서 일부 유형의 쿼리 작업은 메서드 기반 구문으로만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1838a-107">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1838a-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1838a-108">Compiling the Code</span></span>  
 <span data-ttu-id="1838a-109">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1838a-109">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1838a-110">참조</span><span class="sxs-lookup"><span data-stu-id="1838a-110">See also</span></span>

- [<span data-ttu-id="1838a-111">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="1838a-111">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
