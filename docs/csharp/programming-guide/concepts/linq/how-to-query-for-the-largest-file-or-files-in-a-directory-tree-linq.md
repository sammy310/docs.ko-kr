---
title: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리하는 방법(LINQ)(C#)
description: 이 C# 예제에서는 파일 크기(바이트)와 관련된 다섯 개의 LINQ 쿼리를 보여줍니다. FileInfo 개체의 일부 다른 속성을 쿼리하도록 수정할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: 049db9bf104af1593ba9807c307008e8e760da32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176255"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="1d1a8-104">디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="1d1a8-104">How to query for the largest file or files in a directory tree (LINQ) (C#)</span></span>

<span data-ttu-id="1d1a8-105">이 예제에서는 파일 크기(바이트)와 관련된 다섯 개의 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-105">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="1d1a8-106">가장 큰 파일의 크기(바이트)를 검색하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-106">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="1d1a8-107">가장 작은 파일의 크기(바이트)를 검색하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-107">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="1d1a8-108">지정된 루트 폴더 아래의 하나 이상 폴더에서 <xref:System.IO.FileInfo> 개체의 가장 큰 파일이나 가장 작은 파일을 검색하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-108">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="1d1a8-109">가장 큰 파일 10개 등의 시퀀스를 검색하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-109">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="1d1a8-110">지정된 크기보다 작은 파일을 무시하고 해당 파일 크기(바이트)에 따라 파일을 그룹으로 정렬하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-110">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d1a8-111">예제</span><span class="sxs-lookup"><span data-stu-id="1d1a8-111">Example</span></span>  

 <span data-ttu-id="1d1a8-112">다음 예제에서는 파일 크기(바이트)에 따라 파일을 쿼리 및 그룹화하는 방법을 보여 주는 5개의 개별 쿼리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-112">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="1d1a8-113">쿼리가 <xref:System.IO.FileInfo> 개체의 다른 일부 속성을 기반으로 하도록 이러한 예제를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-113">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```csharp  
class QueryBySize  
{  
    static void Main(string[] args)  
    {  
        QueryFilesBySize();  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    private static void QueryFilesBySize()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Return the size of the largest file  
        long maxSize =  
            (from file in fileList  
             let len = GetFileLength(file)  
             select len)  
             .Max();  
  
        Console.WriteLine("The length of the largest file under {0} is {1}",  
            startFolder, maxSize);  
  
        // Return the FileInfo object for the largest file  
        // by sorting and selecting from beginning of list  
        System.IO.FileInfo longestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len descending  
             select file)  
            .First();  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, longestFile.FullName, longestFile.Length);  
  
        //Return the FileInfo of the smallest file  
        System.IO.FileInfo smallestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len ascending  
             select file).First();  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, smallestFile.FullName, smallestFile.Length);  
  
        //Return the FileInfos for the 10 largest files  
        // queryTenLargest is an IEnumerable<System.IO.FileInfo>  
        var queryTenLargest =  
            (from file in fileList  
             let len = GetFileLength(file)  
             orderby len descending  
             select file).Take(10);  
  
        Console.WriteLine("The 10 largest files under {0} are:", startFolder);  
  
        foreach (var v in queryTenLargest)  
        {  
            Console.WriteLine("{0}: {1} bytes", v.FullName, v.Length);  
        }  
  
        // Group the files according to their size, leaving out  
        // files that are less than 200000 bytes.
        var querySizeGroups =  
            from file in fileList  
            let len = GetFileLength(file)  
            where len > 0  
            group file by (len / 100000) into fileGroup  
            where fileGroup.Key >= 2  
            orderby fileGroup.Key descending  
            select fileGroup;  
  
        foreach (var filegroup in querySizeGroups)  
        {  
            Console.WriteLine(filegroup.Key.ToString() + "00000");  
            foreach (var item in filegroup)  
            {  
                Console.WriteLine("\t{0}: {1}", item.Name, item.Length);  
            }  
        }  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the FileInfo.Length property.  
    // In this particular case, it is safe to swallow the exception.  
    static long GetFileLength(System.IO.FileInfo fi)  
    {  
        long retval;  
        try  
        {  
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
  
 <span data-ttu-id="1d1a8-114">전체 <xref:System.IO.FileInfo> 개체를 하나 이상 반환하기 위해 쿼리는 먼저 데이터 소스에서 각 개체를 검사한 다음 해당 Length 속성 값을 기준으로 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-114">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="1d1a8-115">그런 다음 길이가 가장 큰 단일 개체나 시퀀스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-115">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="1d1a8-116">목록의 첫 번째 요소를 반환하려면 <xref:System.Linq.Enumerable.First%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-116">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="1d1a8-117">처음 n개의 요소를 반환하려면 <xref:System.Linq.Enumerable.Take%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-117">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="1d1a8-118">목록의 시작 부분에 가장 작은 요소를 배치하려면 내림차순 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-118">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="1d1a8-119">`GetFiles` 호출에서 <xref:System.IO.FileInfo> 개체가 생성된 이후 기간 내에 파일이 다른 스레드에서 삭제된 경우 발생할 수 있는 예외를 처리하기 위해 쿼리에서 별도 메서드를 호출하여 파일 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-119">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="1d1a8-120"><xref:System.IO.FileInfo> 개체가 이미 생성된 경우에도 <xref:System.IO.FileInfo> 개체는 속성에 처음 액세스할 때 최신 크기(바이트)를 사용하여 해당 <xref:System.IO.FileInfo.Length%2A> 속성의 새로 고침을 시도하기 때문에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-120">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="1d1a8-121">이 작업을 쿼리 외부의 try-catch 블록에 배치하여, 부작용을 일으킬 수 있는 작업을 쿼리에서 방지하는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-121">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="1d1a8-122">일반적으로, 예외를 처리할 때는 애플리케이션이 알 수 없는 상태로 남지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-122">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d1a8-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1d1a8-123">Compiling the Code</span></span>  

<span data-ttu-id="1d1a8-124">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a8-124">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d1a8-125">참조</span><span class="sxs-lookup"><span data-stu-id="1d1a8-125">See also</span></span>

- [<span data-ttu-id="1d1a8-126">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="1d1a8-126">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="1d1a8-127">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="1d1a8-127">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
