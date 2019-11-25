---
title: '방법: 폴더 집합의 전체 바이트 수 쿼리(LINQ)'
ms.date: 07/20/2015
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
ms.openlocfilehash: b926a3e0ed973f449718ca5883aeabc0bfcf7b91
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347643"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)
이 예제에서는 지정된 폴더 및 모든 하위 폴더의 모든 파일에서 사용된 총 바이트 수를 검색하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Linq.Enumerable.Sum%2A> 메서드는 `select` 절에서 선택된 모든 항목의 값을 더합니다. <xref:System.Linq.Enumerable.Sum%2A> 대신 <xref:System.Linq.Enumerable.Min%2A> 또는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 호출하여 지정된 디렉터리 트리에서 가장 큰 파일이나 가장 작은 파일을 검색하도록 이 쿼리를 쉽게 수정할 수 있습니다.  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 지정된 디렉터리 트리의 바이트 수만 계산하면 되는 경우 데이터 소스로 목록 컬렉션을 만드는 오버헤드를 유발하는 LINQ 쿼리를 만들지 않고 보다 효율적으로 이 작업을 수행할 수 있습니다. LINQ 방식의 유용성은 쿼리가 더 복잡함에 따라 또는 동일한 데이터 소스에 대해 여러 쿼리를 실행해야 하는 경우에 증가합니다.  
  
 쿼리는 파일 길이를 가져오기 위해 별도 메서드를 호출합니다. `GetFiles` 호출에서 <xref:System.IO.FileInfo> 개체가 생성된 후 파일이 다른 스레드에서 삭제된 경우 발생할 수 있는 예외를 처리하기 위해 이 작업을 수행합니다. <xref:System.IO.FileInfo> 개체가 이미 생성된 경우에도 <xref:System.IO.FileInfo> 개체는 속성에 처음 액세스할 때 최신 길이를 사용하여 해당 <xref:System.IO.FileInfo.Length%2A> 속성의 새로 고침을 시도하기 때문에 예외가 발생할 수 있습니다. 코드는 이 작업을 쿼리 외부의 try-catch 블록에 배치하여, 부작용을 일으킬 수 있는 작업을 쿼리에서 방지하는 규칙을 따릅니다. 일반적으로, 예외를 처리할 때는 애플리케이션이 알 수 없는 상태로 남지 않도록 주의해야 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.
  
## <a name="see-also"></a>참조

- [LINQ to Objects(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ 및 파일 디렉터리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
