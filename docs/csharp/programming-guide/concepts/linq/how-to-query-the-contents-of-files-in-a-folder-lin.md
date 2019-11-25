---
title: '방법: 폴더의 텍스트 파일 내용 쿼리(LINQ)(C#)'
ms.date: 07/20/2015
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
ms.openlocfilehash: 41be9aadcea3999cb7ea8c01460e72ff99e01765
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140948"
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a><span data-ttu-id="7ae20-102">방법: 폴더의 텍스트 파일 내용 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="7ae20-102">How to: Query the Contents of Text Files in a Folder (LINQ) (C#)</span></span>
<span data-ttu-id="7ae20-103">이 예제에서는 지정된 디렉터리 트리에 있는 모든 파일을 쿼리하고 각 파일을 연 다음 내용을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ae20-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="7ae20-104">이러한 유형의 기술을 사용하여 디렉터리 트리 내용의 인덱스 또는 역방향 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ae20-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="7ae20-105">이 예제에서는 단순 문자열 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ae20-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="7ae20-106">그러나 정규식을 사용하면 더 복잡한 유형의 패턴 일치를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ae20-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="7ae20-107">자세한 내용은 [LINQ 쿼리와 정규식 결합 방법(C#)](./how-to-combine-linq-queries-with-regular-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ae20-107">For more information, see [How to combine LINQ queries with regular expressions (C#)](./how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ae20-108">예</span><span class="sxs-lookup"><span data-stu-id="7ae20-108">Example</span></span>  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took   
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ae20-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7ae20-109">Compiling the Code</span></span>  
<span data-ttu-id="7ae20-110">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ae20-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ae20-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ae20-111">See also</span></span>

- [<span data-ttu-id="7ae20-112">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="7ae20-112">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="7ae20-113">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="7ae20-113">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
