---
description: '자세한 정보: 기본 쿼리 작업 (Visual Basic)'
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
ms.openlocfilehash: 1f8fbda83c21fe9032415d96ff2d7e184083a839
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428690"
---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)

이 항목에서는 Visual Basic의 LINQ (Language-Integrated Query) 식 및 쿼리에서 수행 하는 몇 가지 일반적인 작업 종류에 대해 간략하게 소개 합니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../language-reference/queries/index.md)  
  
 [연습: Visual Basic에서 쿼리 작성](walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>데이터 원본 지정 (원본)  

 LINQ 쿼리에서 첫 번째 단계는 쿼리 하려는 데이터 원본을 지정 하는 것입니다. 따라서 `From` 쿼리의 절은 항상 먼저 제공 됩니다. 쿼리 연산자 원본 유형에 따라 결과를 선택 하 고 모양을 합니다.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 `From`절은 데이터 소스, `customers` 및 *범위 변수* 를 지정 합니다 `cust` . 범위 변수는 쿼리 식에서 실제 반복이 발생 하지 않는다는 점을 제외 하 고 루프 반복 변수와 유사 합니다. 루프를 사용 하 여 쿼리를 실행할 때 `For Each` 범위 변수는의 각 연속 요소에 대 한 참조로 사용 됩니다 `customers` . 컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다. 명시적 형식 지정을 사용 하거나 사용 하지 않고 작성 된 쿼리의 예는 [쿼리 작업의 형식 관계 (Visual Basic)](type-relationships-in-query-operations.md)를 참조 하세요.  
  
 Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `From` [from 절](../../../language-reference/queries/from-clause.md)을 참조 하세요.  
  
## <a name="filtering-data-where"></a>데이터 필터링 (Where)  

 가장 일반적인 쿼리 작업은 부울 식의 형태로 필터를 적용 하는 것입니다. 그런 다음이 쿼리는 식이 true 인 요소만 반환 합니다. `Where`필터링을 수행 하는 데 절이 사용 됩니다. 필터는 결과 시퀀스에 포함할 데이터 소스의 요소를 지정 합니다. 다음 예에서는 런던에 주소가 있는 고객만 포함 되어 있습니다.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 And와 같은 논리 연산자를 사용 `And` `Or` 하 여 절에서 필터 식을 결합할 수 있습니다 `Where` . 예를 들어 London에서 이름이 Devon 인 고객만 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 런던 또는 파리에서 고객을 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `Where` [where 절](../../../language-reference/queries/where-clause.md)을 참조 하세요.  
  
## <a name="ordering-data-order-by"></a>데이터 순서 지정 (Order By)  

 반환 된 데이터를 특정 순서로 정렬 하는 것이 편리한 경우가 많습니다. `Order By`절을 지정 하면 반환 된 시퀀스의 요소가 지정 된 필드를 기준으로 정렬 됩니다. 예를 들어 다음 쿼리는 속성을 기반으로 결과를 정렬 합니다 `Name` . `Name`는 문자열 이므로 반환 된 데이터는 a에서 Z로 사전순으로 정렬 됩니다.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다. `Ascending`및를 모두 지정 하지 않을 경우 기본값은입니다 `Ascending` `Descending` .  
  
 Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `Order By` [Order by 절](../../../language-reference/queries/order-by-clause.md)을 참조 하십시오.  
  
## <a name="selecting-data-select"></a>데이터 선택 (Select)  

 `Select`절은 반환 된 요소의 형식 및 내용을 지정 합니다. 예를 들어 결과가 전체 `Customer` 개체, 하나의 `Customer` 속성, 속성의 하위 집합, 다양 한 데이터 원본의 속성 조합 또는 계산을 기반으로 하는 몇 가지 새로운 결과 형식으로 구성 될 지 여부를 지정할 수 있습니다. `Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션* 이라고 합니다.  
  
 전체 개체로 구성 된 컬렉션을 검색 하려면 `Customer` 범위 변수 자체를 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 `Customer`인스턴스가 많은 필드가 포함 된 많은 개체이 고 검색 하려는 모든가 이름인 경우 `cust.Name` 다음 예제와 같이를 선택할 수 있습니다. 지역 형식 유추는이가 결과 형식을 개체 컬렉션에서 문자열 컬렉션으로 변경 하는 것을 인식 합니다 `Customer` .  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 데이터 원본에서 여러 필드를 선택 하기 위해 다음 두 가지 옵션을 선택할 수 있습니다.  
  
- 절에서 `Select` 결과에 포함할 필드를 지정 합니다. 컴파일러는 해당 필드를 속성으로 포함 하는 익명 형식을 정의 합니다. 자세한 내용은 [무명 형식](../../language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예제의 반환 된 요소는 무명 형식의 인스턴스 이므로 코드의 다른 위치에서 이름을 기준으로 형식을 참조할 수 없습니다. 형식에 대 한 컴파일러 지정 이름에 일반 Visual Basic 코드에서 유효 하지 않은 문자가 포함 되어 있습니다. 다음 예제에서 쿼리에서 반환 되는 컬렉션의 요소는 `londonCusts4` 무명 형식의 인스턴스입니다.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     또는  
  
- 결과에 포함 하려는 특정 필드를 포함 하는 명명 된 형식을 정의 하 고 절에서 형식의 인스턴스를 만들고 초기화 `Select` 합니다. 반환 된 컬렉션 외부에서 개별 결과를 사용 해야 하는 경우 또는 메서드 호출에서 매개 변수로 전달 해야 하는 경우에만이 옵션을 사용 합니다. `londonCusts5`다음 예제에서의 형식은 IEnumerable (Of NamePhone)입니다.  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Visual Basic 절을 사용 하는 방법에 대 한 자세한 내용은 `Select` [select 절](../../../language-reference/queries/select-clause.md)을 참조 하세요.  
  
## <a name="joining-data-join-and-group-join"></a>데이터 조인 (조인 및 그룹 조인)  

 여러 가지 방법으로 절에서 둘 이상의 데이터 소스를 결합할 수 있습니다 `From` . 예를 들어, 다음 코드는 두 개의 데이터 원본을 사용 하 고 결과에서 둘 다의 속성을 암시적으로 결합 합니다. 이 쿼리는 성이 모음으로 시작 하는 학생을 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> [방법: 항목 목록 만들기](how-to-create-a-list-of-items.md)에서 만든 학생의 목록을 사용 하 여이 코드를 실행할 수 있습니다.  
  
 `Join`키워드는 SQL의와 동일 `INNER JOIN` 합니다. 두 컬렉션의 요소 사이에 일치 하는 키 값을 기준으로 두 컬렉션을 결합 합니다. 쿼리에서 일치 하는 키 값이 있는 컬렉션 요소의 전체 또는 일부를 반환 합니다. 예를 들어 다음 코드는 이전 암시적 조인의 작업을 복제 합니다.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` SQL의와 마찬가지로 컬렉션을 단일 계층 구조 컬렉션으로 결합 `LEFT JOIN` 합니다. 자세한 내용은 [Join 절](../../../language-reference/queries/join-clause.md) 및 [Group join 절](../../../language-reference/queries/group-join-clause.md)을 참조 하세요.  
  
## <a name="grouping-data-group-by"></a>데이터 그룹화 (Group By)  

 요소에 있는 `Group By` 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 하는 절을 추가할 수 있습니다. 예를 들어, 다음 코드는 year를 기준으로 학생을 그룹화 합니다.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 [방법: 항목 목록 만들기](how-to-create-a-list-of-items.md)에서 만든 학생 목록을 사용 하 여이 코드를 실행 하는 경우 `For Each` 문의 출력은 다음과 같습니다.  
  
 연도: Junior  
  
 Tucker, Michael  
  
 가르시아 섬, Hugo  
  
 가르시아 섬, Debra  
  
 Tucker, Lance  
  
 연도: 선임  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, 인 hanying  
  
 Adams, Terry  
  
 연도: Freshman  
  
 Mortensen, Sven  
  
 가르시아 섬, Cesar  
  
 다음 코드에 표시 된 변형은 클래스 연도를 정렬 한 다음 각 연도 내에서 성을 기준으로 학생을 주문 합니다.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 에 대 한 자세한 내용은 `Group By` [Group by 절](../../../language-reference/queries/group-by-clause.md)을 참조 하십시오.  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Collections.Generic.IEnumerable%601>
- [Visual Basic에서 LINQ 시작](getting-started-with-linq.md)
- [쿼리](../../../language-reference/queries/index.md)
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [LINQ](../../language-features/linq/index.md)
