---
title: 기본 쿼리 작업(Visual Basic)
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
ms.openlocfilehash: ed5ed56366911c3676c4413711207ac0a8f85765
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826199"
---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)
이 항목에서는에 대 한 간략 한 소개 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Visual Basic의 경우에 쿼리에서 수행 하는 작업의 일반적인 종류의 일부에 대 한 식입니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../../visual-basic/language-reference/queries/index.md)  
  
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>데이터 원본 (원본)를 지정합니다.  
 에 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리, 쿼리 하려는 데이터 원본을 지정 하는 첫 번째 단계입니다. 따라서는 `From` 쿼리 절은 항상 첫 번째를 제공 합니다. 쿼리 연산자 선택한 원본 유형에 따라 결과 셰이프 합니다.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 `From` 데이터 소스를 지정 하는 절 `customers`, 및 *범위 변수*, `cust`합니다. 쿼리 식에서 실제 반복이 발생 하지는 점을 제외 하 고 범위 변수는 루프 반복 변수를 사용 하 여 비슷합니다. 쿼리 실행 되는 시기를 자주 사용 하 여는 `For Each` 루프의 각 연속 요소에 대 한 참조 역할도 범위 변수 `customers`합니다. 컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다. 명시적 형식 지정 하지 않고 사용 하 여 작성 하는 쿼리의 예제를 참조 하세요 [쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.  
  
 사용 하는 방법에 대 한 자세한 합니다 `From` Visual basic에서는 절 참조 [From 절](../../../../visual-basic/language-reference/queries/from-clause.md)합니다.  
  
## <a name="filtering-data-where"></a>데이터 필터링 (위치)  
 아마도 가장 일반적인 쿼리 작업은 부울 식 형태로 필터를 적용 합니다. 다음 쿼리는 식이 true 인 요소만 반환 합니다. `Where` 절을 필터링 하는 데 사용 됩니다. 필터 결과 시퀀스에 포함할 데이터 원본에 있는 요소를 지정 합니다. 다음 예제에서는 London에 주소가 있는 고객만 포함 됩니다.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 와 같은 논리 연산자를 사용할 수 있습니다 `And` 하 고 `Or` 에서 필터 식을 결합 하는 `Where` 절. 예를 들어, london에서 인 이며 이름이 Devon 고객만 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 London 또는 Paris 고객을 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 사용 하는 방법에 대 한 자세한 합니다 `Where` Visual basic에서는 절 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.  
  
## <a name="ordering-data-order-by"></a>(Order By) 데이터 정렬  
 종종 유용 반환 된 데이터를 특정 순서로 정렬 합니다. `Order By` 절은 지정된 된 필드 또는 필드를 기준으로 정렬 됩니다 반환된 된 시퀀스의 요소를 게 합니다. 예를 들어 다음 쿼리는 정렬 기준으로 결과 `Name` 속성입니다. 때문에 `Name` 문자열인 경우 반환된 된 데이터는 A에서 Z까지 사전순으로 정렬 됩니다.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다. 기본값은 `Ascending` 하지 않은 경우 `Ascending` 도 `Descending` 지정 됩니다.  
  
 사용 하는 방법에 대 한 자세한 합니다 `Order By` Visual basic에서는 절 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
## <a name="selecting-data-select"></a>데이터 (선택)를 선택합니다.  
 `Select` 절 형식 및 반환 되는 요소는 콘텐츠를 지정 합니다. 결과 전체으로 구성할 것인지를 지정할 수는 예를 들어 `Customer` 개체를 하나만 `Customer` 속성, 속성의 하위 집합, 다양 한 데이터 원본 또는 몇 가지 새 결과 형식에서 속성의 조합을 기반으로 계산 합니다. `Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.  
  
 전체로 구성 된 컬렉션을 검색 하 `Customer` 개체 자체가 범위 변수를 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 경우는 `Customer` 이름인 검색 하려는 모든 인스턴스는 여러 필드가 있는 큰 개체를 선택할 수 있습니다 `cust.Name`다음 예제에서와 같이 합니다. 지역 형식 유추는이 형식을 변경 하는 결과의 컬렉션에서 인식 `Customer` 문자열의 컬렉션 개체입니다.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 데이터 원본에서 여러 필드를 선택 하는 두 가지 옵션이 있습니다.  
  
-   에 `Select` 절 결과에 포함할 필드를 지정 합니다. 컴파일러는 해당 속성으로 해당 필드가 있는 익명 형식을 정의 합니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예에서 반환 되는 요소는 무명 형식의 인스턴스 이기 때문에 참조할 수 없습니다를 형식 이름으로 다른 곳에서 코드에서. 컴파일러에서 지정 된 이름 형식에 대 한 일반적인 Visual Basic 코드에서 잘못 된 문자가 있습니다. 다음 예의 쿼리에 의해 반환 되는 컬렉션의 요소에서 `londonCusts4` 무명 형식의 인스턴스인  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     또는  
  
-   결과에 포함 하 고 만들고에서 형식의 인스턴스를 초기화 하려는 특정 필드를 포함 하는 명명 된 형식 정의 `Select` 절. 반환 된 컬렉션 외부 개별 결과 사용 해야 하는 경우에 또는 메서드 호출에 매개 변수로 전달 해야 할 경우이 옵션을 사용 합니다. 형식의 `londonCusts5` 다음 예제는 IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 사용 하는 방법에 대 한 자세한 합니다 `Select` Visual basic에서는 절 참조 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)합니다.  
  
## <a name="joining-data-join-and-group-join"></a>조인 데이터 (조인 및 그룹 조인)  
 둘 이상의 데이터 원본에 결합할 수 있습니다는 `From` 여러 가지 방법으로 절. 예를 들어, 다음 코드는 두 데이터 소스를 사용 하 여 하 고 암시적으로 두 개의 결과는 속성을 결합 합니다. 쿼리는 마지막 이름이 모음을 사용 하 여 시작 하는 학생을 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  만든 학생의 목록을 사용 하 여이 코드를 실행할 수 있습니다 [방법: 항목 목록을 만드는](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다.  
  
 합니다 `Join` 키워드는 해당 하는 `INNER JOIN` sql에서입니다. 두 컬렉션의 요소 간에 일치 하는 키 값을 기반으로 하는 두 컬렉션을 결합 합니다. 쿼리는 전체 또는 일부 일치 하는 키 값이 있는 컬렉션 요소를 반환 합니다. 예를 들어, 다음 코드는 이전 암시적 조인 작업을 복제합니다.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` 마찬가지로 컬렉션을 단일 계층 구조 컬렉션으로 결합 한 `LEFT JOIN` sql에서입니다. 자세한 내용은 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md) 하 고 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.  
  
## <a name="grouping-data-group-by"></a>데이터 그룹화 (Group By)  
 추가할 수는 `Group By` 요소 중 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 할 절. 예를 들어, 다음 코드를 클래스 매년 학생을 그룹화합니다.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 만든 학생 목록을 사용 하 여이 코드를 실행 하는 경우 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 출력 된 `For Each` 문은:  
  
 연도: Junior  
  
 Tucker, Michael  
  
 가르시아, Hugo  
  
 가르시아, Debra  
  
 Tucker에 Lance  
  
 연도: 선임  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 인 Hanying Feng으로  
  
 Terry Adams,  
  
 연도: 대학 1 학년  
  
 Mortensen, Sven  
  
 가르시아, Cesar  
  
 다음 코드 에서처럼 변형 클래스 년 정렬 및 다음 성을 기준으로 각 연도 내에서 학생을 정렬 합니다.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 에 대 한 자세한 내용은 `Group By`를 참조 하세요 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Collections.Generic.IEnumerable%601>
- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
- [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
