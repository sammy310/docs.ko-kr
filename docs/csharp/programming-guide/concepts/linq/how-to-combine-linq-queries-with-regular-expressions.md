---
title: LINQ 쿼리와 정규식 결합 방법(C#)
description: 이 예제에서는 C#에서 Regex 클래스를 사용하여 텍스트 문자열 일치를 찾는 정규식을 작성합니다.
ms.date: 07/20/2015
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
ms.openlocfilehash: af63d096e3c2f19ed557180d82d606989a016120
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105339"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a><span data-ttu-id="5a96e-103">LINQ 쿼리와 정규식 결합 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="5a96e-103">How to combine LINQ queries with regular expressions (C#)</span></span>
<span data-ttu-id="5a96e-104">이 예제에서는 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 더 복잡한 텍스트 문자열 일치를 찾는 정규식을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-104">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="5a96e-105">LINQ 쿼리를 사용하면 손쉽게 정규식을 통해 검색하려는 파일을 정확히 필터링하고 결과를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-105">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a96e-106">예제</span><span class="sxs-lookup"><span data-stu-id="5a96e-106">Example</span></span>  
  
```csharp  
class QueryWithRegEx  
{  
    public static void Main()  
    {  
        // Modify this path as necessary so that it accesses your version of Visual Studio.  
        string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio 14.0\";  
        // One of the following paths may be more appropriate on your computer.  
        //string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio\2017\";  
  
        // Take a snapshot of the file system.  
        IEnumerable<System.IO.FileInfo> fileList = GetFiles(startFolder);  
  
        // Create the regular expression to find all things "Visual".  
        System.Text.RegularExpressions.Regex searchTerm =  
            new System.Text.RegularExpressions.Regex(@"Visual (Basic|C#|C\+\+|Studio)");  
  
        // Search the contents of each .htm file.  
        // Remove the where clause to find even more matchedValues!  
        // This query produces a list of files where a match  
        // was found, and a list of the matchedValues in that file.  
        // Note: Explicit typing of "Match" in select clause.  
        // This is required because MatchCollection is not a
        // generic IEnumerable collection.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = System.IO.File.ReadAllText(file.FullName)  
            let matches = searchTerm.Matches(fileText)  
            where matches.Count > 0  
            select new  
            {  
                name = file.FullName,  
                matchedValues = from System.Text.RegularExpressions.Match match in matches  
                                select match.Value  
            };  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm.ToString());  
  
        foreach (var v in queryMatchingFiles)  
        {  
            // Trim the path a bit, then write
            // the file name in which a match was found.  
            string s = v.name.Substring(startFolder.Length - 1);  
            Console.WriteLine(s);  
  
            // For this file, write out all the matching strings  
            foreach (var v2 in v.matchedValues)  
            {  
                Console.WriteLine("  " + v2);  
            }  
        }  
  
        // Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // This method assumes that the application has discovery
    // permissions for all folders under the specified path.  
    static IEnumerable<System.IO.FileInfo> GetFiles(string path)  
    {  
        if (!System.IO.Directory.Exists(path))  
            throw new System.IO.DirectoryNotFoundException();  
  
        string[] fileNames = null;  
        List<System.IO.FileInfo> files = new List<System.IO.FileInfo>();  
  
        fileNames = System.IO.Directory.GetFiles(path, "*.*", System.IO.SearchOption.AllDirectories);  
        foreach (string name in fileNames)  
        {  
            files.Add(new System.IO.FileInfo(name));  
        }  
        return files;  
    }  
}  
```  
  
 <span data-ttu-id="5a96e-107">`RegEx` 검색에서 반환되는 <xref:System.Text.RegularExpressions.MatchCollection> 개체를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-107">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="5a96e-108">이 예제에서는 각 일치 항목의 값만 결과로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-108">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="5a96e-109">그러나 LINQ를 사용하여 해당 컬렉션에 대한 모든 종류의 필터링, 정렬 및 그룹화를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-109">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="5a96e-110"><xref:System.Text.RegularExpressions.MatchCollection>은 제네릭이 아닌 <xref:System.Collections.IEnumerable> 컬렉션이므로 쿼리에 범위 변수의 형식을 명시적으로 기술해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-110">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a96e-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5a96e-111">Compiling the Code</span></span>  
 <span data-ttu-id="5a96e-112">System.Linq 및 System.IO 네임 스페이스에 대한 `using`지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a96e-112">Create a C# console application project with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a96e-113">참조</span><span class="sxs-lookup"><span data-stu-id="5a96e-113">See also</span></span>

- [<span data-ttu-id="5a96e-114">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="5a96e-114">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="5a96e-115">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="5a96e-115">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
