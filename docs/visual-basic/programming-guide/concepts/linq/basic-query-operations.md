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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266380"
---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)
이 항목에서는 Visual Basic의 LINQ(언어 통합 쿼리) 식및 쿼리에서 수행하는 일반적인 작업 의 일부에 대해 간략하게 소개합니다. 자세한 내용은 아래 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../../visual-basic/language-reference/queries/index.md)  
  
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>데이터 원본 지정(에서)  
 LINQ 쿼리에서 첫 번째 단계는 쿼리할 데이터 원본을 지정하는 것입니다. 따라서 쿼리의 절이 `From` 항상 먼저 옵니다. 쿼리 연산자는 소스 유형에 따라 결과를 선택하고 셰이핑합니다.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 절은 `From` 데이터 원본 `customers`및 범위 *변수를* `cust`지정합니다. range 변수는 쿼리 식에서 실제 반복이 발생하지 않는다는 점을 제외하면 루프 반복 변수와 같습니다. 루프를 사용하여 `For Each` 쿼리가 실행되는 경우 range 변수는 에서 각 연속 요소에 `customers`대한 참조 역할을 합니다. 컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다. 명시적 입력 없이 작성된 쿼리의 예는 [쿼리 작업(Visual Basic)에서 관계 유형 참조를](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)참조합니다.  
  
 시각적 기본에서 절을 `From` 사용하는 방법에 대한 자세한 내용은 From [절을](../../../../visual-basic/language-reference/queries/from-clause.md)참조하십시오.  
  
## <a name="filtering-data-where"></a>데이터 필터링(위치)  
 가장 일반적인 쿼리 작업은 부울 식의 형태로 필터를 적용하는 것입니다. 그런 다음 쿼리는 식이 true인 요소만 반환합니다. 절은 `Where` 필터링을 수행하는 데 사용됩니다. 필터는 데이터 원본의 요소들이 결과 시퀀스에 포함하도록 지정합니다. 다음 예제에서는 런던에 주소가 있는 고객만 포함됩니다.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 논리 연산자(예: `And` `Or` 및 필터 식을 `Where` 절)에 결합할 수 있습니다. 예를 들어 런던 출신이고 이름이 Devon인 고객만 반환하려면 다음 코드를 사용합니다.  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 런던 또는 파리에서 반품하는 고객을 반품하려면 다음 코드를 사용하십시오.  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 시각적 기본에서 절을 `Where` 사용하는 방법에 대한 자세한 내용은 Where [절을](../../../../visual-basic/language-reference/queries/where-clause.md)참조하십시오.  
  
## <a name="ordering-data-order-by"></a>데이터 주문(주문별)  
 반환된 데이터를 특정 순서로 정렬하는 것이 편리한 경우가 많습니다. 이 `Order By` 절은 반환된 시퀀스의 요소를 지정된 필드 또는 필드에서 정렬하게 합니다. 예를 들어 다음 쿼리는 속성을 기반으로 `Name` 결과를 정렬합니다. 문자열이기 때문에 `Name` 반환된 데이터는 A에서 Z로 알파벳 순으로 정렬됩니다.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다. 기본값은 `Ascending` 둘 `Ascending` `Descending` 중 어느 쪽도 지정되지 않은 경우입니다.  
  
 시각적 기본에서 `Order By` 절을 사용하는 방법에 대한 자세한 내용은 [절별 순서를](../../../../visual-basic/language-reference/queries/order-by-clause.md)참조하십시오.  
  
