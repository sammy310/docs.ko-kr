---
title: 폴더에 있는 파일의 내용을 쿼리 하는 방법 (LINQ)
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 02ffa398c495ca5af77685d62299c59cfc3b9d9c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347609"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="6a1b6-102">폴더에 있는 파일의 내용을 쿼리 하는 방법 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a1b6-102">How to query the contents of files in a folder (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="6a1b6-103">이 예제에서는 지정된 디렉터리 트리에 있는 모든 파일을 쿼리하고 각 파일을 연 다음 내용을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="6a1b6-104">이러한 유형의 기술을 사용하여 디렉터리 트리 내용의 인덱스 또는 역방향 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="6a1b6-105">이 예제에서는 단순 문자열 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="6a1b6-106">그러나 정규식을 사용하면 더 복잡한 유형의 패턴 일치를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="6a1b6-107">자세한 내용은 [방법: LINQ 쿼리와 정규식 결합 (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a1b6-108">예제</span><span class="sxs-lookup"><span data-stu-id="6a1b6-108">Example</span></span>  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
                                 Let fileText = GetFileText(file.FullName) _
                                 Where fileText.Contains(searchTerm) _
                                 Select file.FullName

        Console.WriteLine("The term " & searchTerm & " was found in:")

        ' Execute the query.
        For Each filename In queryMatchingFiles
            Console.WriteLine(filename)
        Next

        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()

    End Sub

    ' Read the contents of the file. This is done in a separate
    ' function in order to handle potential file system errors.
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compiling-the-code"></a><span data-ttu-id="6a1b6-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6a1b6-109">Compiling the code</span></span>

<span data-ttu-id="6a1b6-110">VB.NET 콘솔 응용 프로그램 프로젝트를 만들고, 코드 샘플을 복사 하 여 붙여넣고, 프로젝트 속성에서 시작 개체 값을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1b6-110">Create a VB.NET console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a1b6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a1b6-111">See also</span></span>

- [<span data-ttu-id="6a1b6-112">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a1b6-112">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="6a1b6-113">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a1b6-113">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
