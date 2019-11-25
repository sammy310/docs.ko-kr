---
title: LINQ 소개
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344932"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Visual Basic의 LINQ 소개
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. LINQ는 데이터의 형식에 관계없이 통합된 구문을 사용합니다.  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. 이러한 개체는 런타임 대신 컴파일 시간에 쿼리에서 더 빠르게 코드를 작성하고 오류를 catch할 수 있도록 하는 IntelliSense를 지원합니다. LINQ 쿼리를 추가 쿼리의 소스로 사용하여 결과를 구체화할 수 있습니다. 또한 사용자가 쿼리 결과를 쉽게 보고 수정할 수 있도록 LINQ 쿼리를 컨트롤에 바인딩할 수 있습니다.  
  
 예를 들어 다음 코드 예제에서는 컬렉션에서 고객의 목록을 반환하고 고객의 위치를 기준으로 고객을 그룹화하는 LINQ 쿼리를 보여 줍니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>예제 실행  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. LINQ 쿼리를 작성하는 경우 공급자는 해당 쿼리를 가져와서 데이터 소스가 실행할 수 있을 명령으로 변환합니다. 또한 공급자는 소스의 데이터를 쿼리 결과를 구성하는 개체로 변환합니다. 마지막으로 공급자는 데이터 소스에 업데이트를 보낼 때 개체를 데이터로 변환합니다.  
  
 Visual Basic includes the following LINQ providers.  
  
|Provider|설명|  
|---|---|  
|LINQ to Objects|LINQ to Objects 공급자를 사용하면 메모리 내 컬렉션 및 배열을 쿼리할 수 있습니다. 개체가 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 지원하는 경우 LINQ to Objects 공급자를 사용하면 개체를 쿼리할 수 있습니다.<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|LINQ to SQL 공급자를 사용하면 SQL Server 데이터베이스의 데이터를 쿼리하고 수정할 수 있습니다. 이렇게 하면 애플리케이션의 개체 모델을 데이터베이스의 테이블 및 개체에 쉽게 매핑할 수 있습니다.<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). 이 디자이너는 데이터베이스의 개체에 매핑되는 애플리케이션의 개체 모델을 만드는 데 사용됩니다. The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|LINQ to XML 공급자를 사용하면 XML을 쿼리하고 수정할 수 있습니다. 메모리 내 XML을 수정하거나 XML을 파일에서 로드하고 파일에 저장할 수 있습니다.<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. 데이터 세트의 데이터를 쿼리, 집계 및 업데이트하는 기능을 단순화하고 확장하기 위해 데이터 세트을 사용하는 애플리케이션에 LINQ의 기능을 추가할 수 있습니다.<br /><br /> 자세한 내용은 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)을 참조하세요.|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. 쿼리 식에는 소스 데이터에 적용할 정렬, 필터링, 그룹화 및 조인 또는 계산을 위한 명령도 포함될 수 있습니다. 쿼리 식 구문은 SQL의 구문과 유사하므로 구문의 상당 부분이 익숙하게 느껴질 수 있습니다.  
  
 쿼리 식은 `From` 절로 시작됩니다. 이 절은 쿼리의 소스 데이터와 소스 데이터의 각 요소를 개별적으로 참조하는 데 사용되는 변수를 식별합니다. These variables are named *range variables* or *iteration variables*. `From` 절은 `From` 절이 선택 사항인 `Aggregate` 쿼리를 제외한 쿼리에 필수적입니다. 쿼리의 범위와 소스가 `From` 또는 `Aggregate` 절에서 식별된 후 쿼리 절의 조합을 포함하여 쿼리를 구체화할 수 있습니다. For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. 예를 들어 다음 쿼리는 고객 데이터의 소스 컬렉션을 `customers` 변수로 식별하고 `cust`라는 반복 변수를 식별합니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 이 예제는 그 자체로 유효한 쿼리이지만 쿼리는 쿼리 절을 더 추가하여 결과를 구체화할 때 훨씬 더 강력해집니다. 예를 들어 `Where` 절을 추가하여 하나 이상의 값을 기준으로 결과를 필터링할 수 있습니다. 쿼리 식은 코드 한 줄입니다. 추가 쿼리 절을 쿼리의 끝에 추가하기만 하면 됩니다. You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. 다음 코드 예제에서는 `Where` 절이 포함된 쿼리의 예를 보여 줍니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 다른 강력한 쿼리 절은 데이터 소스에서 선택된 필드만 반환하는 데 사용할 수 있는 `Select` 절입니다. LINQ 쿼리는 강력한 형식의 개체로 구성된 열거 가능한 컬렉션을 반환합니다. 쿼리는 무명 형식 또는 명명된 형식의 컬렉션을 반환할 수 있습니다. `Select` 절을 사용하여 데이터 소스에서 단일 필드만 반환할 수 있습니다. 이렇게 하는 경우 반환된 컬렉션의 형식은 단일 필드의 형식입니다. 또한 `Select` 절을 사용하여 데이터 소스에서 여러 필드를 반환할 수도 있습니다. 이렇게 하는 경우 반환된 컬렉션의 형식은 새로운 무명 형식입니다. 또한 쿼리가 반환하는 필드를 지정된 명명된 형식의 필드와 일치시킬 수도 있습니다. 다음 코드 예제에서는 데이터 소스의 선택된 필드에서 제공된 데이터로 채워진 멤버가 있는 무명 형식의 컬렉션을 반환하는 쿼리 식을 보여 줍니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 LINQ 쿼리를 사용하여 여러 데이터 소스를 결합하고 단일 결과를 반환할 수도 있습니다. 이 작업은 하나 이상의 `From` 절을 사용하거나 `Join` 또는 `Group Join` 쿼리 절을 사용하여 수행할 수 있습니다. 다음 코드 예제에서는 고객 및 주문 데이터를 결합하고 고객 및 주문 데이터가 포함된 무명 형식의 컬렉션을 반환하는 쿼리 식을 보여 줍니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 `Group Join` 절을 사용하여 고객 개체의 컬렉션이 포함된 계층적 쿼리 결과를 만들 수 있습니다. 각 고객 개체에는 해당 고객에 대한 모든 주문의 컬렉션이 포함된 속성이 있습니다. 다음 코드 예제에서는 계층적 결과로 고객 및 주문 데이터를 결합하고 무명 형식의 컬렉션을 반환하는 쿼리 식을 보여 줍니다. 쿼리는 고객에 대한 주문 데이터의 컬렉션을 포함하는 `CustomerOrders` 속성이 포함된 형식을 반환합니다. 또한 해당 고객에 대한 모든 주문의 총계 합이 포함된 `OrderTotal` 속성도 포함합니다. 이 쿼리는 LEFT OUTER JOIN과 동일합니다.  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 강력한 쿼리 식을 만드는 데 사용할 수 있는 몇 가지 추가 LINQ 쿼리 연산자가 있습니다. 이 항목의 다음 섹션에서는 쿼리 식에 포함할 수 있는 다양한 쿼리 절에 대해 설명합니다. For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

