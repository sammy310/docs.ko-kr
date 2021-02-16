---
description: '자세히 알아보기: 방법: 두 목록 간의 차집합 찾기 (LINQ) (Visual Basic)'
title: '방법: 두 목록 간의 차집합 구하기(LINQ)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: c877be03c3ff82d4be4814035a6401385d907e60
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483692"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="065e7-103">방법: 두 목록 간의 차집합을 설정 찾기 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="065e7-103">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="065e7-104">이 예제에서는 LINQ를 사용하여 두 개의 문자열 목록을 비교하고 names1.txt에 있지만 names2.txt에는 없는 줄만 출력하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="065e7-104">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="065e7-105">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="065e7-105">To create the data files</span></span>  
  
1. <span data-ttu-id="065e7-106">[방법: 문자열 컬렉션 결합 및 비교 (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)에 표시 된 대로 names1.txt 및 names2.txt를 솔루션 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="065e7-106">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="065e7-107">예제</span><span class="sxs-lookup"><span data-stu-id="065e7-107">Example</span></span>  
  
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
  
 <span data-ttu-id="065e7-108">,, 및와 같은 Visual Basic의 일부 쿼리 작업 <xref:System.Linq.Enumerable.Except%2A> 은 <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Union%2A> <xref:System.Linq.Enumerable.Concat%2A> 메서드 기반 구문 으로만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065e7-108">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="065e7-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="065e7-109">Compile the code</span></span>  

<span data-ttu-id="065e7-110">System.xml `Imports` 네임 스페이스에 대 한 문을 사용 하 여 Visual Basic 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="065e7-110">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="065e7-111">참조</span><span class="sxs-lookup"><span data-stu-id="065e7-111">See also</span></span>

- [<span data-ttu-id="065e7-112">LINQ 및 문자열(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="065e7-112">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