## <a name="selecting-data-select"></a>데이터 선택(선택)  
 이 `Select` 절은 반환된 요소의 양식과 내용을 지정합니다. 예를 들어 결과가 전체 `Customer` 개체, 하나의 `Customer` 속성, 속성 하위 집합, 다양한 데이터 원본의 속성 조합 또는 계산에 기반한 새 결과 유형으로 구성되는지 여부를 지정할 수 있습니다. `Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.  
  
 전체 `Customer` 개체로 구성된 컬렉션을 검색하려면 range 변수 자체를 선택합니다.  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 `Customer` 인스턴스에 필드가 많은 큰 개체이고 검색하려는 모든 개체가 이름인 경우 `cust.Name`다음 예제와 같이 을 선택할 수 있습니다. 로컬 형식 추론은 이로 인해 결과 형식이 `Customer` 개체 컬렉션에서 문자열 컬렉션으로 변경된다는 것을 인식합니다.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 데이터 원본에서 여러 필드를 선택하려면 다음 두 가지 를 선택할 수 있습니다.  
  
- 절에서 `Select` 결과에 포함할 필드를 지정합니다. 컴파일러는 해당 필드가 있는 익명 형식을 속성으로 정의합니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예제에서 반환된 요소는 익명 형식의 인스턴스이므로 코드의 다른 위치에 있는 이름으로 형식을 참조할 수 없습니다. 형식에 대한 컴파일러 지정 이름에는 일반 Visual Basic 코드에서 유효하지 않은 문자가 포함되어 있습니다. 다음 예제에서 쿼리에서 `londonCusts4` 반환되는 컬렉션의 요소는 익명 형식의 인스턴스입니다.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     또는  
  
- 결과에 포함할 특정 필드를 포함하는 명명된 형식을 정의하고 `Select` 절에서 형식의 인스턴스를 만들고 초기화합니다. 반환되는 컬렉션 외부에서 개별 결과를 사용해야 하거나 메서드 호출에서 매개 변수로 전달해야 하는 경우에만 이 옵션을 사용합니다. 다음 예제의 `londonCusts5` 유형은 IEnumerable(네임폰)입니다.  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 시각적 기본에서 절을 `Select` 사용하는 방법에 대한 자세한 내용은 절 [선택](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조하십시오.  
  
## <a name="joining-data-join-and-group-join"></a>조인 데이터(조인 및 그룹 조인)  
 여러 가지 방법으로 절에 두 `From` 개 이상의 데이터 원본을 결합할 수 있습니다. 예를 들어 다음 코드는 두 데이터 원본을 사용하고 결과에서 두 데이터 소스의 속성을 암시적으로 결합합니다. 쿼리는 이름이 모음으로 시작하는 학생을 선택합니다.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> 항목 목록 [만들기 방법:](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 만든 학생 목록과 함께 이 코드를 실행할 수 있습니다.  
  
 키워드는 `Join` SQL에서와 `INNER JOIN` 동일합니다. 두 컬렉션의 요소 간에 일치하는 키 값을 기반으로 두 컬렉션을 결합합니다. 쿼리는 일치하는 키 값이 있는 컬렉션 요소의 전체 또는 일부를 반환합니다. 예를 들어 다음 코드는 이전 암시적 조인의 작업을 복제합니다.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`SQL에서와 마찬가지로 컬렉션을 단일 계층 적 컬렉션으로 `LEFT JOIN` 결합합니다. 자세한 내용은 [조인 절](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [그룹 조인 절을](../../../../visual-basic/language-reference/queries/group-join-clause.md)참조하십시오.  
  
## <a name="grouping-data-group-by"></a>데이터 그룹화(그룹별)  
 `Group By` 요소의 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화하는 절을 추가할 수 있습니다. 예를 들어 다음 코드는 학생학생을 수업 연도별로 그룹합니다.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 [방법: 항목 목록 만들기에서](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)만든 학생 목록을 사용하여 이 코드를 실행하는 경우 `For Each` 명령문의 출력은 다음과 같은 것입니다.  
  
 연도: 주니어  
  
 터커, 마이클  
  
 가르시아, 휴고  
  
 가르시아, 데브라  
  
 터커, 랜스  
  
 연도: 시니어  
  
 오멜첸코, 스베틀라나  
  
 오사다 시  
  
 파쿠리, 파디  
  
 펑, 하잉  
  
 애덤스, 테리  
  
 연도: 신입생  
  
 모텐슨, 스벤  
  
 가르시아, 세자르  
  
 다음 코드에 표시된 변형은 수업 연도를 정렬한 다음 매년 학생에게 성으로 주문합니다.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 자세한 `Group By`내용은 [그룹별 절을](../../../../visual-basic/language-reference/queries/group-by-clause.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Collections.Generic.IEnumerable%601>
- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
- [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
