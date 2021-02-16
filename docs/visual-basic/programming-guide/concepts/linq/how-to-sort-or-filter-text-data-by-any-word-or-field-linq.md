---
description: '자세한 정보: 방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링 (LINQ) (Visual Basic)'
title: '방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)'
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: 49fff8df58b41acf7c8a63b94e8d1c85eefec8ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434929"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a>방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(Visual Basic)

다음 예제에서는 줄의 필드를 기준으로 쉼표로 구분된 값 등의 구조적 텍스트 줄을 정렬하는 방법을 보여 줍니다. 필드가 런타임에 동적으로 지정될 수도 있습니다. scores.csv의 필드가 학생의 ID 번호와 일련의 시험 성적 4개를 나타낸다고 가정합니다.

### <a name="to-create-a-file-that-contains-data"></a>데이터가 포함된 파일을 만들려면

[방법: 서로 다른 파일의 콘텐츠 조인 (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md) 항목에서 scores.csv 데이터를 복사 하 여 솔루션 폴더에 저장 합니다.

## <a name="example"></a>예

```vb
Class SortLines

    Shared Sub Main()
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' Change this to any value from 0 to 4
        Dim sortField As Integer = 1

        Console.WriteLine("Sorted highest to lowest by field " & sortField)

        ' Demonstrates how to return query from a method.
        ' The query is executed here.
        For Each str As String In SortQuery(scores, sortField)
            Console.WriteLine(str)
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()

    End Sub

    Shared Function SortQuery(
        ByVal source As IEnumerable(Of String),
        ByVal num As Integer) As IEnumerable(Of String)

        Dim scoreQuery = From line In source
                         Let fields = line.Split(New Char() {","})
                         Order By fields(num) Descending
                         Select line

        Return scoreQuery
    End Function
End Class
' Output:
' Sorted highest to lowest by field 1
' 116, 99, 86, 90, 94
' 120, 99, 82, 81, 79
' 111, 97, 92, 81, 60
' 114, 97, 89, 85, 82
' 121, 96, 85, 91, 60
' 122, 94, 92, 91, 91
' 117, 93, 92, 80, 87
' 118, 92, 90, 83, 78
' 113, 88, 94, 65, 91
' 112, 75, 84, 91, 39
' 119, 68, 79, 88, 92
' 115, 35, 72, 91, 70
```

이 예에서는 함수에서 쿼리 변수를 반환 하는 방법도 보여 줍니다.

## <a name="compile-the-code"></a>코드 컴파일

System.xml `Imports` 네임 스페이스에 대 한 문을 사용 하 여 Visual Basic 콘솔 응용 프로그램 프로젝트를 만듭니다.

## <a name="see-also"></a>추가 정보

- [LINQ 및 문자열(Visual Basic)](linq-and-strings.md)
