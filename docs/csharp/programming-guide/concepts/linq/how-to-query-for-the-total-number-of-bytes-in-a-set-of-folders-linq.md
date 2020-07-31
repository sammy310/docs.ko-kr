---
title: 폴더 집합의 전체 바이트 수를 쿼리하는 방법(LINQ)(C#)
description: C#에서 LINQ를 사용하여 지정된 폴더 및 하위 폴더에 있는 모든 파일에 사용되는 총 바이트 수를 확인하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 964d92a55599d60388f7add937c7f7338f697817
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104292"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="9d5f9-103">폴더 집합의 전체 바이트 수를 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="9d5f9-103">How to query for the total number of bytes in a set of folders (LINQ) (C#)</span></span>
<span data-ttu-id="9d5f9-104">이 예제에서는 지정된 폴더 및 모든 하위 폴더의 모든 파일에서 사용된 총 바이트 수를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-104">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d5f9-105">예제</span><span class="sxs-lookup"><span data-stu-id="9d5f9-105">Example</span></span>  
 <span data-ttu-id="9d5f9-106"><xref:System.Linq.Enumerable.Sum%2A> 메서드는 `select` 절에서 선택된 모든 항목의 값을 더합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-106">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="9d5f9-107"><xref:System.Linq.Enumerable.Sum%2A> 대신 <xref:System.Linq.Enumerable.Min%2A> 또는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 호출하여 지정된 디렉터리 트리에서 가장 큰 파일이나 가장 작은 파일을 검색하도록 이 쿼리를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-107">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 <span data-ttu-id="9d5f9-108">지정된 디렉터리 트리의 바이트 수만 계산하면 되는 경우 데이터 소스로 목록 컬렉션을 만드는 오버헤드를 유발하는 LINQ 쿼리를 만들지 않고 보다 효율적으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-108">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="9d5f9-109">LINQ 방식의 유용성은 쿼리가 더 복잡함에 따라 또는 동일한 데이터 소스에 대해 여러 쿼리를 실행해야 하는 경우에 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-109">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="9d5f9-110">쿼리는 파일 길이를 가져오기 위해 별도 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-110">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="9d5f9-111">`GetFiles` 호출에서 <xref:System.IO.FileInfo> 개체가 생성된 후 파일이 다른 스레드에서 삭제된 경우 발생할 수 있는 예외를 처리하기 위해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-111">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="9d5f9-112"><xref:System.IO.FileInfo> 개체가 이미 생성된 경우에도 <xref:System.IO.FileInfo> 개체는 속성에 처음 액세스할 때 최신 길이를 사용하여 해당 <xref:System.IO.FileInfo.Length%2A> 속성의 새로 고침을 시도하기 때문에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-112">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="9d5f9-113">코드는 이 작업을 쿼리 외부의 try-catch 블록에 배치하여, 부작용을 일으킬 수 있는 작업을 쿼리에서 방지하는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-113">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="9d5f9-114">일반적으로, 예외를 처리할 때는 애플리케이션이 알 수 없는 상태로 남지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-114">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d5f9-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9d5f9-115">Compiling the Code</span></span>  
<span data-ttu-id="9d5f9-116">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-116">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d5f9-117">참조</span><span class="sxs-lookup"><span data-stu-id="9d5f9-117">See also</span></span>

- [<span data-ttu-id="9d5f9-118">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="9d5f9-118">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="9d5f9-119">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="9d5f9-119">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
