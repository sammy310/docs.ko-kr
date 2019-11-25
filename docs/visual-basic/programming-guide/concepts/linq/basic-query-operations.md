---
title: 기본 쿼리 작업
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: e9a646d60bb22507f4c6bcbcdf9222fd0ed18f02
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345760"
---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)
This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query. 자세한 내용은 다음 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Specifying the Data Source (From)  
 In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query. Therefore, the `From` clause in a query always comes first. Query operators select and shape the result based on the type of the source.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`. The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs. When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`. 컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다. For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtering Data (Where)  
 Probably the most common query operation is applying a filter in the form of a Boolean expression. The query then returns only those elements for which the expression is true. A `Where` clause is used to perform the filtering. The filter specifies which elements in the data source to include in the resulting sequence. In the following example, only those customers who have an address in London are included.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause. For example, to return only those customers who are from London and whose name is Devon, use the following code:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 To return customers from London or Paris, use the following code:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Ordering Data (Order By)  
 It often is convenient to sort returned data into a particular order. The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields. For example, the following query sorts the results based on the `Name` property. Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다. The default is `Ascending` when neither `Ascending` nor `Descending` is specified.  
  
 For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Selecting Data (Select)  
 The `Select` clause specifies the form and content of returned elements. For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation. `Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.  
  
 To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example. Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 To select multiple fields from the data source, you have two choices:  
  
- In the `Select` clause, specify the fields you want to include in the result. The compiler will define an anonymous type that has those fields as its properties. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code. The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code. In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     또는  
  
- Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause. Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls. The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Joining Data (Join and Group Join)  
 You can combine more than one data source in the `From` clause in several ways. For example, the following code uses two data sources and implicitly combines properties from both of them in the result. The query selects students whose last names start with a vowel.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 The `Join` keyword is equivalent to an `INNER JOIN` in SQL. It combines two collections based on matching key values between elements in the two collections. The query returns all or part of the collection elements that have matching key values. For example, the following code duplicates the action of the previous implicit join.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL. For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Grouping Data (Group By)  
 You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements. For example, the following code groups students by class year.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:  
  
 Year: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Year: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Year: Freshman  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 The variation shown in the following code orders the class years, and then orders the students within each year by last name.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>참조

- <xref:System.Collections.Generic.IEnumerable%601>
- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
- [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