<xref:System.Linq> 네임스페이스와 LINQ 쿼리를 지원하는 다른 네임스페이스의 클래스에는 애플리케이션의 요구 사항에 따라 쿼리를 만들고 구체화하기 위해 호출할 수 있는 메서드가 포함되어 있습니다. Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>원본 절

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. `From` 절은 쿼리의 소스 컬렉션과 반복 변수를 지정합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select 절

(선택 사항) A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

`Select` 절이 지정되지 않은 경우 쿼리의 반복 변수는 `From` 또는 `Aggregate` 절에서 지정된 반복 변수로 구성됩니다.

### <a name="where-clause"></a>Where 절

(선택 사항) A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join 절

(선택 사항) A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By 절

(선택 사항) A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join 절

(선택 사항) A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate 절

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. `Aggregate` 절은 하나 이상의 집계 함수를 컬렉션에 적용합니다. For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

또한 `Aggregate` 절을 사용하여 쿼리를 수정할 수 있습니다. 예를 들어 `Aggregate` 절을 사용하여 관련된 쿼리 컬렉션에 대한 계산을 수행할 수 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let 절

(선택 사항) A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct 절

(선택 사항) A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip 절

(선택 사항) A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While 절

(선택 사항) A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take 절

(선택 사항) A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While 절

