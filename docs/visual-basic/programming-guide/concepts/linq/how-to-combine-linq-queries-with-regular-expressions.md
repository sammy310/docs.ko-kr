---
description: '자세한 정보: LINQ 쿼리를 정규식과 결합 하는 방법 (Visual Basic)'
title: LINQ 쿼리와 정규식을 결합하는 방법
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: a2fd06f76c5c278ad1a67f3822151e5f73a2630e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424516"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="566dc-103">정규식을 사용 하 여 LINQ 쿼리를 결합 하는 방법 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566dc-103">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>

<span data-ttu-id="566dc-104">이 예제에서는 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 더 복잡한 텍스트 문자열 일치를 찾는 정규식을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-104">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="566dc-105">LINQ 쿼리를 사용하면 손쉽게 정규식을 통해 검색하려는 파일을 정확히 필터링하고 결과를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-105">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>

## <a name="example"></a><span data-ttu-id="566dc-106">예제</span><span class="sxs-lookup"><span data-stu-id="566dc-106">Example</span></span>

```vb
Imports System.IO
Imports System.Text.RegularExpressions

Class LinqRegExVB

    Shared Sub Main()

        ' Root folder to query, along with all subfolders.
        ' Modify this path as necessary so that it accesses your Visual Studio folder.
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"

        ' Take a snapshot of the file system.
        Dim fileList As IEnumerable(Of FileInfo) = GetFiles(startFolder)

        ' Create a regular expression to find all things "Visual".
        Dim searchTerm As New Regex("Visual (Basic|C#|C\+\+|Studio)")

        ' Search the contents of each .htm file.
        ' Remove the where clause to find even more matches!
        ' This query produces a list of files where a match
        ' was found, and a list of the matches in that file.
        ' Note: Explicit typing of "Match" in select clause.
        ' This is required because MatchCollection is not a
        ' generic IEnumerable collection.
        Dim queryMatchingFiles = From afile In fileList
                                Where afile.Extension = ".htm"
                                Let fileText = File.ReadAllText(afile.FullName)
                                Let matches = searchTerm.Matches(fileText)
                                Where (matches.Count > 0)
                                Select Name = afile.FullName,
                                       Matches = From match As Match In matches
                                                 Select match.Value

        ' Execute the query.
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")

        For Each fileMatches In queryMatchingFiles
            ' Trim the path a bit, then write
            ' the file name in which a match was found.
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)
            Console.WriteLine(s)

            ' For this file, write out all the matching strings
            For Each match In fileMatches.Matches
                Console.WriteLine("  " + match)
            Next
        Next

        ' Keep the console window open in debug mode
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()
    End Sub

    ' Function to retrieve a list of files. Note that this is a copy
    ' of the file information.
    Shared Function GetFiles(root As String) As IEnumerable(Of FileInfo)
        Return From file In My.Computer.FileSystem.GetFiles(
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")
               Select New FileInfo(file)
    End Function

End Class
```

<span data-ttu-id="566dc-107">`RegEx` 검색에서 반환되는 <xref:System.Text.RegularExpressions.MatchCollection> 개체를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-107">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="566dc-108">이 예제에서는 각 일치 항목의 값만 결과로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-108">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="566dc-109">그러나 LINQ를 사용하여 해당 컬렉션에 대한 모든 종류의 필터링, 정렬 및 그룹화를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-109">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="566dc-110"><xref:System.Text.RegularExpressions.MatchCollection>은 제네릭이 아닌 <xref:System.Collections.IEnumerable> 컬렉션이므로 쿼리에 범위 변수의 형식을 명시적으로 기술해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-110">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="566dc-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="566dc-111">Compile the code</span></span>

<span data-ttu-id="566dc-112">Visual Basic 콘솔 응용 프로그램 프로젝트를 만들고, 코드 샘플을 복사 하 여 붙여넣고, 프로젝트 속성에서 시작 개체 값을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="566dc-112">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="566dc-113">참조</span><span class="sxs-lookup"><span data-stu-id="566dc-113">See also</span></span>

- [<span data-ttu-id="566dc-114">LINQ 및 문자열(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566dc-114">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="566dc-115">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566dc-115">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)
