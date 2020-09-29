---
title: 지정된 특성 또는 이름을 갖는 파일을 쿼리하는 방법(C#)
description: C#에서 LINQ를 사용하여 디렉터리 트리에서 지정된 파일 이름 확장명을 가진 파일을 찾는 방법과 최신 또는 가장 오래된 파일을 반환하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
ms.openlocfilehash: 01a3482d8ea4c95b60dd9434320f175f0498c3e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165314"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a>지정된 특성 또는 이름을 갖는 파일을 쿼리하는 방법(C#)

이 예제에서는 지정된 디렉터리 트리에서 지정된 파일 이름 확장명(예: ".txt")을 가진 파일을 모두 찾는 방법을 보여 줍니다. 또한 생성 시간을 기준으로 트리에서 가장 최신 파일이나 가장 오래된 파일을 반환하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous
        // query as a starting point. fileQuery is not
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  

  System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.
  
## <a name="see-also"></a>참조

- [LINQ to Objects(C#)](./linq-to-objects.md)
- [LINQ 및 파일 디렉터리(C#)](./linq-and-file-directories.md)