(선택 사항) A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. 예를 들어 다음과 같은 가치를 제공해야 합니다.

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
LINQ에서 제공하는 열거 가능 형식과 쿼리 가능 형식의 멤버를 호출하여 추가 LINQ 쿼리 기능을 사용할 수 있습니다. 쿼리 식의 결과에 대해 특정 쿼리 연산자를 호출하여 이러한 추가 기능을 사용할 수 있습니다. For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. 이 예제에서는 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 메서드를 사용하여 쿼리 결과를 제네릭 목록으로 반환합니다.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. LINQ to SQL 파일의 확장명은 .dbml입니다.  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. 이렇게 하면 O/R 디자이너(개체 관계형 디자이너)가 표시됩니다. The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. LINQ to SQL 파일은 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가합니다. 이 개체에는 액세스하려는 테이블과 뷰의 속성 및 컬렉션과 호출하려는 저장 프로시저의 메서드가 포함되어 있습니다. 변경 내용을 LINQ to SQL(.dbml) 파일에 저장한 후 O/R 디자이너에서 정의된 <xref:System.Data.Linq.DataContext> 개체를 참조하여 코드에서 이러한 개체에 액세스할 수 있습니다. 프로젝트의 <xref:System.Data.Linq.DataContext> 개체는 LINQ to SQL 파일의 이름에 따라 명명됩니다. 예를 들어 Northwind.dbml이라는 LINQ to SQL 파일은 `NorthwindDataContext`라는 <xref:System.Data.Linq.DataContext> 개체를 만듭니다.  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. 이러한 요구 사항은 다음과 같습니다.  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 쿼리 실행은 쿼리를 만드는 것과 구분됩니다. 쿼리를 만든 후 쿼리 실행은 별도의 메커니즘으로 트리거됩니다. A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 기본적으로 쿼리를 만들 때 쿼리 자체는 즉시 실행되지 않습니다. 대신 쿼리 정의가 쿼리 결과를 참조하는 데 사용되는 변수에 저장됩니다. 쿼리 결과 변수가 코드(예: `For…Next` 루프)에서 나중에 액세스될 때 쿼리가 실행됩니다. This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. 쿼리 결과의 개별 요소에 액세스해야 하는 메서드를 적용하여 즉시 실행을 트리거할 수 있습니다. 이는 `Count`, `Sum`, `Average`, `Min` 또는 `Max`와 같은 집계 함수를 포함한 결과일 수 있습니다. For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 `ToList` 또는 `ToArray` 메서드를 사용하는 경우에도 즉시 실행이 시작됩니다. 이는 즉시 쿼리를 실행하고 결과를 캐시하려는 경우에 유용할 수 있습니다. For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>Visual Basic의 XML  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. XML 리터럴을 사용하면 코드에서 직접 XML을 작성할 수 있습니다. Visual Basic 컴파일러는 XML을 첫 번째 클래스 데이터 개체로 처리합니다.  
  
 다음 코드 예제에서는 XML 요소를 만들고 하위 요소와 특성에 액세스한 다음 LINQ를 사용하여 요소의 콘텐츠를 쿼리하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>관련 참고 자료  
  
|항목|설명|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[쿼리](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[LINQ(Language-Integrated Query)](../../concepts/linq/index.md)|LINQ에 대한 일반 정보, 프로그래밍 지침 및 샘플을 포함하고 있습니다.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|LINQ to SQL에 대한 일반 정보, 프로그래밍 지침 및 샘플을 포함하고 있습니다.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|LINQ to Objects에 대한 일반 정보, 프로그래밍 지침 및 샘플을 포함하고 있습니다.|  
|[LINQ to ADO.NET(포털 페이지)](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|LINQ to XML에 대한 일반 정보, 프로그래밍 지침 및 샘플을 포함하고 있습니다.|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [방법: 데이터베이스 쿼리](how-to-query-a-database-by-using-linq.md)  
  
 [방법: 저장 프로시저 호출](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [방법: 데이터베이스의 데이터 수정](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [방법: 조인을 사용하여 데이터 결합](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [방법: 쿼리 결과 정렬](how-to-sort-query-results-by-using-linq.md)  
  
 [방법: 쿼리 결과 필터링](how-to-filter-query-results-by-using-linq.md)  
  
 [방법: 데이터 개수, 합 또는 평균 계산](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [방법: 쿼리 결과의 최소값 또는 최대값 찾기](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>참조

- [LINQ(Language-Integrated Query)](../../concepts/linq/index.md)
- [Visual Basic의 LINQ to XML 개요](../../language-features/xml/overview-of-linq-to-xml.md)
- [LINQ to DataSet 개요](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)(Visual Studio의 LINQ to SQL 도구)
- [DataContext 메서드(O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
