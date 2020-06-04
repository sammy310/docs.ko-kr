---
title: '방법: 두 목록 간의 차집합 구하기(LINQ)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: f533b63b40325b34c5881c1e2f14aa4e576191c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396599"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a>방법: 두 목록 간의 차집합을 설정 찾기 (LINQ) (Visual Basic)
이 예제에서는 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 names1.txt에 있지만 names2.txt에는 없는 줄만 출력하는 방법을 보여 줍니다.  
  
### <a name="to-create-the-data-files"></a>데이터 파일을 만들려면  
  
1. [방법: 문자열 컬렉션 결합 및 비교 (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)에 표시 된 대로 names1 및 names2.txt를 솔루션 폴더에 복사 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 ,, 및와 같은 Visual Basic의 일부 쿼리 작업 <xref:System.Linq.Enumerable.Except%2A> 은 <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Union%2A> <xref:System.Linq.Enumerable.Concat%2A> 메서드 기반 구문 으로만 표현할 수 있습니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  
System.xml `Imports` 네임 스페이스에 대 한 문을 사용 하 여 Visual Basic 콘솔 응용 프로그램 프로젝트를 만듭니다.
  
## <a name="see-also"></a>참고 항목

- [LINQ 및 문자열(Visual Basic)](linq-and-strings.md)
