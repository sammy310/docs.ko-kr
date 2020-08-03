---
title: 두 목록 간의 차집합을 구하는 방법(LINQ)(C#)
description: C#의 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 하나의 목록에 있지만 다른 목록에는 없는 줄만 출력하는 방법을 보여줍니다.
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 24509488d91f9861ee9bf84277238bea7031e5f6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105080"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a>두 목록 간의 차집합을 구하는 방법(LINQ)(C#)
이 예제에서는 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 names1.txt에 있지만 names2.txt에는 없는 줄만 출력하는 방법을 보여 줍니다.  
  
### <a name="to-create-the-data-files"></a>데이터 파일을 만들려면  
  
1. [문자열 컬렉션을 결합 및 비교 방법(LINQ)(C#)](./how-to-combine-and-compare-string-collections-linq.md)에 표시된 대로 names1.txt 및 names2.txt를 솔루션 폴더에 복사합니다.  
  
## <a name="example"></a>예제  
  
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
  
 <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, <xref:System.Linq.Enumerable.Concat%2A> 등 C#에서 일부 유형의 쿼리 작업은 메서드 기반 구문으로만 표현할 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.  
  
## <a name="see-also"></a>참조

- [LINQ 및 문자열(C#)](./linq-and-strings.md)
